# Verifying an email address using Regex.

Without knowing what you are looking at, regex can seem overwhelmingly like hieroglyphics, or like someone mashed their keyboard a few times and decided "This is how you verify something!" Well, that is not the case. In fact, regex is just a simple pattern using symbols that have value. In this article, I will walk you through using Regex to verify an email address.

## Summary

Let's begin with the code snippet: <b>/^([a-z0-9_\ .-]+)@([\da-z\ .-]+)\ .([a-z\ .]{2,6})$/ </b> (I have included spaces after each backslash in order to show its significance. Without the space, the backslash will act as a character escape). With this regex code snippet, you are able to verfiy an email address. The first portion of this is a bracket expression, ensuring that the email has a vaule of "a" through "z" and can include any numerical value as well as an underscore, a period, and a hyphen. Using the plus sign quantifier it will look for at least one of the elements to be matched. Next, it adds an asperand(@), followed by the mail server which are also in bracket expressions. Then, it has a character escape to include the period and will add the domain. Lastly, it will check the length of the preceding item, which in this case, can match a length of two but not exceed six. All of the code is encase in anchors (^) and (\$). 

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

### Anchors
Anchors are used to specify where the pattern should match. The caret(<b>^</b>) is the opening and the dollar sign(<b>$</b>) is the closing symbols and evrything inside these symbols needs to be included in the pattern.

### Quantifiers
? - The question mark specifies zero or one occruence of the preceding element.

\* - The asterisk finds zero or more occurences of the preceding element.

\+ - The plus sign is for at least one occurence of the preceding element.

{n} - There would be a number specified in place of <i>n</i>, and the preceding item is matched exactly that many times.

{min, } - The preceding item is matched at least <i>min</i> times with no maximum limit

{ ,max} - The preceding item is matched zero or more times, up to <i>max</i> times 

{min, max} - The preceding item is matched at least <i>min</i> time, but no more than <i>max</i>

My code only includes the {min, max} quantifier of {2,6} indicating a minimum value of 2 and not surpassing 6. Other examples of quantifiers would be: "favou?rite" which has the option to find "favorite" or "favourite", "ab*a" could be "aa", "aba", "abba" (like the band), "abbba" and I think you get the picture here, it could have no "b"s or as many "b"s as desired. 

### Grouping Constructs
Paratheses are used to group patterns together to capture the matched text. My code snippet has three capturing groups; ([a-z0-9_\ .-]+), which captures the local part of the email (everything before the "@"), ([\da-z\ .-]+) - captures the domain name of the email address (everything between the "@" and the last "."), and ([a-z\ .]{2,6}) - captures the top-level domain (the last part of the domain name, such as "com" or "edu")

### Bracket Expressions
Braket expressions are a way to match a single character or a range of characters. 

My snippet includes three bracket expressions:

[a-z0-9_\ .-] - Has a vaule of "a" through "z" and can include any numerical value as well as an underscore, a period, and a hyphen.

[\da-z\ .-] - "\d" is shorthand for matching digits so any numeric value equivalent to "0-9". "a-z" is checking for lowercase alphabet character. While the " \ ." is a charater escape to allow the use of periods.

[a-z\ .] - This is checking for alphabet values from "a" to "z" and can also inclue periods.

### Character Classes
Character classes often refer to the same thing as a bracket expression. Sometimes, character expressions will refer specifically to the shorthand version of the classes.

### The OR Operator
The boolean "or" operator is defined by a "|", which is called a pipe symbol. In my code snippet I dont have a boolean but it would look like "gray|grey" or gr(a|e)y.

### Flags
Flags can modify how the regex engines interpret patterns or matches in the input string. My code snippet doesn't have any flags, but below I have listed them

"i" - Case-Insensitive matching, ignores differences between upper and lowercase letters.

"g" - Global matching, returns all matches in the input string, not just the first.

"m" - Multi-line matching, allows the anchors to match at the start and end of each line.

"s" - Single-line matching, allows the '.' to match line breaks as well.

"u" - Enables Unicode matching

"x" - Enables extended mode, which ignores whitespace and allows comments in the pattern

### Character Escapes
A character escape, which is symbolized with a backslash( \ ) is required to match certain characters like the period or hyphen. The character escapes are also special sequences of characters that represent a single character.

"\d" - Matches any digit.

"\s" - Matches whitespace characters (spaces, tabs, linebreaks, etc.)

"\w" - Matches any word characters (letters, digits, and underscores)

## Author

Hello, I'm Christopher Baldock. I'm currently a part time student in a coding boot camp with SMU, where I'm expanding my knowledge in data analytics. I've always had a knack for numbers, which is what drew me to the world of databases. I find it fascinating to create organized tables that can be used to derive insights and inform decision-making. While I hope to land a job in data analytics, my ultimate goal is to continue learning and growing in this field. I also creating things, be it tangible or intangible. My current occuption is a carpenter. My hobbies include hiking, gaming, and listening to music. If you wish to see some of my work my GitHub profile is [CBaldock2](https://github.com/CBaldock2). Feel free to reach out via email at [thisIsNotMyActualEmailAddress@gmail.com](mailto:thisIsNotMyActualEmailAddress@gmail.com)
