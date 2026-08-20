#### This chapter explains the meaning of the elements of expressions in Python

**Syntax Notes:** In this and the following chapters, grammar notation will be used to describe syntax, not lexical analysis.

When(one alternative of) a syntax rule has the form:
    name: othername
and no semantics are given, the semantics of this form of _name_ are the same as for _othername_.

### Arithmetic conversions

When a description of an arithmetic operator below used the phrase "the numeric arguments are converted to a common real type", this means that the operator implementation for buil-in numeric types works as described in the _Numeric Types_ section of the standard library documentation.

Some additional rules apply for certain operators and non-numeric operands (for example, a string as a left argument to the % operator).

Extensions must define their own conversion behavior.

### Atoms

**Atoms are the most basic elements of expressions.** The simplest atoms are _names_ or literals. Forms enclosed in parenthesis, brackets or braces are also categorized syntactically as atoms.

#### Built-in constants

The keywords _True, False,_ and _None_ name built-in constants. The token ... names the Ellipsis constant.

Evaluation of these atoms yields the corresponding value.

Note: In particular these _keywords_ cannot be used as names.

#### Identifiers (Names)

An identifier occuring as an atom is a name.

When the name is bound to an object, evaluation of the atom yields that object. When a name is not bound, an attempt to evaluate it raises a _NameError_ exception.

#### Private name mangling

