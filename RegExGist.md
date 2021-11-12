# REG_EX Tutorial

This is tutorial will demonstrate the use of Regular Expressions used to Validate emails by Node or Mongo. Here is the specific expression: 

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

---

## Regular Expressions

In short, a regular expression define patterns used to match character combinations in strings, such as emails and phone numbers. This search pattern is used to descibe what you are searching for by matching simple or complex text patterns. It can just be one character or an intricate sequence of characters. Regular expressions can match, replace, search, stubsting, parse and split text, how cool?! It's like using the "find and replace" fucntion we all are use to - CTRL-H, CTRL-F, etc.

Let's take a look at the expression above and decifer it's meaning

--

## Table of Contents
- [Common Symbols](#common-symbols)
- [ANCHORS](#anchors)
- [Quantifiers](#quantifiers)
- [Capture Groups](#capture-group)
- [Bracket Expressions](#bracket-expressions)

---
### Common Symbols

First off, we need to understand what each character means. List here are the most common ones:

-   `.`      Matches any character, except for line breaks if dotall is false.
-   `*`      Matches 0 or more of the preceding character.
-   `+`      Matches 1 or more of the preceding character.
-   `?`      Preceding character is optional. Matches 0 or 1 occurrence.
-   `\`      Matches any single digit
-   `\`      Matches any word character (alphanumeric & underscore).
- `[XYZ]`    Matches any single character from the character class.
- `[XYZ]+`   Matches one or more of any of the characters in the set.
-   `$`      Matches the end of the string.
-   `^`      Matches the beginning of a string.
- `[^a-z]`   When inside of a character class, the ^ means NOT; in this case, match anything that is NOT a lowercase letter.


### Anchors

Anchors are tokens of the expressions that don't match any characters, rather they say something about the operation. They depict a location, such as the beginning and the end of the string. In this expression we see the anchors used to match an email, `^` is the beginning and `$` is the last of the string.

### Capture Group

This caaptures the text matched by the regular expression. In our expressionm, the first group `([a-z0-9_\.-]+)` matches the username. The middle part `([\da-z\.-]+)` mataches the email service, and finally ([a-z\.]{2,6} matches the `.com`/

### Quantifiers

Here we learn about "greedy" and "lazy" quantifiers. Greedy  will match as much as it can and lazy quantifiers will try for the minimal match. In this expression we see the `+` operator. It connets the username to the the `@` symbol then to domain service. 

### Bracket Expressions

A bracket expression is a list of characters enclosed by `[` and `]`. It mataches any single character in that list. if the first character is `^`, then it it matches characters NOT in the list. 

Let us break down the expression above:

We have `[a-z0-9_\.-]` which indicates any letter a-z and is also case sensitive. It also will match numeric characters 0-9, these charactesr as well `_`,`-`, and `.`. 

`[\da-z\.-]` mataches single digit from 0-9, case sensifive; also `_` and `-`

Finally, `[a-z\.]` matches charactesr a-z, case sensitive and the character `.`.




