---
title: "Does my number look big in this?"

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

A [Narcissistic Number](https://en.wikipedia.org/wiki/Narcissistic_number) is a positive number which is the sum of its own digits, each raised to the power of the number of digits in a given base. In this Kata, we will restrict ourselves to decimal (base 10).

The Challenge:

Your code must return **true or false** depending upon whether the given number is a Narcissistic number in base 10.

Error checking for text strings or other invalid inputs is not required, only valid positive non-zero integers will be passed into the function.

**Examples:**

```
153 (3 digits), which is narcisstic:
1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153

1652 (4 digits), which isn't:
1^4 + 6^4 + 5^4 + 2^4 = 1 + 1296 + 625 + 16 = 1938
```

## Best Practice && Clever

```javascript
function narcissistic( value ) {
  return ('' + value).split('').reduce(function(p, c){
    return p + Math.pow(c, ('' + value).length)
    }, 0) == value;
}
```

## Others

```javascript
function narcissistic(value) {
  return value.toString()
              .split('')
              .map( (x,i,arr) => x ** arr.length)
              .reduce( (a,b)=> +a + +b) 
               === value
}

narcissistic = num => num.toString().split("").reduce(function(prev,el) { return prev + Math.pow(el, String(num).length)},0)  == num;

function narcissistic(number) {
    var arrayOfDigitals = number.toString().split(''),
        numberLength = arrayOfDigitals.length,
        sum = 0;

    arrayOfDigitals.forEach(function(digit) {
        sum += Math.pow(digit, numberLength);
    });

    return sum === number;
}
```



* Number => String 변환 시 toString()을 하지 않고, '' + string 으로 처리하는 경우가 많음.
* 상위 solution은 reduce를 주로 사용하는 경향이 있음. 

<details>
    <summary>
        <h2>내가 짠 그지 같은 코드</h2>
    </summary>
    <div markdown="1">
심히 부끄럽지만 남겨놓는다..
<pre>
function narcissistic(value) {
  value = value.toString();
  let calc = 0;
  for(i=0;i＜value.length;i++){
    calc += Math.pow(value[i],value.length)
  }
  return value == calc
}
</pre>
</div>
</details>



