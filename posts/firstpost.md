---
title: Pseudocode
description: This is a post on My Blog about pseudocode.
date: 2018-05-01
tags:
  - another tag
layout: layouts/post.njk
---
```diff-js
/* 
  Keep track of which books you read and which books you want to read!
  
  Create an array of objects, where each object describes a book and has 
  properties for the title (a string), author (a string), and already read (a 
  boolean indicating if you read it yet).
  
  Iterate through the array of books. For each book, log the book title and 
  book author like so: ‘“The Hobbit” by J.R.R. Tolkien’.
  
  Now use an if/else statement to change the output depending on 
  whether you read it yet or not. If you read it, log a string like ‘You already 
  read “The Hobbit” by J.R.R. Tolkien’, and if not, log a string like ‘You still 
  need to read “The Lord of the Rings” by J.R.R. Tolkien’.
  
  ______________________________________________________________________________
  
  A book has a title, an author and a flag for whether it has been read.
  There is a list of different books that have the properties title, author, read (yes\no).
  
  FOR the books on the list
    IF book has been read
      PRINT `You already read `bookTitle` by `bookAuthor`.`
    ELSE
      PRINT `You still need to read `bookTitle` by `bookAuthor`.`
  END
*/

let book = `bookTitle` && `bookAuthor` && (`yes` || `no`);

if (book = `yes`){
  console.log(`You already read ${`bookTitle`} by ${`bookAuthor`}.`);
}
else (book = `no`)
  console.log(`You still need to read ${`bookTitle`} by ${`bookAuthor`}.`);
```