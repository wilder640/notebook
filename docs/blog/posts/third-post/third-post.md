---
title: 第三篇
description: Minim anim ad officia culpa cupidatat incididunt deserunt ex exercitation consequat non reprehenderit nulla.
date: 2024-06-05
banner: tag_cloud.jpg
tags:
    - HTML5
    - CSS
category: CSS
comments: true
---

## 第三篇文章

### 第一段

Here is some code: `#!py3 import pymdownx; pymdownx.__version__`.

The mock shebang will be treated like text here: ` #!js var test = 0; `.

```python title="globals.py" linenums="1" hl_lines="9-12"
import typing as t
from threading import local

if t.TYPE_CHECKING:
    import typing_extensions as te
    from .core import Context

_local = local() # (1)!


@t.overload
def get_current_context(silent: "te.Literal[False]" = False) -> "Context":
    ...


@t.overload
def get_current_context(silent: bool = ...) -> t.Optional["Context"]:
    ...


def get_current_context(silent: bool = False) -> t.Optional["Context"]:
    """Returns the current click context.  This can be used as a way to
    access the current context object from anywhere.  This is a more implicit
    alternative to the :func:`pass_context` decorator.  This function is
    primarily useful for helpers such as :func:`echo` which might be
    interested in changing its behavior based on the current context.

    To push the current context, :meth:`Context.scope` can be used.

    .. versionadded:: 5.0

    :param silent: if set to `True` the return value is `None` if no context
                   is available.  The default behavior is to raise a
                   :exc:`RuntimeError`.
    """
    try:
        return t.cast("Context", _local.stack[-1])
    except (AttributeError, IndexError) as e:
        if not silent:
            raise RuntimeError("There is no active click context.") from e

    return None


def push_context(ctx: "Context") -> None:
    """Pushes a new context to the current stack."""
    _local.__dict__.setdefault("stack", []).append(ctx)


def pop_context() -> None:
    """Removes the top level from the stack."""
    _local.stack.pop()


def resolve_color_default(color: t.Optional[bool] = None) -> t.Optional[bool]:
    """Internal helper to get the default value of the color flag.  If a
    value is passed it's returned unchanged, otherwise it's looked up from
    the current context.
    """
    if color is not None:
        return color

    ctx = get_current_context(silent=True)

    if ctx is not None:
        return ctx.color

    return None

```

1. 這是一個測試的註解

=== "Tab 1"
    Aliquip pariatur magna laboris nulla sint eiusmod cupidatat aute et non dolor excepteur reprehenderit aliqua. **content**.

    Multiple paragraphs.

=== "Tab 2"
    More Tempor ut aute in reprehenderit.Consequat minim officia aliqua ex. **content**.

    - list item a
    - list item b

* list1
  * child-list1
  * child-list2
  * child-list3
    * cc-list1
    * cc-list3
    * cc-list3
* list2
* list3
* list4

Task List

-   [X] item 1
    *   [X] item A
    *   [ ] item B
        more text
        +   [x] item a
        +   [ ] item b
        +   [x] item c
    *   [X] item C
-   [ ] item 2
-   [ ] item 3

Elit est ad est proident exercitation id ex voluptate veniam. Qui quis eiusmod qui sint ea cupidatat non. Veniam Lorem et est et et. Esse elit nulla deserunt aliquip ea excepteur deserunt proident culpa in cillum. Aute exercitation aute cillum occaecat aute dolor nulla eiusmod qui qui nostrud mollit in. Ad exercitation id cillum laboris dolore incididunt aliquip. Velit voluptate elit minim incididunt irure exercitation aliqua et ad nostrud.

Voluptate velit nulla pariatur occaecat cupidatat ea consectetur voluptate magna magna aliquip. Ullamco labore aliqua quis non enim anim exercitation. Culpa mollit elit est sint in laboris. Laborum commodo non aliquip nostrud excepteur quis enim enim sit duis. Nisi culpa aute consectetur elit occaecat culpa duis ipsum eu reprehenderit consectetur mollit id. Nostrud do duis est laboris exercitation. Anim reprehenderit quis excepteur labore deserunt reprehenderit dolore voluptate.

Ex sint fugiat dolor eiusmod in. Deserunt minim occaecat mollit amet fugiat quis. Ea laborum minim fugiat excepteur ex quis commodo tempor nulla enim dolore.

### 第二段

Deserunt ut consectetur duis commodo nulla veniam occaecat in consectetur cupidatat. Consequat sint anim esse consequat pariatur fugiat voluptate laboris sit veniam do minim ad. Velit nisi et aliqua ullamco ullamco est labore minim ea et duis dolore consectetur enim. Eu enim ipsum exercitation adipisicing labore tempor esse. Aliqua aliquip magna sunt tempor aute ex. Ex sit commodo tempor pariatur.

Consectetur consectetur veniam laborum consectetur anim nostrud nostrud. Quis commodo eiusmod sint duis sit reprehenderit reprehenderit. Commodo anim do occaecat aliqua non aliquip in voluptate cillum eiusmod. Velit voluptate commodo officia in commodo nostrud enim eu ut nostrud tempor. Do pariatur irure incididunt consequat minim velit non ut nulla est tempor voluptate ad. Veniam cillum in amet veniam eu ex consectetur adipisicing eiusmod proident reprehenderit proident et eiusmod.

Non aute do esse anim et ipsum laborum officia excepteur eu. Enim amet sint eiusmod labore pariatur eu mollit ea tempor reprehenderit culpa esse magna. Culpa nulla reprehenderit nostrud qui ex voluptate irure cupidatat elit commodo.

### 第三段

Ex ullamco in pariatur Lorem voluptate exercitation sunt id qui ex nulla cillum ut. Aute culpa consequat adipisicing proident culpa culpa minim proident veniam mollit. Occaecat culpa magna amet commodo cillum consectetur exercitation fugiat enim.

Magna deserunt tempor excepteur officia proident culpa quis fugiat consequat exercitation. Officia labore mollit ea sint cillum. Ut quis Lorem velit proident commodo sit. Laboris do nulla magna culpa exercitation. Ad ad duis fugiat occaecat fugiat nulla eu anim officia velit.

Commodo ullamco nisi aliquip mollit nisi ullamco id. Ullamco labore voluptate eu sunt. Cupidatat deserunt exercitation ea do nisi laboris laborum culpa tempor esse laborum. Adipisicing commodo eiusmod esse do ut elit elit deserunt. Quis sit sunt pariatur occaecat eiusmod sunt et. Voluptate nulla aliqua sit consequat aliqua id nisi commodo ad qui voluptate non.

### 第四段

Quis exercitation laborum excepteur consectetur qui exercitation esse nostrud. Sit qui aute ex laborum ad aliqua adipisicing ut nulla irure deserunt. Ipsum esse commodo cillum sint laboris duis sint. Consequat est ipsum elit elit in occaecat consectetur amet cupidatat. Eiusmod id dolore labore laboris non dolor eiusmod ea minim ullamco. Aliqua consequat qui qui sunt.

Ad duis ex ipsum aute sunt cillum magna. Nulla proident velit irure proident officia anim et exercitation cupidatat est elit non ex. Aute nostrud magna aliqua irure anim pariatur excepteur. Pariatur fugiat dolor ad fugiat Lorem incididunt. Esse aute eu proident id aliquip officia aliqua eu aliqua. Sunt labore consequat esse et minim irure ad in voluptate sit commodo ut ipsum velit. Nulla consectetur dolor consequat est minim do sit aliqua commodo esse.
