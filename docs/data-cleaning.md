## Padding and Stripping
[str.strip](https://docs.python.org/3.14/library/stdtypes.html#str.strip)(chars=None, /)
***
Return a copy of the string with the leading and trailing characters removed. The chars argument is a string specifying the set of characters to be removed. If omitted or None, the chars argument defaults to removing whitespace. The chars argument is not a prefix or suffix; rather, all combinations of its values are stripped.
***
### Analysis
**Return a copy of the string** - means that we are not changing the string itself, but creating a copy of it with a method input.

**Leading and Trailing Characters** - In Python, leading and trailing characters refer to the characters located at the absolute beginning and the absolute end of a piece of text(a string). They do not include any characters that appear inside the middle of the text.

**If ommitted or None** - ommitted means left out, skipped, or not provided.

**The char argument is not a prefix or suffix** - a prefix is a sequence of characters at the very beginning of a string, while a suffix is a sequence of characters at the very end.

**Stripped** - stripped means that unwanted characters were removed from the edges of a string.

### Example
    >>> '    spacious   '.strip()
    'spacious'
    >>> 'www.example.com'.strip('cmowz.')
    'example'

The outermost leading and trailing chars argument values are stripped from the string. Characters are removed from the leading end until reaching a string character that is not contained in the set of characters in chars. A similar action takes place on the trailing end.

### Example
    >>> comment_string = '#....... Section 3.2.1 Issue #32 .......'
    >>> comment_string.strip('.#! ')
    'Section 3.2.1 Issue #32'

[str.lstrip](https://docs.python.org/3.14/library/stdtypes.html#str.lstrip)(chars=None, /)
***
Return a copy of the string with leading characters removed. The chars argument is a string specifying the set of characters to be removed. If omitted or None, the chars argument defaults to removing whitespace. The chars argument is not a prefix; rather, all combinations of its values are stripped
### Example
    >>>'   spacious   '.lstrip()
    'spacious   '
    >>>'www.example.com'.lstrip('cmowz.')
    'example.com'

[str.rstrip](https://docs.python.org/3.14/library/stdtypes.html#str.rstrip)(chars=None, /)
***
Return a copy of the string with trailing characters removed. The chars argument is a string specifying the set of characters to be removed. If omitted or None, the chars argument defaults to removing whitespace. The chars argument is not a suffix; rather, all combinations of its values are stripped.
### Example
    >>> '   spacious   '.rstrip()
    '    spacious'
    >>>'mississippi'.rstrip('ipz')
    'mississ'
***
[str.removeprefix](https://docs.python.org/3.14/library/stdtypes.html#str.removeprefix)(prefix, /)
***
If the string starts with the prefix that were inputed by argument,it will return string, without this argument. Otherwise it return a copy of the original string
### Example
    >>> 'TestHook'.removeprefix('Test')
    'Hook'
    >>> 'BaseTestCase'.removeprefix('Test')
    'BaseTestCase'
[str.removesuffix](https://docs.python.org/3.14/library/stdtypes.html#str.removesuffix)(suffix, /)
If the string ends with the suffix that were inputed by argument,it will return string, without this argument. Otherwise it return a copy of the original string
### Example
    >>>'MiscTests'.removesuffix('Tests')
    'Misc'
    >>>'TmpDirMixin'.removesuffix('Tests')
    'TmpDirMixin'
***
[str.center](https://docs.python.org/3.14/library/stdtypes.html#str.center)(width, fillchar=' ', /)
Return centered in a string of length width, which means that you give Python a target number (the width), and python creates a brand new string that has exactly that many characters in it. It takes your original word and drops it right in the dead center of that new string.

**Padding** - This is the programming term for "stuffing" or "filling the empty space."
**Fillchar** (Fill Character): This is the exact character you are telling Python to use as the padding, it can be a dash(-), an asterisk(*), or any other single character you want.
**ASCII space**: "ASCII" is just the standard character encoding for computers. An "ASCII space" is literally just a regular, invisible space.

### Example
    'Python'.center(10)
    Returns: '  Python  '
What happened: The word 'Python' has 6 characters. You asked for a total width of 10. Python needs to add 4 characters of padding(2 on the left, 2 on the right) to reach a total of 10. Becouse you didn't specify a fillchar, it used the default ASCII space. 
***
### Example 2: A Custom Fillchar
    'Python'.center(10, '-')
    Returns: '--Python--'
What happened: Exactly the same math as above, but this time you explicitly provided '-' as the fillchar. Python used dashes as the padding instead of blank spaces.
### Example 3: Width is too small
    'Python'.center(4)
    Returns: 'Python'
What happened: Your original word 'Python' is 6 characters long. You asked Python to center it in a space that is only 4 characters wide. Becouse the box is smaller than the item itself, Python just gives up and returns your original 6-characters word untouched. It will never chop off your letters to make it fit.
***
[str.ljust](https://docs.python.org/3.14/library/stdtypes.html#str.ljust)(width, fillchar=' ', /)
Return the string left justified in a string of length width. Padding is done using the specified fillchar. The original string is returned if width is less than or equal to initial length of a string.
***
### Example 
    >>> 'Python'.ljust(10)
    'Python     '
    >>> 'Python'.ljust(10, '.')
    'Python....'
    >>> 'Monty Python'.ljust(10, '.')
    'Monty Python'
***
[str.rjust](https://docs.python.org/3.14/library/stdtypes.html#str.rjust)(width, fillchar=' ', /)
Return the string right justified in a string of length width. Padding is done using the specified fillchar. The original string is returned if width is less than or equal to initial length of a string.
### Example 
    >>> 'Python'.rjust(10)
    '    Python'
    >>> 'Python'.rjust(10, '.')
    '....Python'
    >>> 'Monty Python'.rjust(10, '.')
    'Monty Python'
***
## Case Manipulation
[str.lower](https://docs.python.org/3.14/library/stdtypes.html#str.lower)()
Return a copy of the string with all the cased characters converted to lowercase.

**Cased Character** - a cased character is one that can assume multiple cases: "a" is a cased character becouse it can take on an uppercae variat"A" and vice versa. On the other hand, "1" is *uncased* becouse it has no other possible cases to take on.
### Example
    >>> "Lower Method Example".lower()
    'lower method example'
***
[str.upper](https://docs.python.org/3.14/library/stdtypes.html#str.upper)()
Return a copy of the string with all the cased characters converted to uppercase.
***
### Example
    >>> "Python".upper()
    "PYTHON"
***
[str.casefold](https://docs.python.org/3.14/library/stdtypes.html#str.casefold)()
Return a casefold copy of the string.
**Casefolding Method** is similar to lower() method, but more agressive becouse it is intended to remove all case distinctions in a string. For example, the German lowercase letter 'B' is equivalent to "ss". Since it is already lowercase, lower() would do nothing to "B"; casefold() converts it to "ss".
### Example
    >>> 'straBe'.lower()
    'straBe'
    >>> 'straBe'.casefold()
    'strasse'
So, the casefold will change the letter to lowercase in other languages.
***
[str.capitalize](https://docs.python.org/3.14/library/stdtypes.html#str.capitalize)()
Return a copy of the string with its first character capitalized and the rest lowercased.
[str.title](https://docs.python.org/3.14/library/stdtypes.html#str.title)()
Return a titlecased version of the string where words start with an uppercase character and the remaining characters are lowercase.
***
### Example
    >>> 'Hello world'.title()
    'Hello World'
But beware of:
    >>> "they're bill's friends from the UK".title()
    "They'Re Bill'S Friends From The UK"
***
[str.swapcase](https://docs.python.org/3.14/library/stdtypes.html#str.swapcase)()
Return a copy of the string with uppercase characters converted to lowercase and vice versa.
### Example
    >>> 'Hello World'.swapcase()
        'hELLO wORLD'
### String Classification
[str.isprintable()](https://docs.python.org/3/library/stdtypes.html#str.isprintable)

Return True if all characters in the string are printable, False if it contains at least one non-printable character.

The printable characters are those which in the Unicode character database. [unicodedata](https://docs.python.org/3/library/unicodedata.html#module-unicodedata)
### Example
    >>> ''.isprintable(), ' '.isprintable()
    (True, True)
    >>> '\t'.isprintable(), '\n'.isprintable()
    (False, False)
***
[str.isspace()](https://docs.python.org/3/library/stdtypes.html#str.isspace)

Return True of there are only whitespace characters in the string and there is at least one character, False otherwise.

### Example 
    >>> ''.isspace()
    False
    >>> ' '.isspace()
    True
    >>>'\t\n'.isspace()
    True
    >>> '\u3000'.isspace()
    True
[str.istitle()](https://docs.python.org/3/library/stdtypes.html#str.istitle)

[str.isupper()](https://docs.python.org/3/library/stdtypes.html#str.isupper)

[str.islower()](https://docs.python.org/3/library/stdtypes.html#str.islower)

[str.isidentifier()](https://docs.python.org/3/library/stdtypes.html#str.isidentifier)

Return True if the string is a valid identifier according to the language definition

### Example 
    >>> 'hello'.isidentifier()
    True
    >>> 'def'.isidentifier()
    True
