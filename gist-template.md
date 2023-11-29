# 17_CS-Regex

The purpose of this assignment was to understand the concept of the computer science term; regular expression, also known as regex, is a sequence of characters that defines a specific search. Regex can be used to find certain patterns of characters within a string, or to replace a character sequence of characters within a string. They're also frequently used to validate input.

For example, the following regular expression can be used to verify that user input is a valid email address:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/


Below, I will be describing what a Hex Value Regex looks like and go into detail, making it make sense.

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
Regex components are what form the sequence of characters that specify a matching pattern in text. They must be wrapped in forward slash characters ( / )

For a Hex Value, it is as follows: 

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

### Anchors
The ^ and $ can be considered anchors. 

The ^ anchor is one character you'll likely see as one of the first few characters. It get the exact string you match it to; exactly down to the case sensetivity of what you want to target.

The $ is one that youll more likely see around the end of the Regex. It is like the carot, but instead of it being (the carrot) and then some characters, it's the some characters, and then the dollar sign. 

In our example the ^#... lets us know that our search is looking exactly for the pound character.

### Quantifiers
Quantifiers set limits of the string you're looking for. that is why you see {6} and {3} in our hex vaue Regex. It is looking for either a hex value with 6 OR 3 characters. 

Qualifiers are greedy in the way that they match as many occurrences of particular patterns as possible. They include the following:

*-Matches the pattern zero or more times.

+-Matches the pattern one or more times.

?-Matches the pattern zero or one time.

{}-Curly brackets can provide three different ways to set limits for a match:

- { n } Matches the pattern exactly n number of times

- { n, } Matches the pattern at least n number of times

- { n } Matches the pattern form a minimum of n number of times to a maximum of x number of times. 

Each of these can be made lazy by adding the ? symbol after it, meaning it will only match as few occurrences as possible

### Grouping Constructs
As regular expressions grow more complicated, you may check multiple parts of a string to determine that different sections fulfill different requirements. To break sections up, youll need to use the grouping constructs. 

In order to group a section of a regex, you use parentheses (()), and each section within a section is known as a subexpression. 

Unlike bracket expressions, subexpressions look for an exact match unless they're told to do otherwise.


### Bracket Expressions
Square brackets ([]), are what store a range of characters. The range of characters that go inside the square brackets are what we want to include in our Regex or what we want to be a part of our search. 

For our example of a Hex Value, the combination of 3 OR 6 characters (OR 8 if you want to include opacity). #FFF makes white and as you go closer to #AAA, you get a light grey. from #999 to #000 it goes from another shade of grey to pitch black. 

With all of that in mind, you can see that the a-f and 0-9 are next to each other. This is because it will only take in lowercase OR uppercase lettering OR 0 through 9 and so on. The only thing you can do is say when to start and when to stop the set of characters that you specified with the first character.

Another Feature that these square brackets can do, is specify what characters NOT to add or find in its search

For example, if you were to do [^aeiouAEIOU], then it would find all the strings that do not have any uppercase nor lowercase vowels in the word search. 

### Character Classes
A character class in a regex defines a set of characters, which can occur in an input string to fulfill a match. 

Here are some common character classes:

- . Matches any characteristic except the new line character (\n)

- \d Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9]. 

- \w Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].

- \s Matches a single whitespace character, including tabs and line breaks

Each of the last three character classes can be changed to perform an inverse match by capitalizing the letter character. For example, \D matches a non-digit character.

### The OR Operator

Throughout this whole reading, you may have caught how I said 6 OR 3 characters. The Or opperator is used by this straight line (|); the vertical bar.

So now that we have most of the basic knowledge of a regex, using what we know, we can already rewrite a regex to allow our hex value to include a user input that wants to have opacity to their hex value. It would go something like this:

/^#?([a-f0-9]{6}|[a-f0-9]{3}|[a-f0-9]{8})$/

### Flags

At the beginning of this, I said how regex's must be wrapped in forward slash characters; but there is one acception to this rule, and that is with the component known as flags. Flags are placed at the end of a regex, after the second forward slash. What they do is provide more functionality for the regex. There are six flags that can be used, and they may be used seperately or together and in any order. 

three well known flags:
- g - Global search: the regex should be tested against all possible matches in a string.

- i - Case-insensitive search: case should be ignored while attempting a match in a string.

- m - Multi-line search: a multi-line input string should be treated as lultiple lines.

### Character Escapes
The backslash ( \ ) in a regex escapes a character that otherwise would be interpreted literally. for example, the { is used as the beginning of a qualifier, but by adding a backslash before the curly brace means that the regex should look for the open curly brace character instead of beginning to define a quantifier. It is common for the char escape to be used when trying to put special characters inside.

## Author

https://github.com/JoshHill1 

### Github Gist link

https://gist.github.com/JoshHill1/8ef972b3bf270a1da84cd17fca508520 
