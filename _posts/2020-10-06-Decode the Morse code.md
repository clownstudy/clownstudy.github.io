---
title: "Decode the Morse code"

categories:
    - CodeWars
tags:
    - codewars
    - algorithm
toc: true
toc_label: "목차"
toc_sticky: true

---

## Kata Description

```
Part of Series 1/3

This kata is part of a series on the Morse code. After you solve this kata, you may move to the [next one](https://www.codewars.com/kata/decode-the-morse-code-advanced).
```

In this kata you have to write a simple [Morse code](https://en.wikipedia.org/wiki/Morse_code) decoder. While the Morse code is now mostly superseded by voice and digital data communication channels, it still has its use in some applications around the world.

The Morse code encodes every character as a sequence of "dots" and "dashes". For example, the letter `A` is coded as `·−`, letter `Q` is coded as `−−·−`, and digit `1` is coded as `·−−−−`. The Morse code is case-insensitive, traditionally capital letters are used. When the message is written in Morse code, a single space is used to separate the character codes and 3 spaces are used to separate words. For example, the message `HEY JUDE` in Morse code is `···· · −·−−  ·−−− ··− −·· ·`.

**NOTE:** Extra spaces before or after the code have no meaning and should be ignored.

In addition to letters, digits and some punctuation, there are some special service codes, the most notorious of those is the international distress signal [SOS](https://en.wikipedia.org/wiki/SOS) (that was first issued by [Titanic](https://en.wikipedia.org/wiki/RMS_Titanic)), that is coded as `···−−−···`. These special codes are treated as single special characters, and usually are transmitted as separate words.

Your task is to implement a function that would take the morse code as input and return a decoded human-readable string.

**Examples:**

```
decodeMorse('.... . -.--   .--- ..- -.. .')
//should return "HEY JUDE"
```

**NOTE:** For coding purposes you have to use ASCII characters `.` and `-`, not Unicode characters.

The Morse code table is preloaded for you as a dictionary, feel free to use it:

- Coffeescript/C++/Go/JavaScript/Julia/PHP/Python/Ruby/TypeScript: `MORSE_CODE['.--']`
- C#: `MorseCode.Get(".--")` (returns `string`)
- Elixir: `@morse_codes` variable (from `use MorseCode.Constants`). Ignore the unused variable warning for `morse_codes` because it's no longer used and kept only for old solutions.
- Elm: `MorseCodes.get : Dict String String`
- Haskell: `morseCodes ! ".--"` (Codes are in a `Map String String`)
- Java: `MorseCode.get(".--")`
- Kotlin: `MorseCode[".--"] ?: ""` or `MorseCode.getOrDefault(".--", "")`
- Rust: `MORSE_CODE`
- Scala: `morseCodes(".--")`
- Swift: `MorseCode[".--"] ?? ""` or `MorseCode[".--", default: ""]`

- C: provides parallel arrays, i.e. `morse[2] == "-.-"` for `ascii[2] == "C"`

- NASM: a table of pointers to the morsecodes, and a corresponding list of ascii symbols

All the test strings would contain valid Morse code, so you may skip checking for errors and exceptions. In C#, tests will fail if the solution code throws an exception, please keep that in mind. This is mostly because otherwise the engine would simply ignore the tests, resulting in a "valid" solution.

## Best Practice

```javascript
decodeMorse = function(morseCode){
  function decodeMorseLetter(letter) {
    return MORSE_CODE[letter];
  }
  function decodeMorseWord(word) {
    return word.split(' ').map(decodeMorseLetter).join('');
  }
  return morseCode.trim().split('   ').map(decodeMorseWord).join(' ');
}
// map 메서드 안에서 전달인자가 필요한 함수를 사용할 때, 전달인자를 따로 작성하지 않아도 되네.
// 하나의 작업에 여러 로직이 필요한 경우, 하나로 처리 하지 말고 함수 여러 개로 쪼개자. 
```

## Clever

```javascript
decodeMorse = function(morseCode){
  return morseCode
    .trim()
    .split(/  | /)
    .map( (code) => MORSE_CODE[code] || ' ')
    .join('');
}

// /  | / => space 2개 or 1개. 주어지는 morseCode에서는 문자를 구분하는 공백 하나와 단위를 구분하는 공백 3개로 이루어져있는데, space 3개짜리를 2개로 split하게 되면 '' 하나로 분리된다. 이걸 이용해서 5번째 라인의 map 메서드에서 MORSE_CODE[code] || ' ')로 space3개 짜리를 space 1개짜리로 치환하게 되는 것. 처음엔 왜 2개 1개로 쪼갰나 의문이 들었는데, split에 대해서 정확하게 알고 있지 않아서 였다.
```

<details>
    <summary>
        <h2>내가 짠 그지 같은 코드</h2>
    </summary>
    <div markdown="1">
심히 부끄럽지만 남겨놓는다..
<pre>
decodeMorse = function(morseCode){
  let reg = /^\s{0,}/g
  return morseCode.replace(reg,'').split('   ').map(x => x.split(' ').map(y => MORSE_CODE[y]).join('')).join(' ')
}
==============================================================================
** 처음에 NOTE를 제대로 안보고 처리했다가 예상 : [E, E], 결과 : [ E, E] .... 
** trim()은 앞 뒤만 처리한다... 왜 다 없애는걸로 생각했었을까. 굳이 정규표현식으로 replace를 사용하지 않아도 되었던 것.
** 이 전 kata에서 사람들이 map을 활용하는걸 봐서, 이번 kata에서 가능하다면 map으로 해결해보자 했는데.. 그 목적은 달성..
decodeMorse = function(morseCode){
  return morseCode.trim()
         .split('   ')
         .map(x => x.split(' ')
         .map(y => MORSE_CODE[y])
         .join('')).join(' ')
}
</pre>
    </div>
</details>







