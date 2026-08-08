On the main page of [Built-in Functions](https://docs.python.org/3/library/functions.html), there mentioned 68 built-in functions(count yourself, if you don't trust me).

The first built-in function is "abs". 
What can I understand from her name, as of python itself was created to be an easy programming language, I would try to understand the logic behind the names of functions.

Going back to abs, what I think it says. ... (add here explanation for data types)

Here we should just remmember the rule that each and any function in python after it's name is following a paranthesis (), abs function is no exception - abs().

abs(number, /)

Let's deeply review the function.

function keyword is abs.
function takes paramaters as number only and Positional-only parameter separator - which is we are taking from forward slash sign "/".

Guestions:

what is function? 
what does number means inside it?
what is forward slash means inside it?

Let's read a function definition:
Return the absolute value of a number. The argument may be an integer, a floating-point number, or an object implementing __abs__(). If the argument is a complex number, its magnitude is returned.

Let's go sentence by sentence.
Return the absolute value of a number.
    It means, that we are ignoring the sign of a number. Couse any number has sign, either positive or negative. and we are specifying only a negative numbers with a sign, while positive numbers sing, is implicit(something is present, but not directly mentioned)so, if the number is +5 the absolute value of it, is = to 5. The same for a negative number, -5 and the absolute value of it is = to 5.

The argument(make it as a link) may be an integer, a floating-point number, or an object implementing __abs__().
    What is __abs__() - it is a method that applies abs() function. 

Let's summarize an argument may be an: integer, floatin-point number, or object implementing __abs__().

If the argument is a complex number, its magnitude is returned - I am not describing it.

What is positional-only parameter separator [PEP 570](https://peps.python.org/pep-0570/)?
Introduction of new syntax "/" - forward slash in function definition. Which is for specifying positional-only parameters in Python function definitions.

Positional-only parameters have no externally-usable name. When a function accepting positional-only parameters is called, positional arguments are mapped to these parameters based solely on their order.

Here we are finished with abs(number, /) built-in function.

aiter(async_iterable, /)
    Return an asynchronous iterator for an asynchronous iterable. Equivalent to calling x.__aiter__().
what is async_iterable ? - full name is asynchronous iterable, is an object that lets you loop over [data items]("data items" often reffered to intechangeably with data types, objects, or elements, represents the classification of values stored in a program) one by one when those items arrive over time.

what is asynchronous iterator ? - an asynchronous iterator is an object that lets you loop through a stream of data where each item might take time to arrive.

all(iterable, /)
    Return True if all elements of the [iterable](Iterable in Python is any object capable of returning its members one at a time, permitting it to be iterable over in a for-loop) are true (or if the iterable is empty).
    asynchronous - means things do not happend at the same time or speed.
    in python asynchronous programming, an awaitable is simply any object that is capable of being used with the await keyword.

awaitable anext(async_iterator, /)
awaitable anext(async_iterator, default, /)
    When awaited, return the next item from the given asynchronous iterator, or default if given and the iterator is exhausted.

    This calls the __anext__() method of async_iterator, returning an awaitable. Awaiting this returns the next value of the iterator. If default is given, it is returned if the iterator is exhausted, otherwise StopAsyncIteration is raised.

any(iterable, /)
    Return True if any element of the iterable is true. If the iterable is empty, return False.

ascii(object, /)
    As repr(), return a string containing a printable representation of an object, but escape the non-ASCII characters in the string returned by repr() using \x, \u, or \U escapes. This generates a string similar to that returned by repr() in Python 2.

bin(integer, /)
    Convert an integer number to a binary string prefixed with “0b”. The result is a valid Python expression. If integer is not a Python int object, it has to define an __index__() method that returns an integer.

class bool(object=False, /)
    Return a Boolean value, i.e. one of True or False.
    The argument is converted using the standard truth testing procedure.
    If the argument is false or [omitted](in programming, ommited means left out, skipped, or not provided. It usually refers to optional function arguments, missing data fields, or code elements like punctuation that a compiler or language rules allow you to skip without causing an error), this returns False; otherwise, it returns True. The bool class is a subclass of int (see Numeric Types — int, float, complex). It cannot be subclassed further. Its only instances are False and True (see Boolean Type - bool).