<!-- # Title (replace with your title) -->

# Regex Tutorial | Matching an HTML Tag

<!-- Introductory paragraph (replace this with your text) -->

Regular Expressions, also known as REGEX or REGEXP, are created using a sequence of characters that define a search pattern. By matching patterns in a string a developer can then take the matched string and perform an operation on it. Such as: replace it with another string, or take the matched string and perform a validation on it; insuring that the matched string meets the criteria that has been pre-defined by the developer.

## Summary

<!-- Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary. -->

In this tutorial we'll be taking a look at an expression used to match and HTML Tag: /^<([a-z]+)([^<]+)_(?:>(._)<\/\1>|\s+\/>)$/. We'll break down this REGEX into it's individual components and explain each in detail.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

Let's start by breaking down the expression /^<([a-z]+)([^<]+)_(?:>(._)<\/\1>|\s+\/>)$/ into it's more basic components to make it a little less intimidating:

^
<
([a-z]+)
([^<]+)

\_(?:>(.\*)<\/\1>|\s+\/>)$

### Anchors

Anchors:

- ^ - This anchor matches the START of the string with the pattern it is attached to.
  - Example: ^R identifies the first "R" at the start of a string.
- $ - This anchor matches the END of the string with the pattern it is attached to.
- \A - This anchor
- \G - This anchor
- \Z - This anchor
- \` - This anchor

Anchors used in this Regular Expression: ^

### Quantifiers

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
