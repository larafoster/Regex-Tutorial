# Title Regex-Tutorial

This is a tutorial on how Regex is used to validate an email. 

## Summary

`/\b[\w.!#$%&’*+\/=?^'{|}~-]+@[\w-]+(?:\.[\w-]+)*\b/my` is the ECMAScript syntax that I will be demonstrating. 
This expression checks for a valid email based on the paramters set in the regular expression. 

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
- [Credits](#Credits)


### Anchors
The start and end of the expression is indicated by the meta escape. `\b` assert position at a word boundary: `(^\w|\w$|\W\w|\w\W)`

### Quantifiers
`+` is the quantifier that matches the previous token between one and unlimited times.
` (?:\.[\w-]+)*`
`*` matches the previous token between zero and unlimited times.

### OR Operator
In this email regular expression, we are not asserting the OR operatior. An example of an OR operator utilizing | Vertical line or pipe. 
In the example: `a(b|c)` matches a string that is followed by b or c (and captures b or c). 
There is a | Pipe between two characters classes. This creates 2 alternative groups. 
This allows the search to find and match either group. 

### Character Classes
There are several character classes in the email validation. 

Match a single character present between the brackets: `[\w.!#$%&’*+\/=?^'{|}~-]`
Any of the special characters are valid.

`\w` matches any word character (equivalent to [a-zA-Z0-9_])
Any of these characters are valid: including upper or lowercase letters, numbers 0-9 and underscore character.

`=?^'{|}~`matches a single character in the list `=?^'{|}~` (case sensitive)

`.!#$%&'*+` matches a single character in the list `.!#$%&'*+`

`\/ `matches the character `/` with index 4710 (2F16 or 578) literally 

`-` (hyphen) matches the character `-` with index 4510 (2D16 or 558) literally

`@` matches the character `@` with index 6410 (4016 or 1008) literally (case sensitive)

Match a single character present in the list below `[\w-]`

### Flags
Global pattern flags
y modifier: sticky. Force the pattern to only match consecutive matches from where the previous match ended. 
The flag y makes regexp.exec to search exactly at position lastIndex, not “starting from” it.

### Grouping and Capturing
Non-capturing group `(?:\.[\w-]+)*`
* matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy)

`\.` matches the character `.` with index 4610 (2E16 or 568) literally (case sensitive).

### Bracket Expressions
The brackets `[ ]` indicate a set of characters to match. Any individual character between the brackets is accepted as a match. There are 3 instances of bracket expressions to validate the email. 
1. The first one `[\w.!#$%&’*+\/=?^'{|}~-]` refers to the prefix of the email or the user identifier. 
2. Next is `[\w-]` referring to the domain name.
3. Last is the `[\w-]` which is the domain (com, org, biz ...).

### Greedy and Lazy Match
`+` is the quantifier that matches the previous token between one and unlimited times, as many times as possible, giving back as needed (greedy).
`*` matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy).

### Boundaries
`\b` assert position at a word boundary: `(^\w|\w$|\W\w|\w\W)` 
`\b` which represents an anchor like caret (it is similar to $ and ^) matching positions where one side is a word character (like \w) and the other side is not a word character.

### Back-references
In this email regular expression, we are not utilizing back-references. An example of a back-reference is `d(?=r)`. This expression matches a d only if is followed by r, but r will not be part of the overall regex.

### Look-ahead and Look-behind
In this email regular expression, we are not utilizing Look-ahead and Look-behind.
An example of this is when we need to find only those matches for a pattern that are followed or preceded by another pattern.
Positive lookbehind: `(?<=Y)X`, matches X, but only if there’s Y before it. Similarly, Negative lookbehind: `(?<!Y)X`, matches X, but only if there’s no Y before it.

## Credits
  - [regex101](https://regex101.com/) 
  - [Jonny Fox, Regex cookbook](https://medium.com/factory-mind/regex-cookbook-most-wanted-regex-aa721558c3c1) 

## Author
Lara Foster, Fullstack Developer 
  - [Github](https://github.com/larafoster) 
  - [Send me an email](mailto:larafoster.dev@gmail.com) 