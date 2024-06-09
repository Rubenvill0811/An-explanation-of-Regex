# Regex Simplified

In this gist I'm going to breakdown Regex and it's functionality to give you a basic understanding of Regular Expression, or Regex for short.

## Summary

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This is Regex! At first glance it's intimidating and it seems like it's a meaningless string of characters. However, if you take the time to read this gist you will have a foundation to work from and you will be able to experiment with Regex and test its limits!

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

We will be going over the Regex components in greater detail througout this gist, breifly, here are some of the main components in Regex. These components allow you to define the search parameters with specificity.

- Anchors
- Quantifiers
- Character Classes
- Bracket Expressions
- Flags

### Anchors

A Regex anchor allows the developer to define where matches begin or where matches end in a string. The syntax for defining where a match begins is different than defining where the match ends. To define where a match begins we will use the caret ^. Let' make an example.

/^T/

The small boy plays with a big toy.

In this example the letter T would be the match.

/g$/

The small boy plays with a big toy.

In this example the "g" at the end of "big" will provide the match.

Something to remember when using anchors is how Regex reads the text. Regex will read an entire paragraph as one string and because of that it will only match The begining of one line at a time and will not match multiple lines unless the multiline flag is enabled. We'll go over flags later in this tutorial.

### Quantifiers

A quantifier allows the developer to determine the number of times a character may be returned in a search. Here is a list of quantifiers and a brief descritption of what the quantifier does.

- '?' This quantifier makes any character after the questionmark optional.

- "\*" This quantifier matches zero or more.

- '+' This quantifier will match any repeating character.

- '{x}' This quantifier will return a match for a specified amount of times. The developer will put the desired amount between the curly braces like so {5}.

- '{x,}' This quantifier will return the specified amount of matches or more

- '{x,y}' This quantifier will return matches between two specified numebers. If you wanted between four or five matches you would enter it like so, {4,5}.

An important thing to remember about quantifiers is that you can use them after one of these expressions and repeat them as many times as you need like this

[abc]{4}

This will return matches for these character classes four times exactly.

### OR Operator

If you are familiar with Javascript you've likely used the 'OR' operator, which looks like this '||'. In Regex the OR operator has the same functionality but you only need to use one pipe, like this '|'.

In Regex the OR operator allows you to seach a string for one match or another. If you were looking for names that had a similar ending but started differently, you could search the string like this

/(S|K)elly/

This search will return both names Shelly and Kelli because it searches for 'elly' with the starting characters of either 'S' or 'K'.

### Character Classes

creating a search using a character class searches for specific characters in a string.

/[abc]/

This search will return ever instance of 'a' 'b' or 'c' in the string.

### Flags

Flags are interesting because instead of changing the parameters of your search you change the behaivor of the search. Your able to modify the rules for what gets returned. Here is a list of flags and how they work. A flag is added on to the back of the expression like this.

//g

- 'i' The Ignore Casing flag. this flag ignores case sensitivity.

- 'g' The Global flag. This flag makes the expression search for occurrences.

- 's' The Dot all. This flag specifically makes the wild card character '.' apply across all lines in the string.

- 'u' The Unicode flag. This flag allows you to target characters as code points, instead of the default of code units. This flag also allows you to match 32-bit characters as well.

- 'y' The Sticky flag. This flag allows the developer to target the a match at lastindex and only at the lastindex.

- 'm' The Multiline flag. This flag allows you to use the anchor tags '^' and '$' over every single line instead of the beginning or the ending of the entire string.

### Grouping and Capturing

Grouping and Capturing allows you to specify the search to match to a group of characters. Here is an example.

/(ff)/

This search will return any match of the these characters specifically. Examples of words that would be returned are a(ff)irm, Je(ff), a(ff)air. Specifically the double ff's will be returned.

### Bracket Expressions

Bracket Expressions allows the developer to define a search using a seperate ruleset between square brackets.

/[a-z]/

This search will return all lowercase characters of the alphabet.

/[0-9]/

This expression will return any numbers between 0 and 9.

One thing to remember about Bracket Expressions is that they look similar to character classes and they function similarly!

### Greedy and Lazy Match

Greedy and Lazy Matches are quantifiers that tell the Regex engine to make as many matches as possible (a greedy match), or, to make as few matches as possible (a lazy match). Naturally the Regex engine leans toward making greedy matches, if you wanted make a a quantifier lazy you simply add a question mark that the end of the expression. Because of the way that the Regex engine alternates between between search terms after the search parameters (quantifiers) have been satisfied ( like matching this /([aaaabbcc]){2,4}/), the search would max out after the first four a's. If the quantifier expression had been lazy it would return more matches every time that the Regex engine would alternate.

Greedy Match

/([aabcc]{2,4})/

Lazy Match

/([aabcc]{2,4}?)/

Notice, the only difference between these two searches is the questionmark after the expression.

### Boundaries

\b - this is a boundary assertion that asserts the current position in the string is word boundary.
\B - This indicates that the current position is NOT a word.

You will want to use boundary assertions when you want to specify a position where a word begins or ends.

### Back-references

A Back-reference allows the developer to match the same text what has been previously matched by a group.

### Look-ahead and Look-behind

The Look-ahead and Look-behind target the characters to the left or the right of the match. This is helpful when you need to express complex expressions.

## Author

My name is Ruben Villalobos, I'm learning how to code and I'm hoping to eventually work in the tech industry.

Git Hub: Rubenvill0811
Email: Rubenvill0811@gmail.com
