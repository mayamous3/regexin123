
# Regex in 1-2-3 

Regex is short for Regular Expression and can be used to extract data from strings, validate input, and replace text.

This is a tutorial that uses a regex pattern for validating URLs as an example to understand how these expressions are crafted.

## Summary

Regex is a useful way to find, match, and manipulate patterns in text. It seeks to find the right combination of characters that fit a certain pattern.

Regex can be used by programmers and data analysts to sort through and interpet heaps of information. It allows them to extract specific data from strings, validate input, and replace portions of text.

The following regex pattern can be used to validate whether a given URL is a valid one.
 
* `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

In this tutorial, I will describe the regex components that make up this pattern, as well as some 

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

The regex pattern for validating URLs (in summary above, and listed again below) can be broken down into the following components, which are also defined in the subsequent sections. 
* `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

1. '^' : Caret symbol marks the start of the string, ensuring that the pattern will match from beginning to end.
2. '(https?:\/\/)?' : Optional group captures both http:// and https:// .
3. '([\da-z\.-]+)' : Matches a combination of lowercase letters, digits, periods, and hyphens that make up a domain name.
4. '\.([a-z\.]{2,6})' : Allows 2-6 lower case letters or periods to represent the top level domain.
5. '([\/\w \.-]*)*' : Captures any path that could come after the domain. Includes slashes, word characters, spaces, periods, and hyphens, and the asterisk * means that this group can appear zero or more times.
6. '\/?' : Indicates that URL can be closed with an optional forward slash.
7. '$' : Marks the end of the string.

### Anchors
Anchors help find specific positions within a string. There are two main anchor types (both which are used in our example).

* ^ : The caret symbol represents the start of a line or a string. It indicates that the pattern attached to it needs to exist at the beginning of the string. 

We saw in our example that a ^ was placed at the beginning of the pattern indicating that the beginning of the input string would need to meet this criteria: '(https?:\/\/)?' matching the protocol part of a URL.

* $ :  The "dollar sign" represents the ending of a line or string. When the $ is placed at the end of a string, it ensures that the preceding pattern must appear at the end of the input string.

### Quantifiers
Quantifiers are symbols that define how many times a certain character or group of characters should appear in the input string.

A few commonly used quantifiers are:
* '*' (asterisk) : This allows the preceding character or group to appear any number of times, including 0.

In our example, the asterisk quantifier is used at the end of ([\/\w \.-]*), allowing the path and parameters to appear zero or more times, making them optional for the input string.

* '+' (plus sign) : This requires the preceding character or group to appear at least once.

In our example, the plus sign appears at the end of ([\da-z\.-]+), allowing the characters in the domain name to appear one or more times, thereby ensuring that the domain name has at least one character before the period.

* '?' (question mark) : This means that the preceding character or group is optional.

In our example, the question mark is used in (https?:\/\/), and makes the "s" in "https" optional. As a result, "http://" or "https://" are both allowed to be in our input string.

### Grouping Constructs
In Regex there are two types of grouping constructs for grouping together characters that need to be treated as a single unit.

1. () Parenthesis : 

2. (?: ) Non-Capturing Parenthesis : These are used to group characters together without creating a capture group. This grouping construct is not used in our example.

### Bracket Expressions

### Character Classes
Character Classes in Regex are collections of characters that are used to match against any single character within the input string (in our example, the URL)

Character Classes appear as a set of characters inside square brackets [].

Below are a few generic examples of Character Classes:
* [^abc] : not a, b, or c
* [0-9] : any digit from 0-9
* [\d] : shorthand for any digit
* [\w] : shorthand for any word
* [\D] : shorthand for not a digit
* [\W] : shorthand for not a word

You can see that #s 3 and 4 from our example (Described in Regex Components) use character classes.

### The OR Operator

### Flags

### Character Escapes

## Conclusion

To conclude, this regex pattern matches and validates URLs that meet the following criteria:
* With or without a protocol (http or https).
* Has a domain name which consists of lowercase letters, digits, periods, and hyphens.
* Has a top-level domain of 2 to 6 lowercase letters or periods.
* Has an optional path that can include slashes, word characters, spaces, periods, and hyphens.
* Has an optional ending forward slash.

## Author

Amanda Cooper-Ponte
Portfolio:
