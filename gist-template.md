# Explaining a Regular Expression

A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string.

## Summary

Below we will discuss how to implement a regular expression to find an email matching the search criteria. Using the following, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, I will detail the various components of the regex and explain what is occuring. Regular expressions begin and end with forward slashes, `/`, in order to indicate the search parameters and define itself as a regex.


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

### Anchors

Both `^` and `$` are considered <b>Anchors</b>. 

The `^` charactor denotes a string that begins with the specific charactors that follow it. This can be in two formats:
* A case sensitive string that is an exact match.
* A range of possible matches, displayed using braket expressions.

In the above regular expression, as identified in the summary, the regex is looking for a range of possible alphanumeric mathces before the `@` symbol including certain special characters: `_\.-`.

The `$` character denotes a string that ends with the characters that precede it. It can be preceded with an exact string or a range of possible matches.

In the above regular expression, as identified in the summary, the regex is looking for a range of possible lower case alphabetic mathces including certain special characters: `\.`.

### Quantifiers

<b>Quantifiers</b> restrict the string that matches the regular expression (or an individual section of the string). They mostly contain the beginning and ending constraints of the string, the minimum and maximum number of characters to be matched by the regular expression.

Quantifiers are <b>greedy</b> by default which mean they will match as many occurences of a particular pattern as possible. However, each quanifier can be made <b>lazy</b> by adding the `?` symbol after it which means the regex will match as few occurences of a particular pattern as possible.

* `*` Matches the pattern zero or more times

* `+` Matches the pattern one or more times

* `?` Matches the pattern zero or one time

* `{}` Curly brackets can provide three different ways to set limits for a match:

    * `{ n }` Matches the pattern exactly n number of times

    * `{ n, }` Matches the pattern at least n number of times

    * `{ n, x }` Matches the pattern from a minimum of n number of times to a maximum of x number of times

### OR Operator

As a bracket expression represents a pattern to be matched, there are several possiblities of patterns that can be identified. Therefore, it is more specific to use the `OR` operator, `|`, to better specify patterns to be matched. Furthermore, the operator can be used outside of bracket expressions.

### Character Classes

A character class within a regex can define a set of characters that can be matched.

The following are common character classes:

* `.` Matches any character except the newline character (\n)

* `\d` Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].

* `\w` Matches any alphanumeric character from the basic Latin alphabet, including the underscore `_`. This class is equivalent to the bracket expression [A-Za-z0-9_].

* `\s` Matches a single whitespace character, including tabs and line breaks

Each of the last three character classes can be changed to perform an inverse match by capitalizing the letter character.

### Flags

The one exception to the rule stating that regular expressions, as a literal, must be wrapped in forward slashes, `/`, are components known as `Flags`. Flags are placed at the end of the regex, after the second forward slash, to define extra specificity or limitation.

There are six optional flags that can be used, either separately or together and in any order, but these are the three you're most likely to encounter:

* `g` Global search: the regex should be tested against all possible matches in a string.

* `i` Case-insensitive search: case should be ignored while attempting a match in a string

* `m` Multi-line search: a multi-line input string should be treated as multiple lines


### Grouping and Capturing

To break up sections of the regular expression to check for matching patterns, it is possible to surround what are known as subexpresions with parentheses. Also known as grouping constructs, seperating expressions with parentheses add an extra level of complexity to the regular expression.

Grouping constructs have two primary categories: capturing and non-capturing. Capturing group constructs designate a matching pattern to be re-used while non-capturing do not. To identify a non-capturing group construct, precede a given expression with `?:` inside of the parentheses.

### Bracket Expressions

Anything within the `[]` brackets is considered the range of characters to be searched for by the regular expression. Also known as a <b>positive character group</b>, we write these expressions to include all of the characters we want to match.

It is common to see a hyphin between alphanumeric characters that specify a range of characters to match, such as `a-z0-9` which will match an lower case characters between a and z along with any numbers between 0 and 9. 

Bracket expressions also include special characters to be matched which can include hyphins as well as is exemplified in the first bracket expression in the email search regex: `_\.-`.

### Greedy and Lazy Match

Greedy matches indicates that a regex will attempt to match as many occurences of a particular pattern as possible. Whereas, lazy matches will attempt to match as few occurences of a particular pattern as possible.

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
