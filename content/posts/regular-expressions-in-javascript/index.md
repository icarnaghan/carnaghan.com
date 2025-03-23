---
author: "icarnaghan"
title: "Regular Expressions in JavaScript"
date: 2019-11-05
categories: 
  - "coding"
---

In programming, there are many ways to work with strings. A performant way to work with them is through the use of Regular expressions, also known as Regex.

By using regular expressions, you can search for a substring within a string, replace a substring within a string, and extract information from that string. Regular expressions are supported in almost every language. There can be small differences, but the general concept is the same. Javascript is one of the few languages that has direct built-in support for regular expressions.

Regular expressions are difficult to understand for new developers. Even for experienced developers, it can become difficult to work with regex. This tutorial will hopefully clear up any complications with regex and get you started working with regular expressions in your own code.

# Ways of using regular expressions in Javascript

A regular expression in JavaScript is an object that can be defined in two ways.

Instantiating a new RegExp object

```javascript
const regex1 = new RegExp('Hello World')
```

Using the literal form

```javascript
const regex1 = /Hello World/
```

In the first example, 'Hello World' is a pattern. In this second example, the pattern is delimited by the forward slashes, while there are no forward slashes with the object constructor.

# How regular expressions work?

Earlier, I mentioned, regular expressions can be used for searching a substring within a string. This is one basic use of a regular expression. Take a look at the following RegExp object.

```javascript
const regex1 = RegExp('Hello World')
```

What does this actually mean? It searches the string 'Hello World' without any limitations. It does not matter if another string contains 'Hello World' in the middle or starting, or at the end, or even if the string contains only 'Hello World', the regex is satisfied. It does not matter how long the text is.

We can use the test() method to test the regex. This method returns a boolean value.

```javascript
regex1.('sdadasd Hello World asdsadadas') // returns true
regex1.('Hello World asdsadadas') // returns true
regex1.('sdadasd Hello World') // returns true
```

The above three will return true because the substring is present in each of the string passes. Now, have a look at the following.

```javascript
regex1.('sdadasd World asdsadadas') // returns false 
regex1.('Hello asdsadadas') // returns false 
regex1.('sdadasd World') // returns false
```

This time, all three will return false because none of the above contains the exact substring.

This is a simple way of using regular expressions.

# Matching items

Matching is another benefit of regular expressions. Suppose we need to find if a string contains any alphabetic characters. We can use the following method.

```javascript
/[a-z]/.test('abc232') // returns true
```

a-z matches against all or any characters between a and z. When this range is specified between square brackets, the regex will search for any character in a given string. As the string passed('abc232'), contains at least one alphabetic character, the test() method returns true.

Similarly, we have a few other ranges.

```javascript
/[a-z]/ // a,b,c,d,e.....x,y,z 
/[A-Z]/ // A,B,C,D,E.....X,Y,Z 
/[0-9]/ // 0,1,2,3,4.....7,8,9
```

We can also combine these ranges.

```javascript
/[A-Za-z0-9]/
```

Let's see a few more examples.

```javascript
/[a-d]/ // returns true if a or b or c or d is present in the string 
/[0-2]/ // returns true if 0 or 1 or 2 is present in the string
```

There is also a wide range of metacharacters.

- w - matches any alphanumeric character plus underscores. It is equivalent to \[A-Za-z\_0-9\].
- W - matches anything except \[A-Za-z\_0-9\]
- d - equivalent to \[0-9\]
- D - matches anything except \[0-9\]
- s - matches any whitespace character
- S - matches any character that is not a whitespace
- n - matches a newline
- \- matches a null value
- t - matches a tab character

We can also negate a pattern using the ^ character. Have a look at the following pattern.

```javascript
/[^A-Za-z0-9]/
```

This means, anything except the characters specified in double brackets.

```javascript
/[^A-Za-z0-9]/.test('a') // returns false
```

The above regex returns false because 'a' matches the pattern \[A-Za-z0-9\], but because we used negation, it will not match.

# Anchoring

Anchoring is handy if we want to check if a given string starts with a certain character or ends with a certain character. Then we have two special operators, ^ for checking if a character is present at the start, and $ for checking if a character is present at the end.

```javascript
/^a/.test('abc') // returns true 
/^a/.test('bca') // returns false
```

Similarly, we can use the $ operator to check if a character is present at the end or not.

```javascript
/a$/.test('abc') // returns false 
/a$/.test('bca') // returns true
```

# Quantifiers

Quantifiers are a very useful part of regular expressions. Suppose we want to match a string that contains at least one 'a'. We can use the + operator. Similarly, there are few other quantifiers.

## \+ Operator

As mentioned above, the + operator will match if the specified character is present at least one time.

```javascript
/a+/.('abcbaaa') // returns true 
/a+/.test('bbbbb') // returns false
```

## \* Operator

The \* operator will match a string if contains the specified character zero or more times.

```javascript
/a*/.test('abcbaaa') // returns true 
/a*/.test('bbbbb') // returns true
```

## ? Operator

The ? operator will match a string if it contains the specified character at most one time.

```javascript
/a?/.test('abc') // returns true 
/a?/.test('abababba') // returns false
```

## {n} Operator

This will return true if the string contains the specified character n times in a sequence.

```javascript
/a{4}/.test('aaaabc') // returns true 
/a{4}/.test('aabaa') // returns false
```

## Creating groups

We can also create groups in regular expressions using parenthesis. Have a look at the following example.

```javascript
/^(a{3})b$/.test('aaab') // returns true
```

In the above example, a group is created that defines three 'a' at the beginning followed by a single 'b' at the end.

# Modifiers

There are three main modifiers in JavaScript.

- i - used to perform case-insensitive matching.
- m - specifies that the ^ and $ operators will match against a newline boundary if the string has a newline or return characters.
- g - used to find all the matches in a string.

## String methods

Two JavaScript methods are used with regular expressions - search() and replace().

The search() method is used to search a match, and it returns the position of the match.

```javascript
'Hello World'.search(/world/i) // returns 6
```

The above example will return the starting point of the match, i.e. 6. Here, i is a modifier for the case-insensitive match.

The replace method() is used to replace the matched substring with another string.

```javascript
'Hello World'.replace(/world/i, 'Universe') // returns 'Hello Universe'
```

# Wrapping it up

As mentioned at the beginning of this article, regular expressions are difficult to understand at first. If this is the first time you are going through these concept, you may find them challenging. Don’t let this deter you, it takes some time to understand regular expressions, however with practice and you will soon realize that while regular expressions look complicated, they are actually straight forward. Finally, I highly recommend the wonderful https://regexr.com/ site to practice your regular expressions. Feel free to post in the comments section below and share your own experiences and / or questions on regular expressions.
