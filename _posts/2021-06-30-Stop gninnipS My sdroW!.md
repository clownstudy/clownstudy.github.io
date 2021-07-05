---
title: "Stop gninnipS My sdroW!"

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

Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.

**Examples:**

```
The binary representation of `1234` is `10011010010`, so the function should return `5` in this case

n == 4 -> 100 ==> 1
n == 8 -> 1000 ==> 1
n == 9 -> 1001 ==> 2
```

## Best Practice && Clever

```javascript
countBits = n => n.toString(2).split('0').join('').length;
```

## Others

```javascript
function countBits(n) {
  for(c=0;n;n>>=1)c+=n&1
  return c;
}

var countBits = function(n) {
  var count = 0;
  while(n > 0){
    if(n%2 === 1) {
      count++;
    }
    n = Math.floor(n/2);
  }
  return count;
};

const countBits = n => n.toString(2)
                        .split('')
                        .filter(ele => ele == 1)
                        .length
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
var countBits = function(n) {
  let cnt = 0;
  let arr = n.toString(2).split('');
  arr.map((x)=>{x==1?cnt++:0})
  return cnt
};
// map이 아니라 걸러내는거기 때문에 filter로 썼어도 되지 않았을까..
// 애초에 0으로 split하면 1만남는걸 생각 했었더라면..
</pre>
</div>
</details>



