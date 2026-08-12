# Lexical Analysis in Python (Programming)

In the context of computer science, **_Lexical Analysis_** (often called scanning) is the foundational step of taking raw text and chopping it up into its smallest structural pieces so a computer knows exactly what it is looking at.

Becouse you will often see this term used in two slightly different ways, here is how it breaks down depending on your use-case.

## Lexical Analysis in Python (Programming)

In the official Python Language Reference, lexical analysis is the very first step the Python interpreter takes when reading your code. It does not deal with human language. Instead, it scans your .py file and breaks your code down into "tokens" (like keywords, identifiers, operators, and literals) before it actually tries to execute anything.

    Example: Taking the code x = 5 + 10 and splitting it into IDENTIFIER(x), OPERATOR(=), NUMBER(5), OPERATOR(+), NUMBER(10).

## Lexical Analysis in NLP (Human Language)

In Natural Language Processing (NLP), lexical analysis is the process of taking a stream of human text and diving it into its smallest meaningful units, such as paragraphs, sentences, and individual words (also called tokens). When a computer tries to understand a sentence a human wrote, it has to break that sentence down into these digestible pieces first.

    Example: Taking the sentence "I love Python!" and splitting it into ["I", "Love", "Python", "!"] so the computer can eventually analyze the meaning of each word.

Ultimately, whetever you are dealing with Python's internal interpreter reading code or an AI reading human language, lexical analysis is just the act of scanning and tokenizing raw text.
