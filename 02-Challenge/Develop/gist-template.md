# Regex Tutorial

In this readme I will explain the components of regex, short for regular expressions. These expressions are used to match character combinations in strings. This is useful for verifying all qualities have been met for certain form inputs. For example, emails, usernames, and passwords.

## Summary

This is an example of regex, matching the valid input of an email address:

```md
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
```

I will be explaining the various components of this input, which at first glance looks like a highly randomized collection of characters. However, it is a faily intuitive template to verify the validity of an email, making sure it follows the correct format.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

A regex **Anchor** are characters within the regex that represent positions within the string. An example would be the characters **^** and **$** matching the beginning and ending of a string, respectively.

Another example would be the use of boundaries, with **\b** representing a word boundary and **\B** representing a non-word boundary. Word boundaries match the position between a word character, a letter, digit, or underscore, and a non word character. Non-word boundaries are the opposite, matching position between two word characters.

### Quantifiers

A **Quantifier** in regex are characters that specify how many times a character or group of characters should occur in a string. Simple examples would be **"*"** and **+**. * representing a character zero or more times, and + matching a character 0ne or more times. A **?** is the same as * but makes the characters optional. Putting a number in curly brackets like {n} will match a character matching that number exactly. Adding a comma after the number means the character will have to match at least that many times. Finally, adding an **m** after the comma will set limit to how many times that chracter can occur. 

### Grouping Constructs

Grouping constructs allow you to create suexpressikns in your pattern that can be treated as a single unit subject to quantifiers, capturing, and logical grouping. () captures groups within it. Modifiers like ?: or ?= within the parentheses can group chracters differently. ?: will group chracters together without capturing the whole group. 

Example: 

```md
/(?:re)?run/
```
This will match "run" or "rerun" but only captures run.

### Bracket Expressions

Brackets are very useful for grouping chracters and specifying needs and limits within regex. [] will match any characters within the brackets, and a dash - can be used to specify ranges. For example, [a-z] would match every letter in the alphabet, and [0-9] would match all numeric characters. Adding a ^ will match anything **not** included in the brackets. [^a-z] would exclude the alphabet.

### Character Classes

Character classes can be used in lieu of certain bracket expressions when it comes to comprehensive ranges. \d can be used to match any numeric character, equivalent to [0-9]. Alternatively, \D would be the equivalent of adding a ^, excluding numbers. \w matches and letter, digit, or underscore. \W follows the same opposite logic.

### The OR Operator

the OR operator is represented with a pipe **|**. It simply matches an either or on either side of the pipe. **cat|dog** would match either cat or dog.

### Flags

**Flags** are modifiers that change how the regex engine will interpret the pattern. They are usually added after the closing character of a string (the **/**). **i** specifies case insensitivity, **g** (standing for global) searches for matches throughout the whole string rather then stopping after the first match. A comprehensive list of flags can be found within the regex documentation.

### Character Escapes

**Character escapes** in regex allow for matching specific characters or represent special characters without their usual interpretation. They are denoted by a backslash **" \ "** followed by a character that has a special meaning in the regex syntax. There is some crossover with character classes!

## Author

Written by James Bruckner

Github: github.com/jamesbruckner
