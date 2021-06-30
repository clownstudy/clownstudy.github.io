---
title: "Stop gninnipS My sdroW!"

categories:
    - CodeWar
tags:
    - codewar
    - algorithm
toc: true
toc_label: "목차"
toc_sticky: true
---
## Kata Description

Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (like the name of this kata).

- Strings passed in will consist of only letters and spaces.
- Spaces will be included only when more than one word is present.

**Examples:**

```
spinWords("Hey fellow warriors") => "Hey wollef sroirraw" 
spinWords("This is a test") => "This is a test" 
spinWords("This is another test") => "This is rehtona test"
```

## Best Practice

```javascript
function spinWords(words){
  return words.split(' ').map(function (word) {
    return (word.length > 4) ? word.split('').reverse().join('') : word;
  }).join(' ');
}
```

## Clever

```javascript
function spinWords(string){
  return string.replace(/\w{5,}/g, function(w) {
      return w.split('').reverse().join('') })
}
```



* 원본 배열을 수정하는 함수, 아닌 함수 따로 공부해야겠다.
* 정규표현식도 공부해야겠구나..

<details>
    <summary>
        <h2>내가 짠 그지 같은 코드</h2>
    </summary>
    <div markdown="1">
심히 부끄럽지만 남겨놓는다..
<pre>
function spinWords(string){
  let sep = string.split(' ');
  let newA = [];
  sep.forEach(s => {
    if (s.lenth >= 5) s = s.split('').reverse().join('');
    newA.push(s);
  })
  return newA.join('').toString();
}
</pre>
</div>
</details>



