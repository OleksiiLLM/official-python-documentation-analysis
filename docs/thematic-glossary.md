# Thematic Glossary

##  **_Source Characters_**

**_Space_**: Is the source character categorized by the Lexical Analazyer as **_Whitespace_**

**_Tab_**: Is the source character categorized by the Lexical Analyzer as **_Whitespace_**

**_Formfeed_**: Is the source character categorized by the Lexical Analyzer as **_Whitespace_**

**_Blank column_**: Blank column is an invisible keystroke character, represented by space

Think of Space/Tab/Formfeed source characters as a physical blank space between words in a book.

The difference between them are in the amount of invisible keystroke spaces they are taking on the physical code line.

The least amount of blank space can be taken is represented by _space_ and it is a single blank column. _Tab_ is source code character that is taking four blank columns, and _formfeed_ is a historical charcter that **used to tell** printers to eject a page.

**_Literal_**: is data given directly to the computer. It is a value written _literally_ exactly as it is meant to be interpreted.

**_Raw Data_**: Is data in the specific context of syntax, that holds it's form, without the need of any extra steps to evaluate it.

Example: x = 10; 10 here is a raw data, becouse python engine does not need to do anything to evaluate it, in contrast to this expression x = 5 + 5; where Python engine, would need to evaluate the variable value, before getting an expression result.

**_Hard-Coded Data_**: Is the data, explicitly typed to the variable. Such as: tax_rate = 0.05

**_Not Hard-Coded Data(Dynamic)_**: In the contrast to the Hard-Coded Data, Dynamic Data (Not-Hard Coded) is not directly stated into the variable, but being pulled over from somewhere, like from the database and will be dynamically updated, without explicit change of it. Example: tax_rate = get_tax_rate_from_database()