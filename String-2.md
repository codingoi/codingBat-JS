## doubleChar

Given a string, return a string where for every char in the original, there are two chars.

Examples

doubleChar('The') → TThhee <br>
doubleChar('AAbb') → AAAAbbbb<br>
doubleChar('Hi-There') → HHii--TThheerree<br>

Solution 1

```
function doubleChar(str){
   return str.split("").map((char)=> char+char).join("")
}
```
Solution 2

```
function doubleChar(str){
  let newStr = ""
  let i = 0
  while(i<str.length){
    newStr += str[i].repeat(2)
    i++
  }
  
  return newStr
}
```

## countHi

Return the number of times that the string "hi" appears anywhere in the given string.

Examples

countHi('abc hi ho') → 1<br>
countHi('ABChi hi') → 2<br>
countHi('hihi') → 2<br>

```
function countHi(str){
  let results = str.match(/hi/g)
  if(results){return results.length}
  return 0                     
}
```

## catDog

Return true if the string "cat" and "dog" appear the same number of times in the given string.

Examples

catDog('catdog') → true<br>
catDog('catcat') → false<br>
catDog('1cat1cadodog') → true<br>

```
function catDog(str){
  let cat = str.match(/cat/g)
  let dog = str.match(/dog/g)
  
  if(!cat && !dog){return true}
  if(cat && dog){
    if(cat.length == dog.length){return true}
  }
  return false
}
```

## countCode

Return the number of times that the string "code" appears anywhere in the given string, except we'll accept any letter for the 'd', so "cope" and "cooe" count.

Examples

countCode('aaacodebbb') → 1<br>
countCode('codexxcode') → 2<br>
countCode('cozexxcope') → 2<br>

```
function countCode(str){
  let results = str.match(/co[a-z]e/g)
  
  if(results){return results.length}
  return 0
}
```

## endOther

Given two strings, return true if either of the strings appears at the very end of the other string, ignoring upper/lower case differences (in other words, the computation should not be "case sensitive"). Note: str.toLowerCase() returns the lowercase version of a string.

Examples

endOther('Hiabc', 'abc') → true<br>
endOther('AbC', 'HiaBc') → true<br>
endOther('abc', 'abXabc') → true<br>

```
function endOther(a, b){
  
  let aEnd = a.slice(-b.length).toLowerCase()
  let bEnd = b.slice(-a.length).toLowerCase()
  
  if(aEnd === bEnd){return true}
  return false
}
```

## xyzThere

Return true if the given string contains an appearance of "xyz" where the xyz is not directly preceeded by a period (.). So "xxyz" counts but "x.xyz" does not.

Examples

xyzThere('abcxyz') → true<br>
xyzThere('abc.xyz') → false<br>
xyzThere('xyz.abc') → true<br>

```
function xyzThere(str){
  let results_1 = str.match(/(?<!.)xyz/)
  let results_2 = str.match(/[^.]xyz/)
  
  if(results_1) {return true}
  if(results_2) {return true}

  return false
}
```

## bobThere

Return true if the given string contains a "bob" string, but where the middle 'o' char can be any char.

Examples

bobThere('abcbob') → true<br>
bobThere('b9b') → true<br>
bobThere('bac') → false<br>

```
function bobThere(str){
  if(str.match(/b[a-z0-9]b/g){return true}
  return false
}
```

## xyBalance

We'll say that a String is xy-balanced if for all the 'x' chars in the string, there exists a 'y' char somewhere later in the string. So "xxy" is balanced, but "xyx" is not. One 'y' can balance multiple 'x's. Return true if the given string is xy-balanced.

Examples

xyBalance('aaxbby') → true<br>
xyBalance('aaxbb') → false<br>
xyBalance('yaaxbb') → false<br>

```
function xyBalance(str){
  let counter = 0
  let i = 0
  
  while(i < str.length){
    if(str[i] === "x") {counter++}
    if(str[i] === "y") {counter = 0}
    i++
  }
  
  if(counter === 0){return true}
  return false 
}
```

## mixString

Given two strings, a and b, create a bigger string made of the first char of a, the first char of b, the second char of a, the second char of b, and so on. Any leftover chars go at the end of the result.

Examples

mixString('abc', 'xyz') → axbycz<br>
mixString('Hi', 'There') → HTihere<br>
mixString('xxxx', 'There') → xTxhxexre<br>

```
function mixString(a, b){
  let i = 0
  let newStr = ""
  
  while(i < a.length || i < b.length){
    newStr += a[i] || ""
    newStr += b[i] || ""
    i++
  }
  
  return newStr
}
```

## repeatEnd

Given a string and an int n, return a string made of n repetitions of the last n characters of the string. You may assume that n is between 0 and the length of the string, inclusive.

Examples

repeatEnd('Hello', 3) → llollollo<br>
repeatEnd('Hello', 2) → lolo<br>
repeatEnd('Hello', 1) → o<br>

```
function repeatEnd(str, n){
  return str.slice(-n).repeat(n)
}
```

## repeatFront

Given a string and an int n, return a string made of the first n characters of the string, followed by the first n-1 characters of the string, and so on. You may assume that n is between 0 and the length of the string, inclusive (i.e. n >= 0 and n <= str.length()).

Examples

repeatFront('Chocolate', 4) → ChocChoChC<br>
repeatFront('Chocolate', 3) → ChoChC<br>
repeatFront('Ice Cream', 2) → IcI<br>

```
function repeatFront(str, n){
  let i = n
  let newStr = ""
  
  while(i>=0) {
    newStr += str.slice(0,i)
    i--
  }
  return newStr
}
```

## repeatSeparator

Given two strings, word and a separator sep, return a big string made of count occurrences of the word, separated by the separator string.

Examples

repeatSeparator('Word', 'X', 3) → WordXWordXWord<br>
repeatSeparator('This', 'And', 2) → ThisAndThis<br>
repeatSeparator('This', 'And', 1) → This<br>

```
function repeatSeparator(word, sep, count){
  let wordCount = count
  let sepCount = count-1
  let newStr = ""
  
  
  while(wordCount > 0 || sepCount > 0) {
    if(wordCount){newStr += word}
    if(sepCount){newStr += sep}
    wordCount--
    sepCount--
  }
  return newStr
}
```

## prefixAgain

Given a string, consider the prefix string made of the first N chars of the string. Does that prefix string appear somewhere else in the string? Assume that the string is not empty and that N is in the range 1..str.length().

Examples

prefixAgain('abXYabc', 1) → true<br>
prefixAgain('abXYabc', 2) → true<br>
prefixAgain('abXYabc', 3) → false<br>

```
function prefixAgain(str, n){
  let prefix = str.slice(0,n)
  let search = str.slice(n).match(prefix)
  
  if(search){return true}
  return false
}
```
## getSandwich

A sandwich is two pieces of bread with something in between. Return the string that is between the first and last appearance of "bread" in the given string, or return the empty string "" if there are not two pieces of bread.

Examples

getSandwich('breadjambread') → jam<br>
getSandwich('xxbreadjambreadyy') → jam<br>
getSandwich('xxbreadyy') →<br>

```
function getSandwich(str){
  let breadLen = "bread".length
  
  let firstBreadInd = str.indexOf("bread")
  
  if(firstBreadInd === -1){return ""}
  else{
  
  let lastBreadInd = str.lastIndexOf("bread")   
  let strBtwn = str.slice(firstBreadInd+breadLen, lastBreadInd)
  return strBtwn
  } 
}
```
## sameStarChar

Returns true if for every '*' (star) in the string, if there are chars both immediately before and after the star, they are the same.

Examples

sameStarChar('xy*yzz') → true<br>
sameStarChar('xy*zzz') → false<br>
sameStarChar('*xa*az') → true<br>

```
function sameStarChar(str){
  let bool = false
  let i = 0
  
  while(i<str.length){
    if(str[i] === "*"){
      if(i===0 || i === str.length-1){i++}
      else if(str[i-1] !== str[i+1]){return false}
    }
    i++
    }
    return true
  }
}
```

## oneTwo

Given a string, compute a new string by moving the first char to come after the next two chars, so "abc" yields "bca". Repeat this process for each subsequent group of 3 chars, so "abcdef" yields "bcaefd". Ignore any group of fewer than 3 chars at the end.

Examples

oneTwo('abc') → bca <br>
oneTwo('tca') → cat <br>
oneTwo('tcagdo') → catdog <br>

```
function oneTwo(str){
  let i = 0
  let holder = []
  
  while(i<str.length){
    if(str[i+2]){
    holder.push(str[i+1], str[i+2], str[i])
    }
    i+=3
  }
  
  return holder.join("")
}
```
## zipZap

Look for patterns like "zip" and "zap" in the string -- length-3, starting with 'z' and ending with 'p'. Return a string where for all such words, the middle letter is gone, so "zipXzap" yields "zpXzp".

Examples

zipZap('zipXzap') → zpXzp <br>
zipZap('zopzop') → zpzp <br>
zipZap('zzzopzop') → zzzpzp <br>

```
function zipZap(str){
  let regexRepl = 'zp'
  let regexOg = /z[a-z]p/ig
  return str.replaceAll(regexOg, regexRepl)
  
}
```

## starOut

Return a version of the given string, where for every star (*) in the string the star and the chars immediately to its left and right are gone. So "ab*cd" yields "ad" and "ab**cd" also yields "ad".

Examples

starOut('ab*cd') → ad <br>
starOut('ab**cd') → ad <br>
starOut('sm*eilly') → silly <br>

```
function starOut(str){
  let regex = /[a-z]?[*]+[a-z]?/g 
  let  word = str.replaceAll(regex,"")
  return word
}
```








