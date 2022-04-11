---
title: Function and Control Flow
description: This is a post on My Blog about function and control flow in JavaScript.
date: 2018-08-24
tags:
  - second tag
  - posts with two tags
layout: layouts/post.njk
---
An invoked function outputing a sentence

```diff-js
function sentence(){
  console.log(`Hello, World!`);
}
sentence();
```

A program combining a first name and a last name as arguments inside a function

```diff-js
function fullName(firstName,lastName){
  console.log(`${firstName} ${lastName}`);
}
fullName(`Andrzej`,`Zaczynski`);
```

The "name" function with an added return statement used for setting the value of a variable

```diff-js
function fullName(firstName,lastName){
  return firstName + ` ` + lastName;
}
  console.log(fullName(`Andrzej`,`Zaczynski`));
```

"Shall I wear a coat?" program

```diff-js
var temperature = 51;

if(temperature >= 30 && temperature < 50){
  console.log(`Wear a coat.`);
}
else if(temperature >= 0 && temperature < 30){
  console.log(`Wear a coat and a hat.`);
}
else if(temperature < 0){
  console.log(`Stay inside.`);
}
else{
  console.log(`Just pants and vest is fine.`);
}
```