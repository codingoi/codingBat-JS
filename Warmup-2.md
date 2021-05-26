# Warmup-2
A series of logic problems solved using <b>javascript</b>
<br>
Source: <em>https://the-winter.github.io/codingjs</em>

***

## stringTimes

Given a string and a non-negative int n, return a larger string that is n copies of the original string.

Examples

stringTimes('Hi', 2) → HiHi
stringTimes('Hi', 3) → HiHiHi
stringTimes('Hi', 1) → Hi
Solve (ctrl-enter)

```
function stringTimes(str, n){
  return str.repeat(n)
}
```

## frontTimes
Given a string and a non-negative int n, we'll say that the front of the string is the first 3 chars, or whatever is there if the string is less than length 3. Return n copies of the front.

Examples

frontTimes('Chocolate', 2) → ChoCho
frontTimes('Chocolate', 3) → ChoChoCho
frontTimes('Abc', 3) → AbcAbcAbc

```
function frontTimes(str, n){
  let front = str.slice(0,3)
  return front.repeat(n)
}
```

## countXX

Count the number of 'xx' in the given string. We'll say that overlapping is allowed, so 'xxx' contains 2 'xx'.

Examples

countXX('abcxx') → 1
countXX('xxx') → 2
countXX('xxxx') → 3

```
function countXX(str){
  let i = 0
  let counter = 0
   
  while(i < str.length) {
    if(str[i] === "x" && str[i+1] === "x") {counter++}
     i++
  }
  return counter  
}
```

## doubleX

Given a string, return true if the first instance of "x" in the string is immediately followed by another "x".

Examples

doubleX('axxbb') → true
doubleX('axaxax') → false
doubleX('xxxxx') → true

```
function doubleX(str){
  let indexof = str.indexOf("x")
  if(indexof === -1) {return false}
  if(str[indexof+1] === "x"){return true}
  return false
}
```

## last2

Given a string, return the count of the number of times that a substring length 2 appears in the string and also as the last 2 chars of the string, so "hixxxhi" yields 1 (we won't count the end substring).

Examples

last2('hixxhi') → 1
last2('xaxxaxaxx') → 1
last2('axxaaxx') → 1

```
function last2(str){
  let lastChars = str.slice(-2)
  let base = str.slice(0,-2)
  
  let counter = 0
  
  let i = 0
    
  while(i < base.length) {
  if(base[i]+base[i+1] === lastChars) {counter++}
  i++
  }
  return counter
}
```
## arrayCount9
Given an array of ints, return the number of 9's in the array.

Examples

arrayCount9([1,2,9]) → 1
arrayCount9([1,9,9]) → 2
arrayCount9([1,9,9,3,9]) → 3

```
function arrayCount9(nums){
 let i = 0
 let counter = 0
 
 return nums.filter((ele)=>ele === 9).length || 0
}
```

## arrayFront9
Given an array of ints, return true if one of the first 4 elements in the array is a 9. The array length may be less than 4.

Examples

arrayFront9([1,2,9,3,4]) → true
arrayFront9([1,2,3,4,9]) → false
arrayFront9([1,2,3,4,5]) → false

```
function arrayFront9(nums){
  let i = 0
  while(i < 4) {
    if(nums[i] === 9) {return true}
    i++
  }
  return false
}
```

## stringMatch

Given 2 strings, a and b, return the number of the positions where they contain the same length 2 substring. So "xxcaazz" and "xxbaaz" yields 3, since the "xx" "xx", "aa", and "az" substrings appear in the same place in both strings.

Examples

stringMatch('xxcaazz', 'xxbaaz') → 3
stringMatch('abc', 'abc') → 2
stringMatch('abc', 'axc') → 0

```
function stringMatch(a, b){
  let i = 0
  let aCombo = ""
  let bCombo = ""
  
  let counter = 0
  
  while(i<a.length-1){
    aCombo = a[i] + a[i+1]
    bCombo = b[i] + b[i+1]
    
    if(aCombo === bCombo) {counter++}
    
    i++
  }
  
  return counter
}
```

## stringX

Given a string, return a version where all the "x" have been removed. Except an "x" at the very start or end should not be removed.

Examples

stringX('xxHxix') → xHix
stringX('abxxxcd') → abcd
stringX('xabxxxcdx') → xabcdx

```
function stringX(str){
  let i = 0
  let newStr = ""
  
  while(i<str.length){
   if(i === 0 && str[i] === "x") {newStr += "x"}
   if(i === str.length-1 && str[str.length-1] === "x") {newStr += "x"}
   if(str[i] !== "x") {newStr += str[i]}
   i++
  }
  
  return newStr
}
```
