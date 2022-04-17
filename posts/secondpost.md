---
title: Intro to JavaScript practicals
description: This is a post on My Blog about intro to JavaScript practicals.
date: 2018-07-04
tags:
  - number 2
layout: layouts/post.njk
---
Percentage Calculator program

```diff-js
function percentageCalculator(number,percentage){
  var output = number * (percentage/100);
  return output;  
}
var value = percentageCalculator(135,30);
console.log(value);
```

Switch Statement program

```diff-js
function drinkOrder(size,buttonName){
  let drinkName;
  switch(buttonName){
    case `lemon`:
      drinkName = `lemonade`;
      break;
    case `orange`:
      drinkName = `orangeade`;
      break;
    case `cola`:
      drinkName = `cola`;
      break;
  }
  return `You have ordered a ${size} ${drinkName}.`;
}
console.log(drinkOrder(`medium`,`orange`));
```

Calculator program

```diff-js
function calculator(number1,number2,operator){
  var message;
  var value;
  switch(operator){
    case `+`:
      value = number1 + number2;
      break;
    case `-`:
      value = number1 - number2;
      break;
    case `*`:
      value = number1 * number2;
      break;
    case `/`:
      value = number1 / number2;
      break;
    case `%`:
      value = number1 % number2;
      break;      
  }
  return message = `${number1} ${operator} ${number2} = ${value}`;
}
console.log(calculator(1,2,`+`));
```