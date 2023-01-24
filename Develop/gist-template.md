# Regular Expression Youtube Video Identifier  

A regular expression (regex) is a unique and specific order of characters that specify a search pattern. It can be as simple as locating every word starting with a capital letter or as complicated as every instance of a vowel followed by a whitespace and then a three letter word. 

## Summary
    The regex that I will be covering within this tutorial is a Youtube URL validator. This regex search will recognize Youtube URLs in the many different variations that they come in. This regex can have many uses for blogging or social media applications such as auto-formatting videos or automatically switching any linked Youtube video to a Rick Roll. 

>/((?:https?:)?\/\/)?((?:www|m)\.)?((?:youtube\.com|youtu.be))(\/(?:[\w\-]+\?v=|embed\/|v\/)?)([\w\-]+)(\S+)?/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
    Regex anchors are used to assert positions within the search parameters. They can be used to indicate the start or end of a line such as with the caret (^) and dollar sign ($) characters respectfully or word boundaries using /b. This particular regex does not use anchors as it’s designed to search the entirety of the text to locate Youtube URLs. 
### Quantifiers
    Quantifiers are limitations on matches that can be applied to the regex as a whole or to specific parts of the regex. Quantifiers use the characters +, *, ?, as well as curly brackets.
- "+" will match one or more of the preceding token 
- "*" will match 0 or more
- "?" will make the quantifier “lazy” which means it will match as few characters as possible
- "{ }" will match characters to the quantity specified within the brackets. This can be further fine tuned to be exactly x matches, x or more matches, or between x and y matches.

This regex makes frequent use of the “lazy” quantifier to limit its matches for three of its capturing groups, within the fourth capturing group, as well as after the s in **https** to enable matching with or without the s, and finally following the whole https capture group to match any URLs that may or may not include it. 
>((?:https?:)?\/\/)**?**

>((?:www|m)\.)**?**

>(\S+)**?**

>(?:[\w\-]+\?v=|embed\/|v\/)**?**

>https **?**

>(?:https?:)**?**

### OR Operator
    An alternation is represented by the **|** character. This acts much in the same way as a boolean OR operator. When used with regex it will match expressions before or after the **|**. This regex uses four of these characters. One within the second capturing group to allow matching URLs that start with “www” or “m”, another in the third capturing group to allow “youtube.com” or “youtu.be”, and two others are within the fourth capturing group to allow for the various URL formats that follow the “/” after the domain name. 
>(?:www **|** m)

>(?:youtube\.com **|** youtu.be)

>(?:[\w\-]+\?v= **|** embed\/ **|** v\/)

### Character Classes
    Character classes match specific characters such as alpha-numeric characters, arabic characters, whole words, or even whitespace. They primarily use square brackets and backslashes to specify what character(s) the regex is trying to match. 
- “[ ]” Characters placed within square brackets will be matched literally, though a caret (^) can be added to negate the set and a hyphen (-) can be added to indicate range
- “.” This dot will universally match any character except line breaks.
- “\” The backslash is primarily used with the character w, d, and s to indicate words, digits, and whitespace respectively. Capitalizing these three characters will negate the search and return the opposite. The backslash can also be used to escape a character, such as a forward slash or dots.

As URLs often use backslashes, question marks, and dots, this regex uses the backslash throught the whole expression to escape these characters and allow them to be matched. The regex also uses \w for matching whole words.

>((?:www|m) `\.` )

>((?:https?:)? `\/\/` )

>(?:[ **`\w`** \-]+\?v=|embed\/|v\/)?)

### Flags
    Flags are modifiers that are placed at the very end of the regex, right after the last forward slash. They place some additional rules to the expression. 

- “g” This global modifier will retain the last index of the search and allow subsequent searches without repeating the previous match. Without it, the regex will only search for a single match
- “m” The multiline modifier will match the start and end of a line instead of the whole string with the caret and dollar sign anchors enabled 
- “i” This is the case insensitive modifier and will return matches regardless of case
- “u” The unicode modifier will extend unicode escapes
- “y” This sticky modifier ignores the global modifier and and matches only from the last index
- “s” This is the dotall modifier and it will match all characters. It will match newlines as well. 

We use the “g” global modifier for this regex as we wish it to search the entirety of the script for youtube links.

> /((?:https?:)?\/\/)?((?:www|m)\.)?((?:youtube\.com|youtu.be))(\/(?:[\w\-]+\?v=|embed\/|v\/)?)([\w\-]+)(\S+)?/ **g**

### Grouping and Capturing
    Grouping and capturing are almost like mini-expressions within the larger one you are building. They allow you to combine elements that must be matched before proceeding on to the next. If we were to be using a regex to validate an email, this would ensure the characters that come before the “@” character are valid before checking for an “@” character. They primarily exist between parentheses. Characters within the parentheses are matched exactly unlike our bracketed character classes. 

    With grouping, there are captured and non-captured groups. Captured groups are created just with the parentheses, while non-captured groups have  “?:” following the opening parenthesis.

This regex uses six total captured groups and within the first four captured groups is a single non-captured group.  

>((?:https?:)?\/\/) group one with a non-caputred group

>((?:youtube\.com|youtu.be)) group three with a non-captured group

## Author

    By James M. Carter, a UT Coding Bootcamp student enrolled in a full-stack coding course. 

For quetions, please email at carterjamesmike@gmail.com or visit my github profile at [carterjamesmike](https://github.com/carterjamesmike)
