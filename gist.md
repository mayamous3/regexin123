
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
3. '([\da-z\.-]+)' : Matches a combination of lowercase letters, digits, dots, and hyphens that make up a domain name.
4. '\.([a-z\.]{2,6})' : Allows 2-6 lower case letters or periods to represent the top level domain.
5. '([\/\w \.-]*)*' : Captures any path that could come after the domain. Includes slashes, word characters, spaces, dots, and hyphens, and the asterisk * means that this group can appear zero or more times.
6. '\/?' : Indicates that URL can be closed with an optional forward slash.
7. '$' : Marks the end of the string.

### Anchors
Anchors help find specific positions within a string. There are two main anchor types (both which are used in our example).

* ^ : The caret symbol represents the start of a line or a string. It indicates that the pattern attached to it needs to exist at the beginning of the string. 

We saw in our example that a ^ was placed at the beginning of 

* $ :
### Quantifiers

### Grouping Constructs

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

In summation, this regex pattern matches and validates URLs meeting the following criteria:
* With or without a protocol (http or https).
* A domain name consisting of lowercase letters, digits, dots, and hyphens.
* A top-level domain of 2 to 6 lowercase letters or dots.
* An optional path that can include slashes, word characters, spaces, dots, and hyphens.
* An optional ending forward slash.

## Author

Amanda Cooper-Ponte
Portfolio:
