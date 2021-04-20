# Title (replace with your title)

Regex for Email explained 

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.
Hello and welcome to my Regex breakdown of a email Regex. This piece of code `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` can actually be used to help us 
search for data within a certain set of paramaters. In this case, someones email address. By the time you are done, this `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`  
will make perfect sense. Enjoy!

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Anchors are what we typically use to start and end our Regex searches. More specifically, Anchors are a set of Regex tokens that are not interpreted as characters, but instead are used to create the paramater in which a Regex is written. Taking our code as an example `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, our `^` and `$` would be our anchor tokens. 

`^` Is used to indicate the beginning of a Regex expression. Meaning whatever character or characters that would proceed after the `^` is where our Regex expression would begin. Example `^th` would match any string that begins with a  `th`. Such as `th`rough or `th`ursday.
`$` Is used to indicate the end of a Regex expression.  Meaning whatever character or characters that would proceed before the `$` is where our Regex expression would end. Example would be `ht$` that finds any word that ends with `ht`. Such as nig`ht` or thoug`ht`. 

Our Email Regex expression does have `^([a-z0-9_\.-]+)` and `([a-z\.]{2,6})$` instead of alphabet characters as our beginning `^` and end `$` paramaters. How that all comes together will be explained later on.  

### Quantifiers

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Quantifiers are used to measure the number of expressions or characters that we are looking to match up in our Regex expression. Their are 10 different Quantifiers that we can use to create a Regex expression, but our Email Regex expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` only contains two of these, the `{}` and `+`.

`{}` This is seen at the end of our Regex expression as `{2,6}` or more accurately, `[a-z\.]{2,6}`.  representing the `{min,max}` number of letters that we want to see at the end of our Email Regex expression. 
As emails end with `.ca` or `.com` we are using the `{2,6}` to make our Email Regex expression work to ensure that what it is looking for ends like an email. 

`+` The `+` sign lets us match any string that contains at least one character that is put prior to the `+` sign, as indicated in our code `([a-z0-9_\.-] + )` and `([\da-z\.-] + )`. The `+` sign is matching any string in the `[a-z0-9_\.-]` and `[\da-z\.-]`. While whats in the `[]` (OR operator) might not make sense at the moment. It will be explained right below!

For the other 8 Quantifiers and how they are used. Feel free to check out W3schools https://www.w3schools.com/jsref/jsref_obj_regexp.asp. While they are outside the scope of this lession. Feel free to check them out!

### OR Operator

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

`[]` is the OR Operator in our `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` Email Regex expression. Seen by `[a-z0-9_\.-]`, `[\da-z\.-]` and `[a-z\.]`. Essentially, what we put in the `[]` is what we are searching for.  

In our first OR Operator `[a-z0-9_\.-]` we have 6 paramaters that we are searching for. 

1. `a-z`
2. `0-9`
3. `_`
4. `\`
5. `.`
6. `-`

In our second OR Operator `[\da-z\.-]` we have 6 paramaters that we are searching for. 

1. `\d`
2. `a-z`
3. `_`
4. `\`
5. `.`
6. `-`

`\d` Is a unique paramater. It wants to match any string that contains a 0,1,2,3,4,5,6,7,8,9. 


In our third OR Operator `[a-z\.]` we have 3 paramaters that we are searching for. 

1. `a-z`
4. `\`
5. `.`


### Character Classes

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

`\` Are used to represent Character Classes in our code. It only appears once in our code, used as `\.` and is found `/^([a-z0-9_\.-]+)@([\da-z\.-]+)` `\.` `([a-z\.]{2,6})$/`.

the `\.` tells our Email Regex expression that we are looking for a `.` period at that point. This is because emails end with a `.` something. EG, gmail `.` com or hotmail`.`ca.

Their are many more character classes than are touched on in this lession. Feel free to check out Mozilla https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Character_Classes to learn more!

### Flags

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

`/ /` Flags are how we start and end our Regex expressions. `/example-expression/`. The `/ /` lets javascript know that we are creating a Regex expression. While more advanced flags exist, we dont need to use any here. 

### Grouping and Capturing

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

`()` represents how we "Group and Capture" seperate parts of our code. In the case of our Email Regex expression, we have three sections being "grouped and captured"
 `([a-z0-9_\.-]+)`, `([\da-z\.-]+)` and `([a-z\.]{2,6})`. 

 These three groupings represent the three different parts that make up our email

1. `([a-z0-9_\.-]+)` is for the emails "username"
2. `([\da-z\.-]+)` is for the email service provider (Gmail, Hotmail, Yahoo ETC)
3. `([a-z\.]{2,6})` is for the emails `.ca` or `.com`


### Greedy and Lazy Match

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

A greedy match exists whenever a `+` is used in a Regex expression, which our email expression has two of `/^([a-z0-9_\.-]` `+` `)@([\da-z\.-]` `+` `)\.([a-z\.]{2,6})$/`

while a quantifier expression `{2,6}` will allow us to have a `{min,max}` paramater. Our `+` tells javascript that their will not be a limit on the number of characters to be returned.

To view our Email Regex in a different way, think of our Regex expression asking for three character limits for our three "grouping and capturing" sections of code.

1. `[a-z0-9_\.-]+` is looking for as many characters as possible.
2. `[\da-z\.-]+` is looking for as many characters as possible.
3. `[a-z\.]{2,6})` is looking for a minimum of 2 and maximum of 6 characters.

## Author

Matthew Bianco is currently becoming a Full Stack Web Developer through the University of Torontos Online Bootcamp. Github: https://github.com/matthewAbianco

