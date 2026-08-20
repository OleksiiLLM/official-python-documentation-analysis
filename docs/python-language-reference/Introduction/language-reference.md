## Data Model

### Object, values and types

Objects are Python’s abstraction for data. All data in a Python program is represented by objects or by relations between objects. Even code is represented by objects.

**Every object has an identity, a type and a value.**

An object’s identity never changes once it has been created; you may think of it as the object’s address in memory.

An object’s type determines the operations that the object supports, and also defines the possible values for objects of that type.

The value of some objects can change. Objects whose value can change are said to be **mutable**.

Objects whose value is unchangeable once they are created are called **immutable**.

**Note:**The value of an immutable container object that contains a reference to a mutable object can change.

However the container is still considered immutable, because the collection of objects it contains cannot be changed.

Immutability is not strictly the same as having an unchangeable value, it is more [subtle](something is not obvious).

**An object’s mutability is determined by its type.**

Numbers, strings and tuples are immutable.

Dictionaries and lists are mutable.
***
Objects are never explicitly destroyed. However, when they become unreachable they may be [garbage-collected](an automatic memory management feature in computer programming that finds and deletes objects no longer used by a program, freeing up space and preventing memory leaks).

An implementation is allowed to [postpone](to delay an event, meeting, or task and arrange for it to happen at a later time or date) garbage collection or omit it altogether — it is a matter of implementation how garbage collection is implemented, as long as no objects are collected that are still reachable.

**CPython implementation detail:** CPython currently uses a [reference-counting scheme](At its core, reference counting involves keeping track of the number of references (or pointers) to an object in memory. Each time a new reference to an object is created, Python increases that object's reference count. Conversely, when a reference is removed or goes out of scope, Python decreases the reference count.) with (optional) delayed detection of [cyclically linked garbage], which collects most objects as soon as they become unreachable, but is not guaranteed to collect garbage containing circular references.

Some objects contain references to other objects; these are called **containers.**

Examples of containers are tuples, lists and dictionaries.

The references are part of a container’s value

In most cases, when we talk about the value of a container, we imply the values, not the identities of the contained objects.

However, when we talk about the mutability of a container, only the identities of the [immediately contained objects]( in Python is any object directly referenced by a container (such as a list, tuple, or dictionary) rather than being nested deeper inside child objects.) are implied.

For immutable types, operations that compute new values may actually return a reference to any existing object with the same type and value.

For mutable objects this is not allowed.

### The standard type hierarchy

Below is a list of the types that are built into Python. Extension modules (written in C, Java, or other languages, depending on the implementation) can define additional types. Future versions of Python may add types to the type hierarchy.

#### None 

**This type has a single value.**

**There is a single object with this value.**

**This object is accessed throught the buil-in name None.**

It is used to signify the absence of a value in many situations.
Its truth value is false.

#### NotImplemented

**This type has a single value. There is a single object with this value.**

This object is accessed through the built-in name **NotImplemented**.

Numeric methods should return this value if they do not implement the operation for the [operands](An operand is a value, variable, or data input that an operator acts upon in a math equation or computer program) provided.

#### Ellipsis

**This type has a single value. There is a single object with this value.**

This object is accessed through the literal ... or the built-in name Ellipsis. Its truth value is true.

**What is Ellipsis used for in Python?** - Primarly used as a placeholder.

#### numbers.Number

These are created by numeric literals and returned as results by arithmetic operators and arithmetic built-in functions. Numeric objects are immutable; once created their value never changes. Python numbers are of course strongly related to mathematical numbers, but subject to the limitations of numerical representation in computers.

**Python distinguishes between integers, floating-point numbers, and complex numbers**

#### numbers.Integral

These represent elements from the mathematical set of integers (positive and negative)

##### There are two types of integers

###### Integers(int)

These represent numbers in an unlimited range, subject to available (virtual) memory only.

For the purpose of [shift and mask operations](shift and mask operations are bitwise operations used to manipulate the individual binary bits (1s and 0s) of integers), a binary representation is assumed.

###### Booleans (bool)

These represent the truth values False and True. The two objects representing the values False and True are the only Boolean objects.

The Boolean type is a subtype of the integer type, and Boolean values behave like the values 0 and 1, respectively.

In almost all contexts, the exception being that when converted to a string, the stringss "False" or "True" are returned, respectively.

###### numbers.Real (float)

These represent machine-level [double precision floating-point numbers](). You are at the mercy of the underlying machine architecture (and C or Java implementation) for the accepted range and handling of overflow. Python does not support single-precision floating-point numbers; the savings in processor and memory usage that are usually the reason for using these are dwarfed by the overhead of using objects in Python, so there is no reason to complicate the language with two kinds of floating-point numbers.

###### numbers.Complex (complex)

These represent complex numbers as a pair of machine-level double precision floating-point numbers. The same caveats apply as for floating-point numbers. The real and imaginary parts of a complex number z can be retrieve through the read-only attributes z.real and z.imag.

###### Sequences

These represent finite ordered sets indexed by non-negative numbers. The built-in function len() returns the number of items of a sequence. When the length of a sequence is n, the index set contains the numbers 0, 1, ..., n-1. 

Some sequences, including built-in sequences, interpret negative subscripts by adding the sequence length.

**Sequences also support slicing**

If start is missing or None, slicing behaves as if start was zero. If stop is missing or None, slicing behaves as if stop was equal to the length of the sequence.

Some sequences also support "extended slicing" with a third "step" parameter called step.

###### Sequences are distinguished according to their mutability

###### Immutable sequences

An object of an immutable sequence type cannot once it is created. (If the object contains references to other objects, these other objects may be mutable and may be changed; however, the collection of objects directly referenced by an immutable object cannot change.)

###### **The following types are immutable sequences:**

**Strings:** A string(str) is a sequence of values that represent characters, or more formally, _Unicode code points_.

All the code points in the range 0 to 0x10FFFF can be represented in a string.

Python doesn't have a dedicated character type. Instead, every code point in the string is represented as a string object with length 1.

**Tuples:** The items of a tuple() are arbitrary Python objects. Tuples of two or more items are formed by comma-separated lists of expressions. A tuple of one item (a 'sinleton') can be formed by affixing a comma to an expression (an expression by itself does not create a tuple, since parentheses must be usable for grouping of expressions). An empty tuple can be formated by an empty pair of parentheses.

**Bytes:** A byte object is an immutable array. The items are 8-bit bytes, represented by integers in the range 0 <= x < 256. 

###### Mutable sequences

Mutable sequences can be changed after they are created. The subscription and slicing notations can be used as the target of assignemtn and del(delete) statements.

There are currently **two** [intrinsic](means belonging to the basic and essential nature of a thing, it describes a quality, value, or feature that comes from deep inside an object or person rather than from outside sources) mutable sequence types:

**Lists** - The items of a list are arbitrary Python objects. Lists are formed by placing a comma-separated list of expressions in square brackets. (Note that there are no special cases needed to form lists of length 0 or 1.)

**Byte Arrays** - A bytearray object is a mutable array. They are created by the built-in bytearray() constructor. Aside from being mutable (and hence unhashable), byte arrays otherwise provide the same interface and functionality as immutable bytes objects.

###### Set types

**These represent unordered, finite sets of unigue, immutable objects.** As such, they cannot be indexed by any subscript. However, they can be iterated over, and the built-in function len() returns the number of items in a set. Commong uses for sets are fast membership testing, removing duplicates from a sequence, and computing mathematical operations such as intersection, union, difference, and symmetric difference.

For set elements, the same immutability rules apply as for dictionary keys. Note that numeric types obey the normal rules for numeric comparison: if two numbers compare equal, only one of them can be contained in a set.

There are currently tow intrinsic set types:

**Sets:** These represent a mutable set. They are created by the built-in set() constructor and can be modified afterwards by several methods, such as add().

**Frozen Sets:** These represent an immutable set. They are created by the built-in frozenset() constructor. As a frozenset is immutable and hashable, it can be used again as an element of another set, or as a dictionary key.

###### Mappings

These represent finite sets of objects indexed by arbitrary index sets.