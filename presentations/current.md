## Lab goals

- Clarify DOM and its relationship with Javascript.
- Understand, and construct, data structure.
- Write more, if not better, functions.

---

The **Document Object Model (DOM)** provides a structured representation of the document.

![](https://images.duckduckgo.com/iu/?u=http%3A%2F%2F2.bp.blogspot.com%2F-uMWOLkKV8a8%2FT3ZsRGVeYOI%2FAAAAAAAAA40%2FuRein5dtTyk%2Fs1600%2FWeather%2BStormy%2BTree%2BMap%2B4.jpg&f=1)

---

The DOM defines a way for promrams to change

- document structure
- style
- content

~~~

The DOM provides a representation of the document as **a structured group of nodes and objects that have properties and methods**. Essentially, it connects web pages to scripts or programming languages.

```
var mom = document.createElement('h1'),
    julia = document.createTextNode('No idea where mom is!');

// mom has to find great great great...grandma
var ancestor = document.body;

// found mom
ancestor.appendChild(mom);
mom.appendChild(julia)

// just to make sure
console.log(julia.parentElement);
```

Read more about the DOM [here](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction).

~~~

### Can you show me the structure?

### [Yes](https://jueyang.github.io/get-crafty/illustrate).

~~~

### What?

### [Source code](https://github.com/jueyang/get-crafty/blob/gh-pages/illustrate)

---

## Ugh...it's broken.

~~~

## Find out why.

~~~

No one can do this for you expect for you and your BFF --

![](http://cl.ly/290h1f2z030E/Screen%20Shot%202016-02-18%20at%205.21.18%20PM.png)

Console/Developer Tool (Chrome). Use ** `cmd` + `opt` + `j` **.

~~~

### Now let's sabotage some code.

~~~

```
var name = 'tartar sause'.

alert(name);
```

~~~

HTML:

```
<h1>Did you know?</h1>
<p></p>
```

JS:

```
document.getElementById('name').innerText('The real name of grumpy cat is tartar sauce.')
```

~~~

### [Structure exercise](http://codepen.io/anon/pen/Qyorqv?editors=1011)

---

## JS 002

We  will use the Developer Tool in Chrome for a bit, then let's switch to [codepen](http://codepen.io) for the exercises.

---

### Data types

```
> 125
> '125'
> '125' + '5'
> 125 > 3
```

~~~

### Exercise

Define three varibles of each type respectively. Then check with `typeof(varible)`.

See all data types [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures).

---

### console.log

```
> console.log('please tell me the secret of life');
> x = 5;
> console.log(x);
```

~~~

## Tough love policy

No questions will be answered if you don't include an error message or some weird thing returned from your `console.log`.

---

# Data Structure

~~~

### Array

Switch to codepen now.

```
var mags = ['The New Yorker','Nautilus','N+1'];

console.log(mags);
console.log(mags.length);
console.log(mags.length(0));
```

~~~

#### push

```
mags.push('Bon Appetit');

console.log(mags);
```

~~~

#### forEach

```
mags.forEach(function(oneMag){
	console.log('I read ' + oneMag);
});
```

~~~

#### map

```
var numbers = [22,46,72];

var doubles = numbers.map(function(oneNumber){
	return oneNumber * 2;
});

var sentences = numbers.map(function(oneNumber, index){
	return oneNumber + ' has an index of ' + index	+ ' in this array.'
});

console.log(doubles);
console.log(sentences);
```

~~~

#### join

```
var words = ['what','a','wonderful','life'];

words.join();
words.join('');
words.join(' ');

console.log(words);
```

~~~

#### slice

```
partial = words.slice(1,3);

console.log(partial);
```

---

### String

```
var name = 'Barack Obama';

console.log(name.length)
console.log(name[7]);
```

~~~

#### substr

```
var firstName = name.substr(0,6);

console.log(firstName);
```

~~~

### Object

```
var favMag = {};

favMag.name = 'Nautilus';
favMag.genre = 'science';
favMag.interns = ['JoAnna Klein','Susie Neilson','Ankur Paliwal']
favMag.notinterns= [
	{"name":"John Steele", "role":"Publisher and Editorial Director"},
	{"name":"Michael Segal", "role":"Editor in Chief"},
	{"name":"Meehan Crist", "role":"Editor-at-Large"},
]

console.log(favMag);
console.log(favMag.interns);
```

---

### Function

```
function addTwoNumbers(num1,num2){
	return num1 + numb2
}

addNumbers(3,4);
```

~~~

#### callback

Briefly speaking, it's passing one function into another.

```
function addPumpkinsAfterCalculation(num1,num2,calculation){
	return calculation + ' pumpkins'
}

addPumpkinsAfterCalculation(4, 5, addTwoNumbers);
```

---

## Loop

[for Loop](http://codepen.io/anon/pen/yewwzY)

---

## Homework

~~~

1. Fork the [pen](http://codepen.io/anon/pen/obVdxJ) and finish the exercise.
2. Refactor your `js` files from homework 1.

~~~

To deliver:

1. Add an `<a>` in your homework's `index.html`, which links to the your fork of exercise.
2. Push your changes to the `refactor` branch of your repository (see notes on branching at the end).

~~~

### Goal

Get familiar with writing functions.

### How

- Write four calculating functions.
- Complete a fifth function that populates the html with a sentence describing the calculation. You've already done it - "when I add x and y I get z". But Unlike the previous homework, you are no longer constrained by the two varibles you defined. With this function, you can create content with combinations of ANY two numbers.
- Excecute the function once per type of calculation.

Read the instructions in [this semi-finished `js` file](https://gist.github.com/jueyang/62324823e479839d491f) and complete it. It walks you through re-writing your javascript.

---

### Branch it off

**So far you have been on one branch, `master`. You are going to work in a new branch because it lets you keep your original (working) version, while experimenting on a new one.

Create a new branch called `refactor`.

`git checkout -b refactor`

Check which branch you're on before you start working and before you push:

`git branch`

Push to a remote (new) branch

`git push origin refactor`
