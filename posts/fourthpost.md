---
title: Tip program
description: This is a post on My Blog about making a JavaScript program to calculate a tip.
date: 2018-09-30
tags: second tag
layout: layouts/post.njk
---
1. Create variables for the pre-tip total and the tip percentage.

const preTipTotal = 11;                                             
var tip = preTipTotal * 0.15;

2. Calculate the new total.

var postTipTotal = preTipTotal + tip;

3. Display the tip amount in the output rounding the figure to 2 decimal places.

<p id="tip"></p>
document.getElementById("tip").innerHTML =
'tip amount: £' + tip.toFixed(2);

4. Display the total bill amount in the output rounding the figure to 2 decimal places.

<p id="payment"></p>
document.getElementById("payment").innerHTML =
'"Your total bill, with tip, is £' + postTipTotal.toFixed(2) + '."';

To sum up:

<h1>Tip program</h1>
   <p id="tip"></p>
   <p id="payment"></p>
   <script>
      const preTipTotal = 11;                                             
      var tip = preTipTotal * 0.15;                                   // Assign the product of pre_tipTotal and 15% to tip
      var postTipTotal = preTipTotal + tip;                           // Assign the sum of preTipTotal and tip to postTipTotal
      document.getElementById("tip").innerHTML =
'tip amount: £' + tip.toFixed(2);                                        
      document.getElementById("payment").innerHTML =
'"Your total bill, with tip, is £' + postTipTotal.toFixed(2) + '."';
   </script>