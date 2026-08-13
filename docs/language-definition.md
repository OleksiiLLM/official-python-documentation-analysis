# Language Definition

In the context of Python, the **Language Definition** refers to the absolute, theoretical rules that outline exactly what Python is and how it must behave, regardless of the specific software running it.

Think of it as the constitutional law of Python. It does not care about the extra tools or built-in libraries (like _math_ or _json_) you have access to. It solely focuses on two foundational pillars:

1. **Syntax:** How you are legally allowed to spell, structure, and format your code.

2. **Core Semantics:** What that code actually means and what happens to the computer's memory when it executes a specific command (for example, the exact order of operations when eveluating an expression).

In the official ecosystem, the language definition is documented in the **Python Language Reference.** This document acts as the ultimate source of truth.

Ultimately, the language definition separates the idea and rules of Python from the actual software installed on your computer. If a specific Python engine (like the default CPython or an alternative like PyPy) executes code in a way that violates this definition, it is considered a bug in the engine, not a bug in the language itself.