# Matching a Hex Value

The purpose of this document is to explain the functionality of a matching a hex value. 

## Summary

Some of the expressions you will see in this document are listed below:  `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

We will further explore the details of this specific regular expressions as we talk more about anchors, quantifies, character class, and others that are seen used in this expression. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

Anchors are special characters that match specific positions within a string. In the hex value regex, we use ^. This symbol matches the beginning of the string, and ensures that the hex value we're searching for starts at the very beginning of the text, not in the middle of another word.

Code: `/^#`

### Quantifiers

Quantifiers specify how many times a preceding character or group can be repeated. When it comes to matching hex values, we have two quantifiers:
{6}: This follows the character class [a-f0-9]. It indicates that the preceding character class (any single hex digit) must be matched exactly six times for the full format hex value.
{3}: Similarly, this follows the same character class and requires it to be matched exactly three times for the shorthand format.

Code: `/^#?`

### OR Operator

The pipe symbol (|) acts as a logical OR operator. In our regex, it separates the two alternatives within the capture group. The regex engine will try to match either the pattern before the OR ([a-f0-9]{6}) or the pattern after ([a-f0-9]{3}). This allows the regex to be flexible and handle both full and shorthand hex value formats.

Code: `[a-f0-9]{6}|[a-f0-9]{3}`

### Character Classes

Square brackets define a character class, specifying a set of characters that can be matched in that specific position. In our case, [a-f0-9] defines a class that includes all lowercase letters from 'a' to 'f', all uppercase letters from 'A' to 'F', and all digits from 0 to 9. This ensures the regex only matches valid hexadecimal digits.

Code: `a-f0-9`

### Grouping and Capturing

Parentheses are used to create groups. These groups can capture a portion of the matched text for later use in your code. In the hex value regex, the parentheses, ( and ), enclose the character classes and quantifiers. This group captures the actual hex value (without the hash symbol) for potential processing or manipulation within your code.

Code: `([a-f0-9]{6}|[a-f0-9]{3})`

### Bracket Expressions

Square brackets [] define character classes. They specify a set of characters that can be matched at a particular point in the regex pattern. In our example, [a-f0-9] is the bracket expression that defines the characters for a single hexadecimal digit.

Code: `[a-f0-9]`

### Greedy and Lazy Match

Matching a hex value uses greedy matching by default. Greedy matching tries to match the longest possible string that fits the pattern. Since quantifiers ({6} and {3}) specify exact lengths, greediness isn't a major factor. However, it's an important concept to understand when dealing with repetitive patterns where greediness might lead to unintended matches.

Code: `[a-f0-9]{3}`

## Author

My name is Kyla Rodriguez. I am a novice developer with a passion for creation and knowledge and would love to continue to work on future projects.

https://github.com/kylaerod
