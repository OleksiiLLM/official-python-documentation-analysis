# Execution model

## 4.1 Structure of a program

A Python program is constructed from code blocks. A _block_ is a piece of Python program text that is exectured as a unit. The following are blocks: a module, a function body, and a class definition.

Each command typed interactively is a block.

A script file (a file given as standard input to the interpreter or specified as a command line argument to the interpreter) is a code block.

A script command (a command specified on the interpreter command line with the _-c_ option) is a code block.

A module run as a top level script (as module __main__) from the command line using a -m argument is also a code block. The string argument passed to the built-in functions eval() and exec() is a code block.

A code blokc is executed in an execution frame. A frame contains some administrative information (used for debugging) and determines where and how execution continues after the code block's execution has completed.

## Naming and binding

### 4.2.1. Binding of names

Names refer to objects. Names are introduced by name binding operations.

The following constucts bind names:

* formal parameters to functions