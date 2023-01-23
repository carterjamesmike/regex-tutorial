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
