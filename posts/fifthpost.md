---
title: Loops, Arrays and Objects
description: This is a post on My Blog about loops, arrays and objects.
date: 2022-04-04
tags: second tag
layout: layouts/post.njk
---
A loop outputing the 7 times table from 7 x 1 = 7 to 7 x 12 = 84

```diff-js
for (let i = 7, k = 1; k < 13; k++) {
  let i = 7 * k;
  console.log(`7 x ${k} = ${i}`);
}
```

An array of my favourite foods printing some of them to the screen

```diff-js
var favouriteFood = [`pasta`, `pizza`, `chicken`, `fish`, `vegetables`, `sushi`, `ice cream`, `oreo cookies`, `chips`, `hot dog`, `burger`];
console.log(favouriteFood [0]);
console.log(favouriteFood [1]);
console.log(favouriteFood [2]);
console.log(favouriteFood [5]);
console.log(favouriteFood [6]);
console.log(favouriteFood [7]);
console.log(favouriteFood [10]);
```

A for loop printing a list of all my favourite foods

```diff-js
var favouriteFood = [`pasta`, `pizza`, `chicken`, `fish`, `vegetables`, `sushi`, `ice cream`, `oreo cookies`, `chips`, `hot dog`, `burger`];
for (var name of favouriteFood){
  console.log(name);
}
```

An object holding information on my favourite recipe, displaying the properties on screen. A loop listing all the ingredients and directions.

```diff-js
var favoriteRecipe = {
  title: `Pizza with ripening ham and arugula`,
  servings: 2,
  ingredients: [`600 g of wheat flour`, `365 ml of warm water`, `25 g of fresh yeast`, `5 spoons of olive oil`, `1.5 teaspoon of salt`, `1 teaspoon of sugar`, `400 g of canned tomatoes`, `1 clove of garlic`, `1 teaspoon of dried oregano`, `freshly ground pepper`, `250 g of mozzarella cheese with pickle`, `100 g of ripening ham`, `2 handfuls of arugula`, `a few cherry tomatoes`],
  directions: [`Grate yeast with 1/3 cup of warm water, a tablespoon of flour and a teaspoon of sugar.`, `Leave leaven for 10-15 minutes in a warm place.`, `Sift the flour into a large bowl, add leaven, remaining water, olive oil and salt.`, `Knead dough - until it becomes elastic and smooth.`, `Cover the dough with a cloth and let it rise in a warm place for about 30 minutes.`, `Preheat an oven.`, `Knead the dough again, then divide it into 2 equal parts.`, `Stretch each part into a circle with a diameter of 30-35 cm.`, `In a small saucepan, heat the olive oil, then lightly fry fine chopped garlic.`, `Add canned tomatoes, season with salt, pepper and oregano.`, `Cook over low heat for about 10 minutes.`, `Blend sauce with a blender.`, `Smear bottoms with the sauce, leaving edges clean.`, `Sprinkle with torn mozzarella cheese over the entire surface.`, `Bake pizza for 5-8 minutes, until a rim of the dough is very golden.`, `After removing from the oven, put slices of ripening ham, halves of cherry tomatoes, sprinkle with arugula leaves.`]
}
console.log(`${favoriteRecipe.title} (for ${favoriteRecipe.servings})`);
console.log(`Ingredients:`);
for (var ingredient of favoriteRecipe.ingredients) {
  console.log(ingredient);
}
console.log(`Directions:`);
for (var direction of favoriteRecipe.directions) {
  console.log(direction);
}
```

A function called "letsCook" saying: "I'm hungry! Let's cook..." with the name of my recipe title.

```diff-js
var favoriteRecipe = {
  title: `pizza with ripening ham and arugula`,
  servings: 2,
  ingredients: [
    `600 g of wheat flour`,
    `365 ml of warm water`,
    `25 g of fresh yeast`,
    `5 spoons of olive oil`,
    `1.5 teaspoon of salt`,
    `1 teaspoon of sugar`,
    `400 g of canned tomatoes`,
    `1 clove of garlic`,
    `1 teaspoon of dried oregano`,
    `freshly ground pepper`,
    `250 g of mozzarella cheese with pickle`,
    `100 g of ripening ham`,
    `2 handfuls of arugula`,
    `a few cherry tomatoes`
  ],
  directions: [
    `Grate yeast with 1/3 cup of warm water, a tablespoon of flour and a teaspoon of sugar.`,
    `Leave leaven for 10-15 minutes in a warm place.`,
    `Sift the flour into a large bowl, add leaven, remaining water, olive oil and salt.`,
    `Knead dough - until it becomes elastic and smooth.`,
    `Cover the dough with a cloth and let it rise in a warm place for about 30 minutes.`,
    `Preheat an oven.`,
    `Knead the dough again, then divide it into 2 equal parts.`,
    `Stretch each part into a circle with a diameter of 30-35 cm.`,
    `In a small saucepan, heat the olive oil, then lightly fry fine chopped garlic.`,
    `Add canned tomatoes, season with salt, pepper and oregano.`,
    `Cook over low heat for about 10 minutes.`,
    `Blend sauce with a blender.`,
    `Smear bottoms with the sauce, leaving edges clean.`,
    `Sprinkle with torn mozzarella cheese over the entire surface.`,
    `Bake pizza for 5-8 minutes, until a rim of the dough is very golden.`,
    `After removing from the oven, put slices of ripening ham, halves of cherry tomatoes, sprinkle with arugula leaves.`
  ]
}
function letsCook(favoriteRecipe) {
  console.log(`I'm hungry! Let's cook ${favoriteRecipe.title}.`);
}
letsCook(favoriteRecipe);
```

## Shopping Cart

An array of objects providing a simple shopping cart example.

Working out the total cost of the items in the shopping cart.

Accounting for the quantity

```diff-js
var shoppingCart = [
  { name: "loaf of bread", type: "food", quantity: 1, price: 0.85 },
  { name: "multipack beans", type: "food", quantity: 1, price: 1 },
  { name: "mushrooms", type: "food", quantity: 10, price: 0.1 },
  { name: "can of beer", type: "alcohol", quantity: 4, price: 1.1 },
  { name: "prosecco", type: "alcohol", quantity: 1, price: 8.99 },
  { name: "steak", type: "food", quantity: 2, price: 3.99 },
  { name: "blue cheese", type: "food", quantity: 1, price: 2.99 },
  { name: "candles", type: "home", quantity: 3, price: 1.99 },
  { name: "cheesecake", type: "food", quantity: 1, price: 4.99 },
  { name: "onions", type: "food", quantity: 3, price: 0.4 }
];
console.log(`Total = ${totalPrice(shoppingCart)}`);
function totalPrice(shoppingCart) {
  let totalPrice = 0.0;
  for (let item of shoppingCart) {
    let subtotal = item.quantity * item.price;
    console.log(
      `${item.quantity} x ${item.name} @ £${item.price} = £${subtotal}`
    );
    totalPrice += subtotal;
  }
  return totalPrice;
}
```

20% discount for the item having a type of “food”

```diff-js
var shoppingCart = [
  { name: "loaf of bread", type: "food", quantity: 1, price: 0.85 },
  { name: "multipack beans", type: "food", quantity: 1, price: 1 },
  { name: "mushrooms", type: "food", quantity: 10, price: 0.1 },
  { name: "can of beer", type: "alcohol", quantity: 4, price: 1.1 },
  { name: "prosecco", type: "alcohol", quantity: 1, price: 8.99 },
  { name: "steak", type: "food", quantity: 2, price: 3.99 },
  { name: "blue cheese", type: "food", quantity: 1, price: 2.99 },
  { name: "candles", type: "home", quantity: 3, price: 1.99 },
  { name: "cheesecake", type: "food", quantity: 1, price: 4.99 },
  { name: "onions", type: "food", quantity: 3, price: 0.4 }
];
console.log(`Total = ${getTotal(shoppingCart)}`);
function getTotal(shoppingCart) {
  let totalPrice = 0.0;
  for (let item of shoppingCart) {
    const foodType = "food";
    let itemType = item.type;
    console.log(`type of item: ${item.name} is|are ${itemType}`);

    let subtotal = item.quantity * item.price;
    console.log(
      `${item.quantity} x ${item.name} @ £${item.price} = £${subtotal}`
    );

    if (itemType === foodType) {
      subtotal = applyDiscount(subtotal);
    }

    totalPrice += subtotal;
  }
  return totalPrice;
}

function getTotalFinite(shoppingCart) {
  let total = 0.0;
  for (let i = 0; i < shoppingCart.length; i++) {
    let item = shoppingCart[i];
    let subtotal = item.quantity * item.price;
    console.log(
      `${item.quantity} x ${item.name} @ £${item.price} = £${subtotal}`
    );
    total += subtotal;
  }

  return total;
}

function applyDiscount(subtotal) {
  const discount = 0.2;
  return subtotal * (1 - discount);
}
```

20% discount for the item having a type of “any”

```diff-js
var shoppingCart = [
  { name: "loaf of bread", type: "food", quantity: 1, price: 0.85 },
  { name: "multipack beans", type: "food", quantity: 1, price: 1 },
  { name: "mushrooms", type: "food", quantity: 10, price: 0.1 },
  { name: "can of beer", type: "alcohol", quantity: 4, price: 1.1 },
  { name: "prosecco", type: "alcohol", quantity: 1, price: 8.99 },
  { name: "steak", type: "food", quantity: 2, price: 3.99 },
  { name: "blue cheese", type: "food", quantity: 1, price: 2.99 },
  { name: "candles", type: "home", quantity: 3, price: 1.99 },
  { name: "cheesecake", type: "food", quantity: 1, price: 4.99 },
  { name: "onions", type: "food", quantity: 3, price: 0.4 }
];

const discountAmount = 20;
const type = "any";

console.log(`discount: ${discountAmount}%`);
console.log(getTotal(shoppingCart, type));

function getTotal(shoppingCart, discountedType) {
  let totalPrice = 0.0;
  for (let item of shoppingCart) {
    let itemType = item.type;
    console.log(`type of item: ${item.name} is|are ${itemType}`);

    subtotal = applyDiscount(discountedType, discountAmount, item);
    totalPrice += subtotal;
  }
  return totalPrice;
}

function getTotalFinite(shoppingCart) {
  let total = 0.0;
  for (let i = 0; i < shoppingCart.length; i++) {
    let item = shoppingCart[i];
    let subtotal = item.quantity * item.price;
    console.log(
      `${item.quantity} x ${item.name} @ £${item.price} = £${subtotal}`
    );
    total += subtotal;
  }

  return total;
}

function applyDiscount(discountedType, discountAmount, item) {
  let subtotal = item.quantity * item.price;

  if (discountedType == type || item.type == discountedType) {
    let discountRemainder = (100 - discountAmount) / 100;
    subtotal = subtotal * discountRemainder;
  }

  console.log(
    `${item.quantity} x ${item.name} @ £${item.price} = £${subtotal}`
  );
  return subtotal;
}
```

Working out which items cost between 2 price points (higher than or equal to £2 and lower than or equal to £5)

```diff-js
var shoppingCart = [
  { name: "loaf of bread", type: "food", quantity: 1, price: 0.85 },
  { name: "multipack beans", type: "food", quantity: 1, price: 1 },
  { name: "mushrooms", type: "food", quantity: 10, price: 0.1 },
  { name: "can of beer", type: "alcohol", quantity: 4, price: 1.1 },
  { name: "prosecco", type: "alcohol", quantity: 1, price: 8.99 },
  { name: "steak", type: "food", quantity: 2, price: 3.99 },
  { name: "blue cheese", type: "food", quantity: 1, price: 2.99 },
  { name: "candles", type: "home", quantity: 3, price: 1.99 },
  { name: "cheesecake", type: "food", quantity: 1, price: 4.99 },
  { name: "onions", type: "food", quantity: 3, price: 0.4 }
];

function range(cart, lowPrice, highPrice) {
  let arrItems = [];
  for (let item of cart) {
    if (lowPrice <= item.price && item.price <= highPrice) {
      arrItems.push(item);
    }
  }
  return arrItems;
}
console.log(range(shoppingCart, 2, 5));
```

Working out which items cost between 2 price points accounting for the quantity (higher than or equal to £2 and lower than or equal to £5)

```diff-js
var shoppingCart = [
  { name: "loaf of bread", type: "food", quantity: 1, price: 0.85 },
  { name: "multipack beans", type: "food", quantity: 1, price: 1 },
  { name: "mushrooms", type: "food", quantity: 10, price: 0.1 },
  { name: "can of beer", type: "alcohol", quantity: 4, price: 1.1 },
  { name: "prosecco", type: "alcohol", quantity: 1, price: 8.99 },
  { name: "steak", type: "food", quantity: 2, price: 3.99 },
  { name: "blue cheese", type: "food", quantity: 1, price: 2.99 },
  { name: "candles", type: "home", quantity: 3, price: 1.99 },
  { name: "cheesecake", type: "food", quantity: 1, price: 4.99 },
  { name: "onions", type: "food", quantity: 3, price: 0.4 }
];

function range(cart, lowPrice, highPrice, quantity) {
  let arrItems = [];
  for (let item of cart) {
    let price = item.price;
    if (quantity) {
      price *= item.quantity;
    }
    if (lowPrice <= price && highPrice >= price) {
      arrItems.push(item);
    }
  }
  return arrItems;
}
console.log(range(shoppingCart, 2, 5, true));
```