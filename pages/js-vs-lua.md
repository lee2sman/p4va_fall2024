---
layout: page
title: Differences and "Gotchas" between Javascript and Lua
---

This post was prepared for students who are taking my p5.js (Javascript library) and Pico-8/Love2d (Lua) courses simultaneously. This isn't comprehensive but instead a quick cheat sheet to help avoid common misundertandings or pitfalls when learning these two languages.

## Global and local variables

### Javascript

Declare all global variables before your `setup()` so they can be accessed throughout your program.

### Lua

Usually you will declare your global variables inside `_init()` since all variables are by default global. To reset a game, you can just run init again. To specify a local variable to be used solely inside a function, you do it like this: `local var = 28` for example. 

## Built-in functions: draw() vs _update() and  _draw()

### Javascript

`draw()` is an infinitely running function by default. It runs approx 60 times a second.

### Lua

These two functions by default run 30 times a second: `_update()` function is where you should put math/instruction/button presses, etc. `_draw()` is where you should put code relating to drawing/graphics.

## Arrays

### Javascript

They start at index 0. To get the length of an array: arrayName.length

### Lua

In Lua, we build arrays with Tables. The array starts at index 1. To get the length, use the # symbol: `#arrayName`

## Loops

### Javascript

Since we start arrays at 0, we generally count starting at 0 and stopping 1 below the target number. In other words, we start counting from the 0 finger!

```js
for (i=0; i<10; i++){
  print(i)
}
```

### Lua

We start arrays at 1, so we count up from 1, ending on our target number. When we count on our fingers, we begin at 1 like we are used to. 

```lua
for i=1,10 do
  print(i)
end

--OR

for key, value in ipairs(arrayName) do
  print(key, value)
end
```

## Comparisons and Conditionals

### Javascript

```js
|| or
&& and
! not
// a comment


// ( ) are required around conditionals
if (age != 5){   //not equal to 
  print("you're not 5");
else if (age == 5) {
  print("You are 5!");
else {
  print("Impossible!);
}
```

### Lua

```lua
or
and
not
-- a comment

--no ( ) needed around conditionals
if age ~= 5 then  
  print("you're not 5")
elseif age==5 then
  print("You're 5 dude!")
else  --notice: no "then" here
  print("Not possible!")
end
```

## Object methods

### Javascript

```
foo.bar();  //run foo's method bar()
```

### Lua

```lua
foo:bar() //run foo's method bar()
```

## Anything else?

Let [Lee](https://faculty.purchase.edu/lee.tusman) know to add to this list.
