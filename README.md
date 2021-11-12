# Matching an Email with Regex

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

A regular expression, or regex for short, is a way to search patterns of characters, using a particular syntax. 

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

In this document, we'll talk about how regex is used to check if emails match how it's expected to be written.


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

In this particular case, we will study the component of a regex to determine if a email is correct or not. The expression for this regex is:

``` javascript
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
 Let's take a look to the components of this regex.

### Anchors

The anchors determine the beginning and the end of the pattern we are looking at. To begin the pattern, it is used the anchor ```^```, and to end, the anchos ```$```.
The anchor ^ could be used in two different ways: as a string march, or as a range of possibles matches. In the case of the regex that matches an email, it is used to determine a range of possible matches.

As we can see, at the beginning of the regex ```([a-z0-9_\.-]+)```, it is expected to start with a letter, number, or a sign like ```_``` , ```.``` or ```-```. At the end, ```([a-z\.]{2,6})``` is spected to end with a combination of letters, but is also adding a condition ```{2,6}```, called quantifier, that is going to be explained in the next section.

### Quantifiers

The quantifiers determine the number of characters that the regex is going to match. Normally have a minimum and a maximum of characters.

There exist many ways to use the quantifiers. They are:
- ```*``` : Matches the pattern zero or more times
- ```+``` : Matches the patter one or more times
- ```?``` : Matches the patter zero or one time
- ```{}```: Curly brackers can be use in three differents ways:
  - ```{n}```: Matches the pattern exactly ````n``` times
  - ```{n, }```: Matches the pattern at least ```n``` times.
  - ```{n, m}```: Matches the patter between ```n``` and ```m``` times

In the case of the email, at the end of the regex, the quantifier ```{2,6}``` is looking for a pattern between 2 and 6 letters or numbers.

### Grouping Constructs

Grouping constructors are use to determine sections of a regex. Each section is devided by parentheses ```()```, and are called subexpressions.

In this example, the "Matching an Email" regex have three subexpressions:

- ```([a-z0-9_\.-]+)``` is the first one
- ```([\da-z\.-]+)``` is the second one
- ```([a-z\.]{2,6})``` is the third one

Inside of each subexpression is a bracket expression. Let's take a look to what they are.

### Bracket Expressions

Bracket expressions are denoted by square brackets ```[]```, and represent the all the possible characters of the pattern we want to match. For example, the bracket expression ```[xyz]```, will look for all the string that contain the letters ```x```, ```y``` or ```z```, independent of the length of the match, so ```xzyz``` will be a match and ```xxxxxxxxxxxxx```, will be a match too.

Bracket expressions are commonly used in five ways:

- ```[a-z]```: The string can contain any lowercase letter between a and z.
- ```[A-Z]```: The string can contain any uppercase letter between A and Z.
- ```[a-zA-Z]```: The string can contain any letter between a and z.
- ```[0-9]```: The string can contain numbers between 0 and 9.
- ```[_-]```: The string can contain underscore and hyphens.

In the cas of the "Matching an email" regex, in each grouping constructor is a bracket expression inside. For example, in the first grouping constructor ```([a-z0-9_\.-]+)```, it's expected to match any combination of letters, numbers, underscore and hyphens.

### Character Classes

The characters classes describes other type of character that matches with the pattern. 

Some examples of this are:

- ```\d```: Matches any numeric digit.
- ```\w```: Matches any alphanumeric character. It's equivalent to the bracket expression ```[A-Za-z0-9]```.
- ```\s```: Matches a singles whispace character, tab or line breaks.
- ```\.```: Matches any character except the newline character ```\n```

In the case of "Matching an email" regex, there is a character class ```\.``` in every bracket expression.

### The OR Operator

The or operator ```|``` is use simillar to any other or operator in programming. It allows matching between two or more options. For example, the regex ```[xyz]``` can be writen as ```(x|y|z)```.

In the cas of the "Matching an email" regex, there is no OR operator

### Flags

Flags are added at the end of the regex to include some optiones to the search. There are six optional flags, and they are: 

- ```i```: ignore casing
- ```g```: which stands for global, serves to extend the searching to find all matches for a given expression inside a string, instead of stopping on the first match.
- ```s```: make the character class ````.``` match newlines as well.
- ```m```: Makes the boundary characters ```^``` and ```$``` match the beginning and ending of every single line instead of the beginning and ending of the whole string.
- ```y```: Makes the expression start its searching from the index indicated in its lastIndex property.
- ```u```: Makes the expression assume individual characters as code points, not code units.

### Character Escapes

The character escape is a way to include a character that want to be in the pattern, that otherwise would be interpreted literally. It is used with the backslash ```\```. Some examples are ```\n```, ```\{``` or ```\.```.

## Author

This tutorial was created by [Juan Jose Ramirez](https://github.com/JuanjoRamirez262).
