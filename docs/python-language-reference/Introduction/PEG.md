# Parsing Expression Grammar (PEG)

Understanding how a computer reads code can definitely feel like trying to decipher an alien language. You are diving into the absolute lowest level of how a programming language operates under the hood!

In the official documentation, Python's grammar rules were historically written in a format called BNF (or EBNF), but the creators recently switched to a slightly different notation system called Parsing Expression Grammar (PEG).

Here is a straightforward, use-case-driven breakdown of what a Parsing Expression Grammar is, how it works, and why Python made the switch.

## 1. What is a Parsing Expression Grammar?

At its core, a PEG is a strict set of mathematical instructions that tells the Python Parser exactly how to group individual words (tokens) into valid structural blocks of code.

Think of it like a highly rigid set of instructions for a factory sorting machine. The machine (the Parser) receives a conveyor belt full of random parts (your code). The PEG is the manual that tells the machine: "If you see a keyword 'if', followed by an expression, followed by a colon, package it into an 'If-Statement' box."

## 2. The Defining Feature: "Ordered Choice"

To truly understand PEG, you have to understand how it differs from traditional grammars (like EBNF). The biggest difference comes down to ambiguity and choice.

In older grammar styles, the "OR" symbol ( | ) is treated as a free-for-all.

The Problem: If a rule says `Rule = Option A | Option B`, and your code happens to match both options, the parser gets confused. It has to guess, and if it guesses wrong, it has to backtrack, which slows the computer down.

PEG eliminates this confusion entirely using a concept called **Ordered Choice**.

The PEG Solution: In PEG, the choices are strictly prioritixed from left to right. It says: "Try to match Option A. If it works, stip immediately and do not even look at Option B. If Option A fails, ONLY then try Option B.

Traditional Grammar: "I will have a cheeseburger or a hamburger."(The waiter is confused because a cheeseburger is a type of hamburger. Which one do you actually want?).

PEG:"Check if you have cheese. If you do, give me a cheeseburger and stop listening to me. If you do not have cheese, give me a hamburger." There is zero ambiguity.

## 3. The Superpower: "Lookahead"

PEG introduces a powerful feature called syntactic lookahead. It uses specific notation to peek at the upcoming code without actually "eating" or processing it yet.

& (And-predicate): This means "Ensure the next thing is X, but don't process it yet."

! (Not-predicate): This means "Ensure the next thing is NOT X, but don't process it yet."

## 4. Why Did Python Switch to PEG?

For decades, Python used a simpler parser (an LL(1) parser based on EBNF). However, as Python evolved, the language became too complex for the old parser to handle efficiently.

The switch to PEG provided three massive benefits for everyday developers:

1. No more "Hacks": The old parser couldn't look ahead, so the core developers had to write messy workarounds in C to make complex features work. PEG handles complex rules naturally.

2. New Features: Advanced structural features, like Python 3.10's match/case statement (Structural Pattern Matching), were practically impossible to build cleanly with the old grammar. PEG made them possible.

3. Better Syntax Errors: Because PEG is so strict and predictable about exactly where a rule fails, modern Python can give you incredibly precise error messages (e.g., "SyntaxError: expected ':'" instead of a generic "Invalid Syntax").

Ultimately, parsing expressions are just the rigid, unambiguous rules that strip away all human interpretation so a machine can reliably turn your text into software.

## More about PEG

While PEG uses mathematical formulas to map out exactly how valid code can be constructed, you can think of it just like reading a strict recipe. Here is your use-case-driven guide to the symbols and syntax of PEG.

## 1. The Basics: Defining a Rule

Every grammar needs a way to declare a rule and specify the exact text required to satisfy it.

### Definition

`=` or `::=` (Definition): This simply means "is defined as". You put the name of your rule on the left, and the exact "ingredients" required to make it on the right.

### Terminal String

`"..."` or `'...'` (Terminal String): This is exact, literal text you must type on your keyboard. The parser stops looking for sub-rules here and just looks for an exact character match.

## Logic: Making Choices

Code rarely goes in just one straight line; you usually have options. This is where PEG flexes its strict rule-set.

`|` or `/` (Ordered Alternation): This symbol means "OR", allowing the code to take one of several valid paths. However, in PEG, this is known as **Ordered Choice**. The choices are strictly prioritized from left to right.

## Quantifiers: Controlling Volume

These symbols dictate exactly how many times an element or ingredient is allowed to appear.

`[ ... ]`(Optional): This means the items inside the brackets can appear zero or one time. It is entirely optional, but you cannot have more than one.

`{ ... }`(Repetition): This means the item can appear zero or more times. It is an infinite loop of optionality.

`( ... )`(Grouping): Just like in standard math, parentheses force the parser to evaluate the items inside together before looking at the rest of rule.

## 4. The PEG Superpower: Lookaheads

Becouse traditional parsers could not look ahead, developers had to write messy workarounds in C to make complex features work. PEG introduces specific syntatic lookahead notation to peek at the upcoming code without actually "eating" or processing it yet.

`&` **(And-predicate):** This means "Ensure the next things is X, but don't process it yet."
`!` **(Not-predicate):** This means "Ensure the next thing is NOT X, but don't process it yet".

By combining these simple symbols, you strip away all human logic and ambiguity, reducing any language down to pure, predictable symbol-matching.