# Grammar Notation Specifics of Python

The official Python documentation actually uses slightly different notation styles depending on what part of the language it is describing.

* The Lexical vs Syntatic Divide: Syntatic notation describes how words group together into valid code blocks (like `if` statements), but Lexical notation describes how individual, raw characters group together to form words.

* The EBNF Mistmach: If this were strict, old-school EBNF, it would use an = for the definition instead of a :. It would also use a comma , to enforce concatenation (followed by) , and it would end the rule with a semicolon ;. Furthermore, strict EBNF uses curly braces { } for repetition, not the asterisk *.

* The Shorthand: The example you provided is a Lexical rule defining a variable name (an identifier). Becouse lexical rules deal with raw characters, the documentation borrows heavily from Regular Expression shorthand. The `:` definition, the `*` for repetition, and the `"a"..."z"` ranges are a highly specific symbolic shorthand meant to be more readable for humans.

## How to Read This Notation

When reading this, you just need to break it down using the logical rules of PEG and Regular Expressions. Let's translate it into plain English, starting from the bottom up:

`digit: "0"..."9"`

Translation: A `digit` is defined as any single character in the range from 0 to 9.

`letter: "a"..."z" | "A"..."Z"`

Translation: A letter is defined as a range of characters from a to z, OR any uppercase character from A to Z.

`name: letter (letter | digit | "_")*`

Translation: A `name` is defined as starting with exactly one `letter`. This is followeb by a grouped set of choices (...).

Inside that group, the next character can be a `letter`, OR `digit`, OR `_`.

The asterisk `*` at the very end means that his entire grouped choice can be repeated zero or more times.

**The Practical Takeaway:**

This mathematical formula is the exact reason why you can name a Python variable my_var1 or just x, but you cannot name a variable 1st_var. The rule strictly dictates that the very first character must be a letter, and only after that first letter are you allowed to use an endless loop of letters, digits, or underscores.

## Structural Symbols (The Bluerpint)

These symobols are used to define the rules and group items together.

`:` or `::=` (Definition): This simplye means "is defined as". YOu put the name of the concept you are defining on the left, and the exact ingredients to make it on the right.

`"..."` or `'...'` (Literal Srting): This represents the exact, literal text you must type on your keyboard. The parser is looking for an exact character match.

`( ... )` (Grouping): Just like in standard math, parentheses force the parser to evaluate the items inside together as a single group before looking at the rest of the rule.

## Logic Symbols (The Choices)

These symbols tell the parser what options it is allowed to accept.

`|` (Alternation): This means "OR". It allows the code to take one of several valid paths.

`"a"..."z"` (Inclusive Range): This is a highly specific shorthand used to represent a range of characters without typing every sinlge one out.

## Quantifier Symbols (The Volume)

These symbols dictate exactly how many times an ingredient is allowed (or required) to appear. They almost always apply to the single character or grouped parentheses ( ) immediately preceding them.

`*` (Asterisk): This means the preceding item can appear zero or more times. It acts as an infinite loop of optionality.

`+` (Plus): This means the preceding item can appear one or more times. (It must appear at least once, but can repeat infinitely).

`[ ... ]` (Optional): This means the items inside the square brackets can appear zero or one time. It is entirely optional, but you cannot have more than one.

