# Regular Expressions - Programming with text


Regular expression is a **search pattern**. Regular expressions are extremely useful in extracting information from text such as code, log files, spreadsheets, or even documents.

The first thing to recognize when using regular expressions is that **everything is essentially a character**, and we are writing patterns to match a specific sequence of characters (also known as a **string**). 

**Literal characters vs meta-characters**: Characters in RegEx are understood to be either a **metacharacter with a special meaning** or a regular character with a literal meaning. Example `\d` represents a single digit (0-9) whereas "d" represents the english alphabet d.

**Wildcard character**: `.` is a wildcard character => any character expect new line (`\n`). This can be very useful when we are looking for a pattern, not the exact contents of it. This character is so common that, in order to match a period character we need to use `\.`

**Matching specific characters**: We can use **character class or character set** to match one out of several characters. [abc] => (a | b | c)

**Excluding specific characters**: [^ab] means neither a nor b. 

**Character ranges**: Shorthand for matching a character in list of **sequential characters** by using the **dash** to indicate a character range. [A-Za-z0-9_] represents \w (alphanumeric or word character)

**Quantifiers in Regular Expressions**: How many instances.
1. `*` => Zero or more times (Kleene star)
2. `+` => One or more times (kleene plus)
3. `?` => Zero or one time
4. `{n}` => Match exactly n times
5. `{m,}` => Match atleast m times
6. `{m, n}` => more than "m" and less than "n"

The standard quantifiers in regular expressions are **greedy**, meaning they match as much as they can, only giving back as necessary to match the remainder of the regex.

By using a **lazy** quantifier, the expression tries the minimal match first.

**White space** => `\s`

**Starting and ending** => `^` and `$`

## Resources
1. Introductory reading material - [link](https://regexone.com/)
2. Exercises - [link](https://www.hackerrank.com/domains/regex)