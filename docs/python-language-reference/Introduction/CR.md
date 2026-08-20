# Carriage Return

CR (Carriage Return): Represented in code as \r

Think of an old mechanical typewriter. When you finished typing a sentence and wanted to start a new one, you had to do two physical actions:

1. Push the heavy metal carriage all the way back to the left side of the paper **(Carriage Return)**.

2. Roll the paper up by one notch so you don't type over the words you just wrote **(Line Feed)**.

**The Lexical Analyzer:** When Python's internal engine reads your .py script, it doesn't see visual line breaks; it scans for these invisible CR and LF characters to mathematically determine exactly where one line of code ends and the next begins.

**Universal Newlines:** Python has a built-in feature to make your life easier. Whether your text file was saved on Windows using CRLF, or on a Mac using LF, the lexical analyzer recognizes all of them simply as a standard "New line." This ensures your code doesn't suddenly break just because you emailed it to a friend using a different computer.

Ultimately, CR and LF are just the digital, invisible keystrokes for hitting the "Enter" or "Return" key on your keyboard.