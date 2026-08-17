# Introduction

This reference manual describes the Python programming language. It is not intended as a tutorial.

While I am trying to be as precise as possible, I chose to use English rather than formal specifications for everything except syntax and lexical analysis. This should make the document more understandable to the average reader, but will leave room for ambiguities. Consequently, if you were coming from Mars and tried to re-implement Python from this document alone, you might have to guess things and in fact you would probably end up implementing quite a different language. On the other hand, if you are using Python and wonder what the precise rules about a particular area of the language are, you should definitely be able to find them here. If you would like to see a more formal definition of the language, maybe you could volunteer your time — or invent a cloning machine.

It is dangerous to add too many implementation details to a language reference document — the implementation may change, and other implementations of the same language may work differently. On the other hand, CPython is the one Python implementation in widespread use (although alternate implementations continue to gain support), and its particular quirks are sometimes worth being mentioned, especially where the implementation imposes additional limitations. Therefore, you’ll find short “implementation notes” sprinkled throughout the text.

Every Python implementation comes with a number of built-in and standard modules. These are documented in The Python Standard Library. A few built-in modules are mentioned when they interact in a significant way with the language definition.

## Alternate Implementations

Though there is one Python implementation which is by far the most popular, there are some alternate implementations which are of particular interest to different audiences.

Known implementations include:

**CPython**this is the original and most-maintained implementatin of Python, written in C. New language features generally appear here first.

**Jypthon**is python implemented in Java. This implementation can be used as a scriptiong language for Java applications, or can be used to create applications using the Java class libraries. It is also often used to create tests for Java libraries.

**Python for .NET**implementation actually uses the CPython implementation, but is a managed .NET application and makes .NET libraries available. It was created by Brian Lloyd.

**IronPython**an alternate Python for .NET. Unlike Python.NET, this is a complete Python implementation that generates IL, and compiles Python code directly to .NET assemblies. It was created by Jim Hugunin, the original creator of Jython.

**PyPy**an implementation of Python written completely in Python. It supports several advanced features not found in other implementations like stackless support and a Just in Time compiler. ONe of the goals of the project is to encourage experimentation with the language itself by making it easier to modify the interpreter (since it is written in Python)

Each of these implementations varies in some way from the language as documented in this manual, or introduces specific information beyond what’s covered in the standard Python documentation. Please refer to the implementation-specific documentation to determine what else you need to know about the specific implementation you’re using.

## Notation

The descriptions of lexical analysis and syntax use a grammar notation that is a mixture of EBNF and PEG.

For example:

    name:   letter (letter | digit | "_")*
    letter: "a"..."z" | "A"..."Z"
    digit:  "0"..."9"

In this example, the first line says that a name is a letter followed by a sequence of zero or more letters, digits, and underscores. A letter in turn is any of the single characters 'a' through 'z' and A through Z; a digit is a single character from 0 to 9.