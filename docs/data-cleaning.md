# Data Cleaning: Messy User Input
## The Common Scenario
A user fills out a web form for their email address or username, and they accidentally hit the spacebar before or after typing. If you try to save that or check it against a database, " user@email.com " will fail to match "user@email.com".
---
### The Solution: 'str.strip()'

> (chars=None, /)
>
> Return a copy of the string with the leading and trailing characters removed. The chars argument is a string specifying the set of characters to be removed. If omitted or None, the chars argument defaults to removing whitespace. The chars argument is not a prefix or suffix; rather, all combinations of its values are stripped.