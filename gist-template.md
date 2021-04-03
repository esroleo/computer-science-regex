# Title (replace with your title)

This gist is a tutorial for a regex expression that matches a valid email address.

## Summary

This tutorial will cover a step by step deconstruction of a regex that matches a valid email address.

The regex expression we will be deconding is ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```


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

Regular expressions are patterns used to match character combinations in strings. Please see below compnents used for this regex expression to match an email address.


### Anchors

Anchors match a position before or after characters.

 ^ – The caret anchor matches the beginning of the text.
 $ – The dollar anchor matches the end of the text.

In our example  ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```, we have two anchors ^ and $, meaning where to start a matching pattern and whend to end it.

You can see the / slash at the beggining and at the end of our regex expression. Meaning it starts at /^ (beggining) and ends at $/.

### Quantifiers

In our example  ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```, we specify how many instances of a character, group, or character class must be present in the string matched.

In the case of the left side of the @: ```/^([a-z0-9_\.-]+)```

We will match one string as dictated by the + sign before the last parentheses.

In the case of the right side of the @: ```([\da-z\.-]+)\.([a-z\.]{2,6})$/```

We will match one string as dictated by the + sign before the escaped period \.

```{2,6}``` --> matches between 2 and 6 of the preceding token (```[a-z\.]```)

### Character Classes

In our example  ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```, we have [] square breackets, these are used to match different sypes of strings in order to match what you are looking for. 

In this case lets divide the expression in two sections, before and after @.

Left side of the @: ```[a-z0-9_\.-]+```

a-z --> match and lowercase character from a-z
0-9 --> match any characters from 0-9
_ --> allow the usage of _ (underscore character) in the matching.
\. --> escapte character for the . character.
+ --> We will match one string as dictated by the + sign before the last parentheses.
- --> allow the usage of - (minus symbol) in the matching


e.g (left side of the @) --> test1_ab.--  


Right side of the @: ```[\da-z\.-\.-]+)\.([a-z\.]{2,6})$/```

```\da-z\.-\.-]+)``` or before .com scenarios for matching.

\d --> match any digit character from 0-9
a-z --> match any character from a-z lowercase (case sensitive)
\. --> escapte character for the . character.
- --> allow the usage of - (minus symbol) in the matching
+ --> We will match one string as dictated by the + sign before the last parentheses.

```\.([a-z\.]{2,6})$/``` or the .com scenarios for matching.

\. --> escapte character for the . character.
a-z --> match any character from a-z lowercase (case sensitive)
\. --> escapte character for the . character.
{2-6} --> matches between 2 and 6 (min 2 and max of 6) of the preceding token (```[a-z\.]```)
$ --> matched at the end of the string. It means that the .com or .ca etc has to be at the end of the email address string.

e.g (right of the @) --> @gmail.ca or hotmail.com

Full example 

test1_ab.--@gmail.com
test123_ab--.@hotmail.com

### Grouping and Capturing

In our example  ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```, we have () parentheses used togroup two sections. That is before @ and after. 

That is to group two regrular expressions. One will target before the @, and the other after to match the email address format.

### Bracket Expressions

In our example  ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```, we have [] square breackets, these are used to match different sypes of strings in order to match what you are looking for. 

### Greedy and Lazy Match

Is a way to tell the regex expression how many characters you want to match. In our case we do not have a lazy method since actually want the whole string. 

```/^([a-z0-9_\.-]+)``` --> We will match one character token or group.

## Author

Tutorial created by Esteban Romero. 

Gist link --> 

Git Hub profile --> https://github.com/esroleo


## Credits

https://www.javascripttutorial.net/regular-expression-anchors/#:~:text=Anchors%20have%20special%20meaning%20in,the%20beginning%20of%20the%20text.


