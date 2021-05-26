# Warmup-1
A series of logic problems solved using <b>javascript</b>
<br>
Source: <em>https://the-winter.github.io/codingjs</em>

***

## sleepIn

The parameter weekday is true if it is a weekday, and the parameter vacation is true if we are on vacation. We sleep in if it is not a weekday or we're on vacation. Return true if we sleep in.

Examples

sleepIn(true, true) → true <br>
sleepIn(true, false) → false <br>
sleepIn(false, true) → true <br>

```
function sleepIn(weekday, vacation){
  if(vacation) {return true}
  if(!weekday) {return true}
  return false
}
```

## monkeyTrouble

We have two monkeys, a and b, and the parameters aSmile and bSmile indicate if each is smiling. We are in trouble if they are both smiling or if neither of them is smiling. Return true if we are in trouble.

Examples

monkeyTrouble(true, true) → true <br>
monkeyTrouble(false, false) → true <br>
monkeyTrouble(true, false) → false <br>

```
function monkeyTrouble(aSmile, bSmile){
  if(aSmile && bSmile) {return true}
  if(!aSmile && !bSmile) {return true}
  
  return false
}
```
 
## sumDouble

Given two int values, return their sum. Unless the two values are the same, then return double their sum.

Examples

sumDouble(1, 2) → 3 <br>
sumDouble(3, 2) → 5 <br>
sumDouble(2, 2) → 8 <br>

```
function sumDouble(a, b){
  if(a === b) {return a*4}
  
  return a+b
}
```

## diff21

Given an int n, return the absolute difference between n and 21, except return double the absolute difference if n is over 21.

Examples

diff21(19) → 2 <br>
diff21(10) → 11 <br>
diff21(21) → 0 <br>

```
function diff21(n){
  let absolute = Math.abs(n-21)
  if(n>21) {return absolute*2}
  return absolute
}
```
## parrotTrouble

We have a loud talking parrot. The "hour" parameter is the current hour time in the range 0..23. We are in trouble if the parrot is talking and the hour is before 7 or after 20. Return true if we are in trouble.

Examples

parrotTrouble(true, 6) → true <br>
parrotTrouble(true, 7) → false <br>
parrotTrouble(false, 6) → false <br>

```
function parrotTrouble(talking, hour){
  let sleeping = hour < 7 || hour > 20
  if(talking && sleeping) {return true}
  return false
}
```
## makes10

Given 2 ints, a and b, return true if one if them is 10 or if their sum is 10.

Examples

makes10(9, 10) → true <br>
makes10(9, 9) → false <br>
makes10(1, 9) → true <br>

```
function makes10(a, b){
  if(a === 10 || b === 10) {return true}
  if(a+b === 10){return true}
  return false
}
```
## nearHundred

Given an int n, return true if it is within 10 of 100 or 200. Note: Math.abs(num) computes the absolute value of a number.

Examples

nearHundred(93) → true <br>
nearHundred(90) → true <br>
nearHundred(89) → false <br>

```
function nearHundred(n){
  let oneHund = Math.abs(n-100)
  let twoHund = Math.abs(n-200)
   
  if(oneHund <=10 || twoHund <=10) {return true}
  return false 
}
```
## posNeg

Given 2 int values, return true if one is negative and one is positive. Except if the parameter "negative" is true, then return true only if both are negative.

Examples

posNeg(1, -1, false) → true <br>
posNeg(-1, 1, false) → true <br>
posNeg(-4, -5, true) → true <br>

```
function posNeg(a, b, negative){

  if(a < 0 && b < 0 && negative) {return true}
  if(a < 0 && b < 0 && !negative) {return false}
  if(!negative && (a < 0 || b < 0)) {return true}
  return false
}
```
## notString

Given a string, return a new string where "not " has been added to the front. However, if the string already begins with "not", return the string unchanged.

Examples

notString('candy') → not candy <br>
notString('x') → not x <br>
notString('not bad') → not bad <br>

```
function notString(str){
  let not = str.slice(0,3)
  if(not === "not") {return str}
  return "not " + str
}
```

## missingChar

Given a non-empty string and an int n, return a new string where the char at index n has been removed. The value of n will be a valid index of a char in the original string (i.e. n will be in the range 0..str.length()-1 inclusive).

Examples

missingChar('kitten', 1) → ktten <br>
missingChar('kitten', 0) → itten <br>
missingChar('kitten', 4) → kittn <br>

```
function missingChar(str, n){
  return str.slice(0,n) + str.slice(n+1) 
}
```

## frontBack

Given a string, return a new string where the first and last chars have been exchanged.

Examples

frontBack('code') → eodc <br>
frontBack('a') → a <br>
frontBack('ab') → ba <br>

```
function frontBack(str){
  // Code to handle str with 0 or 1 characters
  if(str.length === 0 || str.length === 1) {return str}
  // unmodified holds the chars that will not be swapped
  let unmodified = str.slice(1,-1)
  
  return str.slice(-1) + unmodified + str[0]
}
```
## front3

Given a string, we'll say that the front is the first 3 chars of the string. If the string length is less than 3, the front is whatever is there. Return a new string which is 3 copies of the front.

Examples

front3('Java') → JavJavJav <br>
front3('Chocolate') → ChoChoCho <br>
front3('abc') → abcabcabc <br>

```
function front3(str){
  let front = str.slice(0,3)
  return front + front + front
}
```
## backAround

Given a string, take the last char and return a new string with the last char added at the front and back, so 'cat' yields 'tcatt' The original string will be length 1 or more.

```
function backAround(str){
  let lastChar = str.slice(-1)
  return  lastChar + str + lastChar
}
```
## or35

Return true if the given non-negative number is a multiple of 3 or a multiple of 5. (Hint: Use the % 'mod' operator)

Examples

or35(3) → true <br>
or35(10) → true <br>
or35(8) → false <br>

```
function or35(n){
  if(n % 3 === 0 || n % 5 === 0) {return true}
  return false
}
```

## front22

Given a string, take the first 2 chars and return the string with the 2 chars added at both the front and back, so 'kitten' yields 'kikittenki' chars are there.

Examples

front22('kitten') → kikittenki <br>
front22('Ha') → HaHaHa <br>
front22('abc') → ababcab <br>

```
function front22(str){
  let twoChar = str.slice(0,2)
  return twoChar + str + twoChar
  
}
```

## startHi

Given a string, return true if the string starts with 'hi'and false otherwise.

Examples

startHi('hi there') → true <br>
startHi('hi') → true <br>
startHi('hello hi') → false <br>

```
function startHi(str){
  if(str.slice(0,2) === "hi") {return true}
  return false
}
```

## icyHot

Given two temperatures, return true if one is less than 0 and the other is greater than 100.

Examples

icyHot(120, -1) → true <br>
icyHot(-1, 120) → true <br>
icyHot(2, 120) → false <br>

```
function icyHot(temp1, temp2){
  
  let icy = temp1 < 0 || temp2 < 0
  let hot = temp1 > 100 || temp2 > 100
  
  if(icy && hot) {return true}
  return false
}
```
## in1020

Given 2 int values, return true if either of them is in the range 10..20 inclusive.

Examples

in1020(12, 99) → true <br>
in1020(21, 12) → true <br>
in1020(8, 99) → false <br>

```
function in1020(a, b){
  let aRange = a >= 10 && a <= 20
  let bRange = b >= 10 && b <= 20
  
  if(aRange || bRange) {return true}
  return false
}
```

## hasTeen

We'll say that a number is 'teen' if it is in the range 13..19 inclusive. Given 3 int values, return true if 1 or more of them are teen.

Examples

hasTeen(13, 20, 10) → true <br>
hasTeen(20, 19, 10) → true <br>
hasTeen(20, 10, 13) → true <br>

```
function hasTeen(a, b, c){
  let aIsTeen = a >= 13 && a <= 19
  let bIsTeen = b >= 13 && b <= 19
  let cIsTeen = c >= 13 && c <= 19
  
  if (aIsTeen || bIsTeen || cIsTeen) {return true}
  return false
  
}
```

## loneTeen

We'll say that a number is 'teen' if it is in the range 13..19 inclusive. Given 2 int values, return true if one or the other is teen, but not both.

Examples

loneTeen(13, 99) → true <br>
loneTeen(21, 19) → true <br>
loneTeen(13, 13) → false <br>

```
function loneTeen(a, b){
  let aTeen = a >= 13 && a <= 19
  let bTeen = b >= 13 && b <= 19
  
  if(aTeen && bTeen) {return false}
  else if(aTeen || bTeen) {return true}
  
  return false
}
```
## delDel

Given a string, if the string "del" appears starting at index 1, return a string where that "del" has been deleted. Otherwise, return the string unchanged.

Examples

delDel('adelbc') → abc <br>
delDel('adelHello') → aHello <br>
delDel('abcdel') → abcdel <br>

```
function delDel(str){
  if(str.slice(1,4) === "del") {return str.slice(0,1) + str.slice(4)}
  return str
  
}
```
## mixStart

Return true if the given string begins with 'mix', except the 'm' can be anything, so 'pix', '9ix' .. all count.

Examples

mixStart('mix snacks') → true <br>
mixStart('pix snacks') → true <br>
mixStart('piz snacks') → false <br>

```
function mixStart(str){
  if(str.slice(1,3) === "ix") {return true}
  return false
}
```

## startOz

Given a string, return a string made of the first 2 chars (if present), however include first char only if it is 'o' and include the second only if it is 'z', so 'ozymandias' yields 'oz'.

Examples

startOz('ozymandias') → oz <br>
startOz('bzoo') → z <br>
startOz('oxx') → o <br>

```
function startOz(str){
  let i = 0
  let newStr = ""
  
  while(i < 2) {
    if(str[i] === "o" && i === 0) {newStr += str[i]}
    if(str[i] === "z" && i === 1) {newStr += str[i]}
    i++
  }
  
  return newStr
}
```
## intMax

Given three int values, a b c, return the largest.

Examples

intMax(1, 2, 3) → 3 <br>
intMax(1, 3, 2) → 3 <br>
intMax(3, 2, 1) → 3 <br> 

```
function intMax(a, b, c){
  return Math.max(a,b,c)
}
```

## close10

Given 2 int values, return whichever value is nearest to the value 10, or return 0 in the event of a tie. Note that Math.abs(n) returns the absolute value of a number.

Examples

close10(8, 13) → 8 <br>
close10(13, 8) → 8 <br>
close10(13, 7) → 0 <br>

```
function close10(a, b){
  let aAbs = Math.abs(a-10)
  let bAbs = Math.abs(b-10)
  
  if(aAbs === bAbs) {return 0}
  if(aAbs < bAbs) {return a}
  else {return b}
}
```

## in3050

Given 2 int values, return true if they are both in the range 30..40 inclusive, or they are both in the range 40..50 inclusive.

Examples

in3050(30, 31) → true <br>
in3050(30, 41) → false <br>
in3050(40, 50) → true <br>

```
function in3050(a, b){
  let aRange30 = a >= 30 && a <= 40
  let aRange40 = a >= 40 && a <= 50
  
  let bRange30 = b >= 30 && b <= 40
  let bRange40 = b >= 40 && b <= 50
  
  if(aRange30 && bRange30) {return true}
  if(aRange40 && bRange40) {return true}
  return false
  
}
```

## max1020

Given 2 positive int values, return the larger value that is in the range 10..20 inclusive, or return 0 if neither is in that range.

Examples

max1020(11, 19) → 19 <br>
max1020(19, 11) → 19 <br>
max1020(11, 9) → 11 <br>

```
function max1020(a, b){
  let aRange = a >= 10 && a <= 20
  let bRange = b >= 10 && b <= 20
  
  if(aRange && bRange) {return Math.max(a,b)}
  if(!aRange && !bRange) {return 0}
  
  if(aRange) {return a}
  if(bRange) {return b}

}
```

## stringE

Return true if the given string contains between 1 and 3 'e' chars.

Examples

stringE('Hello') → true <br>
stringE('Heelle') → true <br>
stringE('Heelele') → false <br>

```
function stringE(str){
  
  const regex = /[e]/g;
  const found = str.match(regex)
  
  if(!found) {return false}
  if(found.length > 0 && found.length < 4) {return true}
  return false
  
}
```

### lastDigit

Given two non-negative int values, return true if they have the same last digit, such as with 27 and 57. Note that the % 'mod' operator computes remainders, so 17 % 10 is 7.

Examples

lastDigit(7, 17) → true <br>
lastDigit(6, 17) → false <br>
lastDigit(3, 113) → true <br>
 
```
function lastDigit(a, b, c){
  let aLast = a % 10
  let bLast = b % 10
  
  if(aLast === bLast) {return true}
  return false
}
```

## endUp

Given a string, return a new string where the last 3 chars are now in upper case. If the string has less than 3 chars, uppercase whatever is there. Note that str.toUpperCase() returns the uppercase version of a string.

Examples

endUp('Hello') → HeLLO <br>
endUp('hi there') → hi thERE <br>
endUp('hi') → HI <br>

```
function endUp(str){
  
  let newStr = str.slice(0,-3) + str.slice(-3).toUpperCase()
  return newStr
  
}
```
## everyNth

Given a non-empty string and an int N, return the string made starting with char 0, and then every Nth char of the string. So if N is 3, use char 0, 3, 6, ... and so on. N is 1 or more.

Examples

everyNth('Miracle', 2) → Mrce <br>
everyNth('abcdefg', 2) → aceg <br>
everyNth('abcdefg', 3) → adg <br>

```
function everyNth(str, n){
  let i = 0
  let newStr = ""
  
  while(i < str.length) {
    if(i % n === 0) {newStr += str[i]}
    i++
  }
  
 return newStr  
}
```
