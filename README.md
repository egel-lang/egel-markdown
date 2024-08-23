# Egel enhanced Markdown

Egel enhanced Markdown is a markdown document with included scripting.

## Egel code

Start egel code by beginning a line with `.egel`. The rest of the
line and all consecutive indented lines are code.

```
    .egel
        def fac = [0 -> 1| N -> N * (fac (N - 1))];;
```

The code is dynamically evaluated so egel declarations must be ended
with double semicolons.

## Shorthands

A number of shorthands make writing code easier, just as normal code
that line and all following indented lines define egel code.

```
    .import "regex.ego";;
    .include System;;
    .data branch, leaf;;
    .def author = "Marco Devillers";;
    .val global = ref 3.14;;
```

## Substitution

In the markdown document, all expressions surrounded by double curly
braces are evaluated.

```
    This document is written by {{author}}.
```

## Hooks

Hooks can be defined and are run after the initial processing of the
document. They take the Markdown file as a list of lines and should
output a list of lines.

```
    .hook (map [L -> L + "!"]);;
```
