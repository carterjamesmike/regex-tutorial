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
- [Bracket Expressions](#bracket-expressions)
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

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
