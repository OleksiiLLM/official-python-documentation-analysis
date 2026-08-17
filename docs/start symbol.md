# Start Symbol

A formal grammar is a set of rules for rewriting strings, along with a "start symbol" from which rewriting starts.

Therefore, a grammar is usually thought of as a language generator. However, it can also be used as the basis for a parser - a functin in computing that determines whether a given string belongs to the language or is grammatically incorect.

In the context of Python (and formal grammar definitions), the **Start Symbol** is the single, highest-level "production rule" in the language. It represents the ultimate finish line for the Parser.

Think of it like building a massive Lego set. You have individual pieces (tokens), and you use instructions to combine them into chunks like a "door" or a "roof" (production rules). But the Start Symbol is the picture on the front of the box—it is the final, complete "House." If you have leftover pieces that don't fit into the "House," you did it wrong.

When Python reads your code, it tries to match everything you wrote against this one master rule. If it successfully collapses all your text into the start symbol, the code is valid. If it fails, you get a SyntaxError.

## Examples in Python

Interestingly, Python uses a few different start symbols depending on exactly how you are running your code:

file (or module): This is the start symbol used when you run a normal .py script (e.g., python script.py). In the grammar rulebook, this symbol essentially says: "A valid program is simply a list of zero or more statements, ending with an End-Of-File marker."

interactive: This is the start symbol used when you open your terminal and type directly into the Python REPL. Because it only evaluates one line at a time, this rule expects just a single statement followed by a newline, rather than a whole file.

eval: If you use Python's built-in eval() function (which evaluates mathematical strings like eval("5 + 10")), the parser uses this specific start symbol. It strictly expects an expression (something that produces a value) and will throw an error if you try to pass it a full statement like an if block.

Ultimately, the start symbol is the top of the pyramid. Every single valid keyword, string, function, and class you write must eventually roll up into this one ultimate structural rule.