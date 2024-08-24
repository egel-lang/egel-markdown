# Egel-enhanced Markdown

Egel-enhanced Markdown is a markdown document with included scripting.

## Running the script

Run the script on Egel-enhanced Markdown with the following command:

```
    egelmd.eg [--debug] <fn.emd>
```

## Egel code

Start Egel code by beginning a line with `.egel`. The rest of the
line and all consecutive indented lines are code.

```
    .egel
        def fac = [0 -> 1| N -> N * (fac (N - 1))];;
```

The code is dynamically evaluated so egel declarations must end
with double semicolons.

## Shorthands

Several shorthands make writing code easier, just as normal code
that line and all following indented lines define Egel code.

```
    .import "regex.ego";;
    .using System;;
    .data branch, leaf;;
    .def author = "Marco Devillers";;
    .val global = ref 3.14;;
```

## Substitution

In the markdown document, all expressions that are surrounded by double
curly braces are evaluated.

```
    This document is written by {{author}} who declares that the 
    factorial of 5 is {{fac 5}}.
```

## Hooks

Hooks can be defined and are run after the initial processing of the
document. They take the Markdown file as a list of lines and should
output a list of lines.

```
    .hook (map [L -> L + "!"]);;
```
