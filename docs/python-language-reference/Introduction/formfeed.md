# Formfeed

In the context of Python (and computing in general),a **Formfeed** is an invisible control character - represented in code as the escape sequence _\f_ - originally designed to tell a physical printer to eject the current page and start printing at the top of a new one.

Here is how you will encounter formfeed in Python today:

* **As Whitespace:**Python formally recognizes the formfeed character as whitespace. If you have a string containing a formfeed and run _"f".isspace()_, Python will return _True_.

Ultimately, formfeed is a historical artifact. Unless you are writing Python code to interface with legacy 1980s hardware or parsing very specific, old-school text files, you will almost never intentionally type or use \f in modern everyday programming.