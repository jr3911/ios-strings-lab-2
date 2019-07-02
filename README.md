# Strings Lab 2

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.

## Question 1

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

Example

Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```

```swift
var problem = "split this string into words and print them on separate lines"
var currentWord = ""
var wordArray = [String] ()

// fills array with characters preceeding a space
for char in problem {
if char == "\u{0020}" {
wordArray.append(currentWord)
currentWord = ""
continue
} else {
currentWord += String(char)
}
}

// Finishes array by appending the value last assigned to currentWord
wordArray.append(currentWord)

// Prints each element of the array onto separate lines
for eachWord in wordArray {
print(eachWord)
}
```


## Question 2

Given a string `testString` create a new variable called `condensedString` that has any consecutive spaces in `testString` replaced with a single space.

```swift
let testString = "  How   about      thesespaces  ?  "
//condensedString = " How about thesespaces ? "
```
```swift
let testString = "  How   about      thesespaces  ?  "
var condensedString = ""
var currentWord = ""
var spaces = 0

for char in testString {
if char == " " {
spaces += 1
if spaces > 1 {
spaces = 0
continue
} else {
currentWord.append(char)
}
} else {
currentWord += String(char)
}
condensedString += currentWord
currentWord = ""
}
print(condensedString)
```

## Question 3

Given a string with multiple words. Reverse the string word by word.

Example:

Sample Input: `"Swift is the best language"`

Sample Output: `"language best the is Swift"`

```swift
var sampleString = "Swift is the best language"
var sampleStringArray = sampleString.components(separatedBy: " ")
var reversedStringArray: [String] = sampleStringArray.reversed()
var reversedString = ""

for word in reversedStringArray {
    reversedString += word + " "
}

print(reversedString)
```

## Question 4

Given a string with multiple words. Write code that prints how many of them are palindromes.

Example:

Sample Input: `"danaerys dad cat civic bottle"`

Sample Output: `2`

```swift
let sample = "danaerys dad cat civic bottle"
let array = sample.components(separatedBy: " ")
var palindromes = 0

for word in array {
    if word == String(word.reversed()) {
        palindromes += 1
    }
}

print(palindromes)
```



## Question 5

You are given a string representing an **attendance record** for a student. The record only contains the following three characters:

`'A' : Absent.`

`'L' : Late.`

`'P' : Present.`

If a student has more than one 'A' or more than 2 continuous 'L's that student should not be rewarded. Print true if student is to be rewarded and False if they shouldn't.

Example:

Sample Input: `"PPALLP"`

Sample Output: `true`

```swift
var attendance = "PPALLP"
var numAbscences = 0
var reward = true

for status in attendance {
    if status == "A" {
        numAbscences += 1
    }
    if numAbscences > 1 || attendance.contains("LLL") {
        reward = false
        break
    }
}

print(reward)
```

## Question 6

Given a tuple with two strings. The first string is a **ransom note**, the second string being the characters from a magazine. Determine whether or not you can construct the ransom note using the characters from the magazine.

Each letter from the magazine can only be used once. You can assume all letters are lowercased.

Examples:

Sample Input1: `("a", "b")`

Sample Output1: `False`

Sample Input2: `("aa", "aab")`

Sample Output2: `True`
