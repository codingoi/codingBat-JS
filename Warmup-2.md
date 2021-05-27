# Warmup-2
A series of logic problems solved using <b>javascript</b>
<br>
Source: <em>https://the-winter.github.io/codingjs</em>

***

## stringTimes

Given a string and a non-negative int n, return a larger string that is n copies of the original string.

Examples

stringTimes('Hi', 2) → HiHi <br>
stringTimes('Hi', 3) → HiHiHi <br>
stringTimes('Hi', 1) → Hi <br>

```
function stringTimes(str, n){
  return str.repeat(n)
}
```

## frontTimes
Given a string and a non-negative int n, we'll say that the front of the string is the first 3 chars, or whatever is there if the string is less than length 3. Return n copies of the front.

Examples

frontTimes('Chocolate', 2) → ChoCho <br>
frontTimes('Chocolate', 3) → ChoChoCho <br>
frontTimes('Abc', 3) → AbcAbcAbc <br>

```
function frontTimes(str, n){
  let front = str.slice(0,3)
  return front.repeat(n)
}
```

## countXX

Count the number of 'xx' in the given string. We'll say that overlapping is allowed, so 'xxx' contains 2 'xx'.

Examples

countXX('abcxx') → 1 <br>
countXX('xxx') → 2 <br>
countXX('xxxx') → 3 <br>

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

doubleX('axxbb') → true <br>
doubleX('axaxax') → false <br>
doubleX('xxxxx') → true <br>

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

last2('hixxhi') → 1 <br>
last2('xaxxaxaxx') → 1 <br>
last2('axxaaxx') → 1 <br>

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

arrayCount9([1,2,9]) → 1 <br>
arrayCount9([1,9,9]) → 2 <br>
arrayCount9([1,9,9,3,9]) → 3 <br>

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

arrayFront9([1,2,9,3,4]) → true <br>
arrayFront9([1,2,3,4,9]) → false <br>
arrayFront9([1,2,3,4,5]) → false <br>

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

stringMatch('xxcaazz', 'xxbaaz') → 3 <br>
stringMatch('abc', 'abc') → 2 <br>
stringMatch('abc', 'axc') → 0 <br>

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

stringX('xxHxix') → xHix <br>
stringX('abxxxcd') → abcd <br>
stringX('xabxxxcdx') → xabcdx <br>

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
## altPairs

Given a string, return a string made of the chars at indexes 0,1, 4,5, 8,9 ... so "kittens" yields "kien".

Examples

altPairs('kitten') → kien <br>
altPairs('Chocolate') → Chole <br>
altPairs('CodingHorror') → Congrr <br>

```
function altPairs(str){
  let newStr = ""
  let alt
  let i = 0
  
  while(i < str.length){
    newStr += str[i]
    if(alt === 1) {alt = 3}
    else if(alt === 3 || alt === undefined){alt = 1}
    i += alt
  }
  return newStr
}
```

## stringYak

Suppose the string "yak" is unlucky. Given a string, return a version where all the "yak" are removed, but the "a" can be any char. The "yak" strings will not overlap.

Examples

stringYak('yakpak') → pak <br>
stringYak('pakyak') → pak <br>
stringYak('yak123ya') → 123ya <br>

```
function stringYak(str){
  return str.replaceAll('yak','')
}
```

## array667

Given an array of ints, return the number of times that two 6's are next to each other in the array. Also count instances where the second "6" is actually a 7.

Examples

array667([6,6,2]) → 1 <br>
array667([6,6,2,6]) → 1 <br>
array667([6,7,2,6]) → 1 <br>

```
function array667(nums){
  let counter = 0
  let i = 0
  while(i < nums.length){
    if(nums[i]===6 && (nums[i+1] === 6 || nums[i+1]===7)){
      counter++
    }

    i++
  }
  return counter
}
```
## noTriples

Given an array of ints, we'll say that a triple is a value appearing 3 times in a row in the array. Return true if the array does not contain any triples.

Examples

noTriples([1,1,2,2,1]) → true <br>
noTriples([1,1,2,2,2,1]) → false<br>
noTriples([1,1,2,2,2,1]) → false <br>

```
function noTriples(nums){
  let i = 0
  while(i <= nums.length-3){
    if(nums[i] === nums[i+1] && nums[i] === nums[i+2]){
      return false
    }
    i++
  }
  return true
}
```

## has271

Given an array of ints, return true if it contains a 2, 7, 1 pattern

Examples

has271([1,2,7,1]) → true <br>
has271([1,2,8,1]) → false <br>
has271([2,7,1]) → true <br>

```
function has271(nums){
  let i = nums.indexOf(2)
  while(i !== -1 && i < nums.length){
    if(nums[i+1] === 7 && nums[i+2] === 1){
      return true
    }
    i++
  }
  return false
}
```


