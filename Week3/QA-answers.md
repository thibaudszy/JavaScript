## Alex

---

**For function getActiveClasses() I’ve made this solution first**

```js
const getActiveClasses = () => {
  const activeClasses = {};
  classes.forEach((instance) => {
    if (instance.active) {
      activeClasses[instance.name] = getPeopleOfClass(instance.name);
    }
  });
  return activeClasses;
};
```

**but suddenly it doesn’t work, it return only one class instead of 3 as expected, so I’ve changed to**

```js
const activeClasses = {};
classes.forEach((instance) => {
  if (instance.active) {
    activeClasses[instance.name] = 1;
  }
});
for (let instance in activeClasses) {
  activeClasses[instance] = getPeopleOfClass(instance);
}
return activeClasses;
```

and it works for me. So my question is: could someone explain me what I’ve done wrong?

## Hikmet

---

Hi, There are test-reports in the homework section of Week3. In the files, there is a warning:’This test has not been run.' How can we run this test?

Go in the unit-tests directory and run:

### Answer

Run `npm run test`

## Mohamed Belal

---

"Is there any modern website made only with vanilla js without framework" is that possible ?, and if not how big websites like face book coded before inventing frameworks

### Answer

Booking is an example of a big, interactive website that works without a framework. Then it depends what yo mean by framework. A lot of websites are _server side generated_, meaning the html and css are created in the backend before being sent to the users. This is still done via frameworks, but they are not always JavaScript frameworks. In general, dynamic, interactive websites are often made with frameworks, static ones less so because it is not necessary.

## Sultan

---

What is the difference between named function and undefined function?
How to avoid from undefined value in function?

## Answer

Functions with no name are called anonymous functions. They work like regular functions but can't be reused.

## Mohanad AL Hasan

---

My question about `this` keyword , can I use this with all functions or just with functions as a method or property of an object?

### Answer

You can't use it in [arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions).

In functions declared with the `function` keyword and when in [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode), it depends how the function is called.

## Nuha Saleh

---

Is there any other way to check `if (something !== undefined)` inside function?

### Answer

Not if you only want to check if the value is specifically not `undefined`. However if you write `if(!something)`, this will check that the value is not [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)

## Basheer Ghaleb

---

is there any limits to use parameters in functions ??

### Answer

Not really, but don't go crazy ;)

## Mostafa Abdullah

---

As I knew the arrow function has given to us by ECMAScript and it's a replacement of the regular function, but the question is if will compare them together which one is the easiest and the much used from the programmers?

### Answer

The arrow function is not a replacement but an alternative. Both have their advantages and disadvantages. From [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

> An arrow function expression is a compact alternative to a traditional function expression, but is limited and can't be used in all situations.

I would say arrow functions are prefered to traditional functions when their limitations are not an issue. They also have the added benefit that when declared with the `const` keyword, they cannot be redeclared.

## Basheer Ghaleb

---

Is it necessary to specify let or const for a new variable inside a function?

```js
const array = ['item1', 'item2'];
function addToArray(arr, items) {
  newArray = [...array];
}
```

## Elif

---

Hi, how many nested functions can be used? Is there a limitation?

### Answer

Unless you start using [recursive functions](https://www.javascripttutorial.net/javascript-recursive-function/) (a function that calls itself), you won't run into this issue.

The limit depends on the environment. From a [quick search](https://stackoverflow.com/questions/7826992/browser-javascript-stack-size-limit), modern versions of chrome allow more than 13'903 calls. If you exceed it, you will run into a stack overflow error.

## Asiye Gokalp

---

```js
const myFunc=function(num){
  return function toDouble(){
    console.log(num\*2);
  }
}
console.log(myFunc(8)());
```

The above function can be invoked using two double brackets.
Invoking with two double brackets did not work for the following function.
what's the reason?

```js
function myName() {
  const name = 'Melisa';
  console.log(name);
  function sayHi() {
    console.log('Hello!');
  }
}
myName()();
```

### Answer

That's because you are not returning the function in the second example. So the `sayHi` function will be destroyed once the `myName` function finishes being executed.

## Badi

---

What is module scope?

Let's say you have two files:

`index.js`

```js
import getNumberPlusOne from `./getNumberPlusOne.js`

console.log(getNumberPlusOne(5));
```

`getNumberPlusOne.js`

```js
const moduleScopeVariable = 1;

export default (num) => num + moduleScopeVariable;
```

You are importing the function `getNumberPlusOne` in `index.js`, but for this function to run properly, it needs the value held in its module scope. However, even though you import the `getNumberPlusOne` module in `index.js`, you don't have access to the module's scoped variable outside of the `getNumberPlusOne` function.

## yusuf demir

---

Hello,

```js
const sendCongratulationsMessage = (name) => {
  console.log(`Congratulations ${name}, you passed the test. Well done!`);
};

const sendConsolidationMessage = (name) => {
  console.log(
    `Sorry ${name}, unfortunately you did not pass your test. Let's see what we can do to get you back on track`
  );
};

const sendResultMessage = (grade, ...rest) => {
  if (grade < 6) {
    sendConsolidationMessage(...rest);
  } else {
    sendCongratulationsMessage(...rest);
  }
};

sendResultMessage(5, 'John');
sendResultMessage(9, 'Deedee');
```

In this example, we have one parameter which called "name" and this is not an array. Why a spread operator was used for only one parameter?

## Answer

Because it is in an array. Learn more about the [function argument's object here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
