<!-- # Title (replace with your title) -->

# Regex Tutorial | Matching an HTML Tag

<!-- Introductory paragraph (replace this with your text) -->

## Introduction

Regular Expressions, also known as REGEX or REGEXP, are created using a sequence of characters that define a search pattern. By matching patterns in a string a developer can then take the matched string and perform an operation on it. Such as: replace it with another string, or take the matched string and perform a validation on it; insuring that the matched string meets the criteria that has been pre-defined by the developer.

## Summary

<!-- Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary. -->

In this tutorial we'll be taking a look at an expression used to match and HTML Tag: /^<([a-z]+)([^<]+)\*(?:>(.\_)<\/\1>|\s+\/>)$/. We'll break down this REGEX into it's individual components and explain each in detail.

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

Let's start by breaking down the expression /^<([a-z]+)([^<]+)\*(?:>(.\_)<\/\1>|\s+\/>)$/ into it's more basic components to make it a little less intimidating:

- /
  - ^
  - <
  - (
  - [a-z]+
  - )
  - (
  - [^<]+
  - )
  - -
  - (
  - ?:
  - >
  - (
    - .
    - \*
  - )
  - <
  - \ /
  - \1
  - >
  - |
  - \s
  - -
  - \ /
  - >
  - )
  - $
- /

### Anchors

To match HTML Tags this regex uses the anchors: ^, \, and $.

^ (caret) tells the regex what character the pattern should start with. In this case it should start with "<" because we are looking for an HTML Tag and those begin with "<".

The \ (backslash) allows the regex to "escape" certain characters that, without the "\", would otherwise perform an action we don't want the character to perform.
Example: using "." would match EVERY character in a string (even whitespace) while "\." would match only the period. This regex uses it with "\_", "\s", and "\*". With my testing I did not find the escape character to make a difference with an underscore but if it is not used with the star then the regex will throw an error.

The $ (dollar symbol) tells regex what it should find at the end of the pattern. We see this at the end of our regex along with characters contained in () (paranthesis) because this regex is looking for a pattern ending with one of the options listed in the grouping created with ().

### Quantifiers

To match HTML Tags this regex uses the quantifiers: +, ?, and \*.

- (plus symbol) tells the regex to look for one or more of the preceding token. We first see + being used with [a-z] meaning that the regex is to match one or more of the characters ranging from a-z.

? (question mark) normally a ? would inform our regex to match a string containing predifined criteria that is followed by zero or one of the characters preceding the ?.
Example: xyz? would match a string containing xy followed by zero or one z.
However, this ? is used in conjuction with :. These two together create ?: which is used to signal a non-capturing group.

- (asterisk) informs our regex to match 0 or more of the preceding code. We first see \* being used with ([^<]+) making the contents of () optional.
  Example: xyz\* would match a string containing xy followed by zero or more z.

### OR Operator

To match HTML Tags this regex uses the OR Operators: [] and |.

[] (square brackets): matches a string that is followed by one of the characters inside the [] and does so WITHOUT capturing the contents contained within []. We see several examples of this in our regex the first being [a-z].
Example: x[yz] would match xy or xz.

| (vertical bar): is used with () to match a preceding string with one of the contents contained within ()and does so WHILE capturing the contents contained with ().
Example: x(y|z) would match xy or xz.

### Character Classes

To match HTML Tags this regex uses the character classes: \s, and .

\s: matches any whitespace character. We see \s being used in our non capturing group.

. : matches any character except line breaks.

### Flags

A regex start is signaled by / and the end is marked by the same character /. We can include flags after the closing /. These flags include: g for global, m for multi-line, i for case insensitive, y for unicode, and y for sticky.
Example: /Xyz/i would match XYZ.

### Grouping and Capturing

Grouping and Capturing come into play when we want to use regex with our preferred programming language. Grouping and Capturing uses () (paranthesis) to match a specific pattern in a string. We see Grouping and Capturing done in multiple places with our regex: ([a-z]+) and ([^<]+).
Example: /(flavor)/ would match "flavor" while ( a) would match all "a"'s with whitespace preceding it. Specifically for our regex the grouping ([a-z]) would match any character ranging from a-z.

Then theres (?:). This combination ?: tells our regex to disable the capturing group. We see this as (?:>(.\_)<\/\1>|\s+\/>) in our regex.

### Bracket Expressions

[] (square brackets): matches a string that is followed by one of the characters inside the [] and does so WITHOUT capturing the contents contained within []. We see several examples of this in our regex the first being [a-z].
Example: [xyz] is the same as x|y|z.

### Greedy and Lazy Match

The quantifiers ( \* + {} ) are known as greedy operators. They try to match everything they can when given a string. We see the () used with our grouping.
Example: ([a-z]+) will match the following group ([^<]+) with any value from a to z at least once due to the +.

### Boundaries

Boundaries are represented by \b. They are not used in this regex but I'll go over them anyway. Boundaries are placed at the beginning and end of the searich criteria defined by the developer. They can be used in word matching.
Example: \bxyzz\b would match xyzz and NOT xyz, xyyz, or xxyz.

### Back-references

Back-references are used to match text that has been matched by a previous matching group. We see it in our regex with \1. This \1 tells us that it's trying to match the same thing that the first capturing group matched. Our first capture group is ([a-z]+). So \1 is attempting to capture something ranging from a - z.

### Look-ahead and Look-behind

Look-ahead and Look-behing will NOT be part of the overall regex match. It's use is trying to identify a search where you want something ONLY if it's followed or preceded by your pre-defined search criteria.
Example: x(?=y) will match an x ONLY if it's followed by a y.
(?<=y)x will match an x ONLY if it's following a y.

## Author

You can view more of my work at [my github](https://github.com/D-Whipp)
