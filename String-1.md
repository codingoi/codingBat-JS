# String-1
A series of logic problems solved using <b>javascript</b>
<br>
Source: <em>https://the-winter.github.io/codingjs</em>
***

## helloName

Given a string name, e.g. "Bob", return a greeting of the form "Hello Bob!".

Examples

helloName('Bob') → Hello Bob!<br>
helloName('Alice') → Hello Alice!<br>
helloName('X') → Hello X!<br>

```
 function helloName(name){
  return "Hello " + name +"!"
}
```

## makeAbba

Given two strings, a and b, return the result of putting them together in the order abba, e.g. "Hi" and "Bye" returns "HiByeByeHi".

Examples

makeAbba('Hi', 'Bye') → HiByeByeHi<br>
makeAbba('Yo', 'Alice') → YoAliceAliceYo<br>
makeAbba('What', 'Up') → WhatUpUpWhat<br>

```
function makeAbba(a, b){
  return a+b+b+a
}
```

## makeTags

The web is built with HTML strings like "<i>Yay</i>" which draws Yay as italic text. In this example, the "i" tag makes <i> and </i> which surround the word "Yay". Given tag and word strings, create the HTML string with tags around the word, e.g. "<i>Yay</i>".

Examples

makeTags('i', 'Yay') → Yay<br>
makeTags('i', 'Hello') → Hello<br>
makeTags('cite', 'Yay') → Yay<br>

```
function makeTags(tag, word){
  return `<${tag}>${word}</${tag}>`
}
```
## extraEnd

Given a string, return a new string made of 3 copies of the last 2 chars of the original string. The string length will be at least 2.

Examples

extraEnd('Hello') → lololo<br>
extraEnd('ab') → ababab<br>
extraEnd('Hi') → HiHiHi<br>

```
function extraEnd(str){
  return str.slice(-2).repeat(3)
}
```

## firstTwo

Given a string, return the string made of its first two chars, so the String "Hello" yields "He". If the string is shorter than length 2, return whatever there is, so "X" yields "X", and the empty string "" yields the empty string "". Note that str.length() returns the length of a string.

Examples

firstTwo('Hello') → He<br>
firstTwo('abcdefg') → ab<br>
firstTwo('ab') → ab<br>

```
function firstTwo(str){
  return str.slice(0,2)
}
```

## withoutEnd

Given a string, return a version without the first and last char, so "Hello" yields "ell". The string length will be at least 2.

Examples

withoutEnd('Hello') → ell<br>
withoutEnd('java') → av<br>
withoutEnd('coding') → odin<br>

```
function withoutEnd(str){
  return str.slice(1,str.length-1)
}
```

## comboString

Given 2 strings, a and b, return a string of the form short+long+short, with the shorter string on the outside and the longer string on the inside. The strings will not be the same length, but they may be empty (length 0).

Examples

comboString('Hello', 'hi') → hiHellohi<br>
comboString('Hi', 'Hello') → HiHelloHi<br>
comboString('aaa', 'b') → baaab<br>

```
function comboString(a, b){
  let aLen = a.length
  let bLen = b.length
  
  if(aLen > bLen) {return b + a + b}
  return a + b + a 
}
```

## nonStart

Given 2 strings, return their concatenation, except omit the first char of each. The strings will be at least length 1.

Examples

nonStart('Hello', 'There') → ellohere<br>
nonStart('java', 'code') → avaode<br>
nonStart('shotl', 'java') → hotlava<br>

```
function nonStart(a, b){
  return a.slice(1).concat(b.slice(1))
}
```
## left2

Given a string, return a "rotated left 2" version where the first 2 chars are moved to the end. The string length will be at least 2.

Examples

left2('Hello') → lloHe<br>
left2('java') → vaja<br>
left2('Hi') → Hi<br>

```
function left2(str){
  return str.slice(2) + str.slice(0,2)
}
```

## right2

Given a string, return a "rotated right 2" version where the last 2 chars are moved to the start. The string length will be at least 2.

Examples

right2('Hello') → loHel<br>
right2('java') → vaja<br>
right2('Hi') → Hi<br>

```
function right2(str){
  return str.slice(-2) + str.slice(0,-2)
}
```

## theEnd

Given a string, return a string length 1 from its front, unless front is false, in which case return a string length 1 from its back. The string will be non-empty.

Examples

theEnd('Hello', true) → H<br>
theEnd('Hello', false) → o<br>
theEnd('oh', true) → o<br>

```
function theEnd(str, front){
  if(front) {return str.slice(0,1)}
  return str.slice(-1)
}
```

## withoutEnd2

Given a string, return a version without both the first and last char of the string. The string may be any length, including 0.

Examples

withoutEnd2('Hello') → ell<br>
withoutEnd2('abc') → b<br>
withoutEnd2('ab') →  <br>

```
function withoutEnd2(str){
  return str.slice(1,-1)
}
```

## endsLy

Given a string, return true if it ends in "ly".

Examples

endsLy('oddly') → true<br>
endsLy('y') → false<br>
endsLy('oddl') → false<br>

```
function endsLy(str){
  if(str.slice(-2) === "ly"){return true}
  return false
}
```

## nTwice

Given a string and an int n, return a string made of the first and last n chars from the string. The string length will be at least n.

Examples

nTwice('hello', 2) → helo<br>
nTwice('Chocolate', 3) → Choate<br>
nTwice('Chocolate', 1) → Ce<br>

```
function nTwice(str, n){
  if(n === 0) {return ""}
  return str.slice(0,n) + str.slice(-n)
}
```

## twoChar

Given a string and an index, return a string length 2 starting at the given index. If the index is too big or too small to define a string length 2, use the first 2 chars. The string length will be at least 2.

Examples

twoChar('java', 0) → ja<br>
twoChar('java', 2) → va<br>
twoChar('java', 3) → ja<br>

```
function twoChar(str, index){
  let newStr= ""
  newStr += str.slice(index,index+2)
  if(newStr.length !== 2) {return str.slice(0,2)}
  return newStr
}
```

## middleThree

Given a string of odd length, return the string length 3 from its middle, so "Candy" yields "and". The string length will be at least 3.

Examples

middleThree('Candy') → and<br>
middleThree('and') → and<br>
middleThree('solving') → lvi<br>

```
function middleThree(str){
  let mid = Math.floor(str.length/2)
  
  return str.slice(mid-1, mid+2) 
}
```

## hasBad

Given a string, return true if "bad" appears starting at index 0 or 1 in the string, such as with "badxxx" or "xbadxx" but not "xxbadxx". The string may be any length, including 0.

Examples

hasBad('badxx') → true<br>
hasBad('xbadxx') → true<br>
hasBad('xxbadxx') → false<br>

```
function hasBad(str){
  let bad = "bad"
  let badSearch = str.slice(0,4).match(bad)
  if(badSearch !== null) {return true}
  return false 
}
```

## atFirst

Given a string, return a string length 2 made of its first 2 chars. If the string length is less than 2, use '@' for the missing chars.

Examples

atFirst('hello') → he<br>
atFirst('hi') → hi<br>
atFirst('h') → h@<br>

```
function atFirst(str){
  let newStr = str.slice(0,2)
  
  while(newStr.length < 2) {
    newStr += "@"
  }
  return newStr
}
```

## lastChars

Given 2 strings, a and b, return a new string made of the first char of a and the last char of b, so "yo" and "java" yields "ya". If either string is length 0, use '@' for its missing char.

Examples

lastChars('last', 'chars') → ls<br>
lastChars('yo', 'java') → ya<br>
lastChars('hi', '') → h<br>

```
function lastChars(a, b){
  let first = a.slice(0,1) || "@"
  let last = b.slice(-1) || "@"
  
  return first+last
}
```

## conCat

Given two strings, append them together (known as "concatenation") and return the result. However, if the concatenation creates a double-char, then omit one of the chars, so "abc" and "cat" yields "abcat".

Examples

conCat('abc', 'cat') → abcat<br>
conCat('dog', 'cat') → dogcat<br>
conCat('abc', '') → abc<br>

```
function conCat(a, b){
  let last = a.slice(-1)
  let first = b.slice(0,1)
  
  if(last !== first) {return a+b}
  return a.slice(0,-1) + b
}
```

## lastTwo

Given a string of any length, return a new string where the last 2 chars, if present, are swapped, so "coding" yields "codign".

Examples

lastTwo('coding') → codign<br>
lastTwo('cat') → cta<br>
lastTwo('ab') → ba<br>

```
function lastTwo(str){
  let base = str.slice(0,-2)
  
  return base + str.slice(-1) + str.slice(-2,-1)
}
```

## seeColor

Given a string, if the string begins with "red" or "blue" return that color string, otherwise return the empty string.

Examples

seeColor('redxx') → red<br>
seeColor('xxred') →   <br>
seeColor('blueTimes') → blue <br>

```
function seeColor(str){  
  if(str.slice(0,4).includes("blue")){return "blue"}
  if(str.slice(0,3).includes("red")){return "red"}
  return ""
}
```

## frontAgain

Given a string, return true if the first 2 chars in the string also appear at the end of the string, such as with "edited".

Examples

frontAgain('edited') → true<br>
frontAgain('edit') → false<br>
frontAgain('ed') → true<br>

```
function frontAgain(str){
  if(str.length === 0 || str.length === 1){return false}
  if(str.slice(0,2) === str.slice(-2)){return true}
  return false
}
```

## minCat

Given two strings, append them together (known as "concatenation") and return the result. However, if the strings are different lengths, omit chars from the longer string so it is the same length as the shorter string. So "Hello" and "Hi" yield "loHi". The strings may be any length.

Examples

minCat('Hello', 'Hi') → loHi<br>
minCat('Hello', 'java') → ellojava<br>
minCat('java', 'Hello') → javaello<br>

```
function minCat(a, b){
  let aLen = a.length
  let bLen = b.length
  
  if(aLen === 0 || bLen === 0){return ""}
  if(aLen === bLen){return a+b}
  
  if(aLen > bLen){return a.slice(-bLen)+b}
  return a + b.slice(-aLen)
}
```
## extraFront

Given a string, return a new string made of 3 copies of the first 2 chars of the original string. The string may be any length. If there are fewer than 2 chars, use whatever is there.

Examples

extraFront('Hello') → HeHeHe<br>
extraFront('ab') → ababab<br>
extraFront('H') → HHH<br>

```
function extraFront(str){
  return str.slice(0,2).repeat(3)
}
```
## without2

String-1 -- without2
Given a string, if a length 2 substring appears at both its beginning and end, return a string without the substring at the beginning, so "HelloHe" yields "lloHe". The substring may overlap with itself, so "Hi" yields "". Otherwise, return the original string unchanged.

Examples

without2('HelloHe') → lloHe<br>
without2('HelloHi') → HelloHi<br>
without2('Hi') →   <br>

```
function without2(str){
  if(str.length === 1) {return str}
  if(str.slice(0,2) === str.slice(-2)){return str.slice(2)}
  return str
}
```

## deFront

Given a string, return a version without the first 2 chars. Except keep the first char if it is 'a' and keep the second char if it is 'b'. The string may be any length. Harder than it looks.

Examples

deFront('Hello') → llo<br>
deFront('java') → va<br>
deFront('away') → aay<br>

```
function deFront(str){
  let i = 0
  let newStr = ""
  
  if(str[0] ==="a"){newStr = "a"}
  if(str[1] === "b"){newStr += "b"}
  newStr += str.slice(2)
  
  return newStr
}
```

## startWord

Given a string and a second "word" string, we'll say that the word matches the string if it appears at the front of the string, except its first char does not need to match exactly. On a match, return the front of the string, or otherwise return the empty string. So, so with the string "hippo" the word "hi" returns "hi" and "xip" returns "hip". The word will be at least length 1.

Examples

startWord('hippo', 'hi') → hi<br>
startWord('hippo', 'xip') → hip<br>
startWord('hippo', 'i') → h<br>

```
function startWord(str, word){ 
  if(word.length === 1){return str.slice(0,word.length)}
  if(str.slice(1,word.length) === word.slice(-word.length+1)){return str.slice(0,word.length)}
  return ""
}
```

## withoutX

Given a string, if the first or last chars are 'x', return the string without those 'x' chars, and otherwise return the string unchanged.

Examples

withoutX('xHix') → Hi<br>
withoutX('xHi') → Hi<br>
withoutX('Hxix') → Hxi<br>

```
function withoutX(str){
    let newStr = ""
    let i = 0
    while(i < str.length){
      if(i === 0 && str[i] === "x"){newStr += ""}
      else if(i === str.length-1 && str[i] === "x"){newStr += ""}
      else {newStr += str[i]}
      i++
    }
  return newStr
}
```

## withoutX2

Given a string, if one or both of the first 2 chars is 'x', return the string without those 'x' chars, and otherwise return the string unchanged. This is a little harder than it looks.

Examples

withoutX2('xHi') → Hi<br>
withoutX2('Hxi') → Hi<br>
withoutX2('Hi') → Hi<br>

```
function withoutX2(str){
  
  let newStr = ""
  
  if(str.length === 0) {return ""}
  if(str.length === 1 && str[0] === "x"){return ""}
  if(str[0] === "x" || str[0] === ""){newStr = ""} else {newStr += str[0]}
  if(str[1] === "x" || str[1] === ""){newStr += ""} else {newStr += str[1]}
  newStr += str.slice(2)
  return newStr
}
```

















