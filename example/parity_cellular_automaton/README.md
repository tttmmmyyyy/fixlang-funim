# Parity Cellular Automaton

## Overview

This is an implementation of a type of cellular automaton.
The characteristic feature is that the rules differ between odd cells and even cells.
However, the rules for odd cells and even cells are related by a 45-degree rotation.

Cells that can be referenced by odd cells (center is itself, ■ are referenceable cells)
```
■ ■ □
■ ■ ■
□ ■ ■
```

Cells that can be referenced by even cells (center is itself, ■ are referenceable cells)
```
□ ■ ■
■ ■ ■
■ ■ □
```

## How to Run

- Install [Fix programming language](https://github.com/tttmmmyyyy/fixlang).
- Install Cairo, X11, Xext (XQuartz on MacOS). [Reference](https://github.com/tttmmmyyyy/fixlang-cairo)
- Run `fix run` in this folder.