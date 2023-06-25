# Matching Hex Values Using Regex

## Introduction

The hexadecimal positional numeral system is a base-16 system used to represent numbers which is widely used in computing and digital systems. In this system, there are 16 digits used to represent the numbers 0-9, followed by A-F, where A represents 10, B represents 11, and so on up to F, which represents 15. Each digit's value is based on its position within the number, similar to the decimal system.

A common use of the hex system is defining hex color codes. A hex color code is a six-digit code that combines numbers (0-9) and letters (A-F) to define the intensity of red, green, and blue (RGB) components in a color. Each pair of digits represents one of the RGB channels, in that order, ranging from 00 (minimum intensity) to FF (maximum intensity).

For example, the code #FF0000 represents pure red, with maximum intensity in the red channel and no intensity in green and blue channels. Similarly, #00FF00 represents pure green, and #0000FF represents pure blue. In some cases, we can also define a hex value using only three characters. This is true when the same character is used twice to represent the values of the RGB components. For example, red can be written as #FF0000 or #F00.

Hexadecimal color codes allow designers to precisely define shades and hues. They are widely used in various applications, including web design, graphic design, and programming, to ensure consistent and accurate color representation across different platforms and devices.

In this tutotial, we will learn more about matching Hex Values using regular expressions. We will delve into how this specific regular expression, or regex, works, taking a look at each component.

## Summary

We will be looking at the following regex, matching a Hex Value:

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

This regex is used to check whether a given string is a valid hexadecimal code. Below we will detail the anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes. We will also look at some examples.

<hr>

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
<hr>

## Regex Components

<hr>

### Anchors

In the case of matching hex values, the `^` symbol indicates the beginning of the string, and the `$` indicates the end of the string. For example, `^abc` will match if the string begins with abc, and `xyz$` will match if the string ends with xyz. Our regex uses these symbols in combination to check the full expression and whether it matches the hex value pattern.

### Quantifiers

This regex used the quantifiers `?` and `{n}`.

The question mark `?` acts as a quantifier that allows matching the preceding character 0 or 1 times. It acts as a conditional element within the regex pattern. In our specific regex, the `?` is preceded by the pound symbol `#,` which means that the expression will match either a string that starts with `#` or a string that does not. To illustrate another example using the question mark `?`, consider the regex pattern `\w+ou?r`, which matches both "favor" and "favour".

The `{n}` quantifier appears twice, `{6}` and `{3}`. This metacharacter specifies the exact number of times the preceding character should be matched, in this case, n times. For instance, `{\d{4}}` in the regular expression will match any string that consists of four consecutive digits, such as `1234` or `5555`.

### Grouping Constructs

The regex uses one group: `([a-f0-9]{6}|[a-f0-9]{3})`. This grouping is employed in conjunction with the OR operator, which will be explained further in the OR operators section.

### Bracket Expressions

The bracket expression `[]` is placed within the grouping construct, before the quantifier. It allows us to define a valid hex value. This means our regex with a bracket expression of `[a-f0-9]` will match a string containing lowercase letters between "a" and "f" and digits between 0 to 9. This is also relevant in character classes, which will be explained next.

### Character Classes

Within this regex, we utilize a character class that repeats twice: `[a-f0-9]`. A character class allows for matching any character enclosed within square brackets. For instance, `[abc]` would match either "a," "b," or "c." Similarly, `[-.]` would match either "-" or ".".

Within our character class, we define two ranges: `a-f` and `0-9`. This means that it will match any character ranging from "a" to "f" (in lowercase, excluding uppercase letters) and any character ranging from "0" to "9." For example, `[a-d]` would match "a," "b," "c," or "d," while `[2-4]` would match "2," "3," or "4."

### The OR Operator

As previously mentioned, our regex contains a group separated by the OR operator (`|`). Within the group (`[a-f0-9]{6}|[a-f0-9]{3}`), we have two expressions: `[a-f0-9]{6}` and `[a-f0-9]{3}`. This implies that our regex will match either of these two expressions.

### Flags

In regular expressions, flags modify matching behavior. However, there are none present in the matching hex values regex.

### Character Escapes

Character escapes are special sequences used to match specific characters or groups of characters in regular expressions. They are represented by a backslash (`\`) followed by the character to be matched. Within our specific regex, we employ two character escapes:

- The "#" character is matched using the escape sequence `#`.
- Any digit from '0' to '9' is matched using the escape sequence `\d`.

These character escapes allow us to match the optional `#` character at the start of the hexadecimal value and the digits contained within the hexadecimal value itself.

## Conclusion

After looking at each component in our regex `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, we can summarize its matching pattern as follows:

"The pattern matches any sequence of characters that begins with a # symbol or without it, followed by either six characters ranging from 'a' to 'f' and '0' to '9', OR followed by three characters ranging from 'a' to 'f' and '0' to '9'."

## Author

If you have any questions, please contact feel free to contact me here:

- Email: [kirstyn.rowen@gmail.com](mailto:kirstyn.rowen@gmail.com)
- GitHub: [kirstynrowen](https://github.com/kirstynrowen)
