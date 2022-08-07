## Question

what the difference between `if` and `switch`? And when should I use `if` ? and when should I use `switch` ?

## Question

what is the diffrence please ?

```html
<video src="###"></video>
<!-- VS  -->
<video>
  <source src="s###" />
</video>
```

### Answer

[See the MDN documentation here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#usage_notes). Short answer:

> Browsers don't all support the same video formats; you can provide multiple sources inside nested <source> elements, and the browser will then use the first one it understands.

## Question

What is the difference between for and while loops ?

## Question

How can I clean the following text and find the most frequent word ?

```
 const sentence = '%I $am@% a %tea@cher%, &and& I lo%#ve %te@a@ching%;. The@re $is no@th@ing; &as& mo@re rewarding as educa@ting &and& @emp%o@weri@ng peo@ple. ;I found tea@ching m%o@re interesting tha@n any ot#her %jo@bs. %Do@es thi%s mo@tiv#ate yo@u to be a tea@cher!? %Th#is 30#Days&OfJavaScript &is al@so $the $resu@lt of &love& of tea&ching'
```

### Answer

[Answer here](https://codepen.io/thibaudszy/pen/BarpJKm?editors=0010). You can see the output of the console.logs in the browser console.
You can visualize the execution of this code [here](https://pythontutor.com/render.html#code=%20const%20sentence%20%3D%20'%25I%20%24am%40%25%20a%20%25tea%40cher%25,%20%26and%26%20I%20lo%25%23ve%20%25te%40a%40ching%25%3B.'%0A%20%0A%20const%20cleanSentence%20%3D%20sentence.replace%28/%5B%5EAa-zZ%7C%5Cs%5D/gi,%20''%29.toLowerCase%28%29%3B%0A%0Aconsole.log%28%7BcleanSentence%7D%29%3B%0A%0Aconst%20sentenceArray%20%3D%20cleanSentence.split%28'%20'%29%3B%0A%0Aconsole.log%28%7BsentenceArray%7D%29%0A%0Aconst%20repeatedWords%20%3D%20%7BmostCommonWord%3A%20null%7D%0A%0AsentenceArray.forEach%28word%20%3D%3E%20%7B%0A%20%20if%28repeatedWords%5Bword%5D%29%7B%0A%20%20%20%20repeatedWords%5Bword%5D%2B%3D1%3B%0A%20%20%7D%20else%20%7B%0A%20%20%20%20repeatedWords%5Bword%5D%3D1%3B%0A%20%20%7D%0A%20%20%0A%20%20if%28!repeatedWords.mostCommonWord%29%7B%0A%20%20%20%20repeatedWords.mostCommonWord%20%3D%20word%3B%0A%20%20%20%20return%3B%0A%20%20%7D%20%0A%20%20if%28repeatedWords%5Bword%5D%20%3E%20repeatedWords%5BrepeatedWords.mostCommonWord%5D%29%7B%0A%20%20%20%20repeatedWords.mostCommonWord%20%3D%20word%3B%0A%20%20%7D%0A%7D%29%0Aconsole.log%28%20repeatedWords%29%0Aconsole.log%28'The%20most%20common%20word%20is%3A',%20repeatedWords.mostCommonWord%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D&textReferences=falsey).

## Question

What is pass-by-reference? and What are the differences between pass-by-value and pass-by-reference?

### Answer

View an example of both [here](https://pythontutor.com/render.html#code=//%20pass%20by%20value%0Aconst%20add%20%3D%20%28a,b%29%3D%3Ea%2Bb%3B%0Aconst%20myVar%20%3D%201%3B%0Aconst%20sum%20%3D%20add%28myVar,%201%29%3B%0A%0Aconsole.log%28'myVar%3A',%20myVar,%20'%3B%20sum%3A',%20sum%29%3B%0A%0A//%20pass%20by%20reference%0A%0Aconst%20addOneToFirstElement%20%3D%20%28arr%29%20%3D%3E%20%7B%0A%20%20arr%5B0%5D%20%3D%201%3B%0A%20%20return%20arr%3B%0A%7D%0A%0Aconst%20myArr%20%3D%20%5B0,%201,%202%5D%3B%0Aconst%20newArr%20%3D%20addOneToFirstElement%28myArr%29%3B%0Aconsole.log%28'myArr%3A',%20myArr,%20'%3B%20newArr%3A',%20newArr%29%3B&cumulative=false&curInstr=13&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false).

Learn more in [this article](https://www.javascripttutorial.net/javascript-pass-by-value/#:~:text=JavaScript%20pass%2Dby%2Dvalue%20or%20pass%2Dby%2Dreference&text=It%20means%20that%20JavaScript%20copies,variables%20outside%20of%20the%20function.)

**In short:** when passing a primitive value to a function, that value will be copied and any change to it's value will not affect the variable it passed to the function's arguments. When passing an object to a function, you are passing the reference of that object, not the actual object. Therefore, the function can modify the properties of the object via its reference.

## Question

The thing that confuses me is that the first output is as an array as it should be, but the second output is as a string. Why is this output not an array?

```js
const myRecipe = { ingredients: ['4 eggs', '2 strips of bacon', '1 tsp salt/pepper'] };

console.log(myRecipe['ingredients']);

//Output:[ '4 eggs', '2 strips of bacon', '1 tsp salt/pepper' ]

for (let key in myRecipe) {
  console.log(key + ': ' + myRecipe[key]);
}
//Output:ingredients: 4 eggs,2 strips of bacon,1 tsp salt/pepper
```

### Answer

This is due to _type coercion_ when adding an array to a string. To do this, JS will convert the Array to a string using the [toString](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toString) method. You can learn more [here](https://github.com/weiqinl/You-Dont-Know-JS-CN/blob/master/types%20%26%20grammar/ch4.md#tostring).

If you want to print:

`ingredients: [ '4 eggs', '2 strips of bacon', '1 tsp salt/pepper' ]`

you should use:

```js
console.log(`${key}:`, myRecipe[key]);
```

## Question

Can we use the `break`, `continue` and `label` statements with all loops types? and what the best usage for each ?

## Question

What is the difference between contains() and includes()?

### Answer

- `contains`:

  > The contains() method of the Node interface returns a boolean value indicating whether a node is a descendant of a given node, that is the node itself, one of its direct children (childNodes), one of the children's direct children, and so on. [learn more](https://developer.mozilla.org/en-US/docs/Web/API/Node/contains)

  [What is a DOM node](https://dmitripavlutin.com/dom-node-element/)

  This method can only be used in the browser, as NodeJs does not have DOM nodes.

- `includes`:
  > The includes() method determines whether an array includes a certain value among its entries, returning true or false as appropriate. [learn more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)

## Question

I have some questions about Prototype? What is a prototype of object and array and etc.? And how does it work?

### Answer

Prototypes are the mechanism by which JavaScript objects inherit features from one another. In this article, we explain what a prototype is, how prototype chains work, and how a prototype for an object can be set.

[A good overview on MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes).

Why do primitive values have methods like objects. Because of [autoboxing](https://dev.to/benjaminmock/do-you-know-what-autoboxing-in-js-is-enl).

## Question

what is the differences between are global scope and local scope ?

## Question

```js
const car = {
  model: 'audi',
  year: '2020',
  gear: [1, 2, 3, 4, 5, 6],
};
for (let feature in car) {
  console.log(feature);
}
```

    When I run this code I can see the output is:

    ```
    model
    year
    car
    ```

    When I write:
    `console.log(feature.model)`
    the result is `undefined`!
    Also when I write : `console.log(feature.gear[0])`
    It gives me error!
    Why the first one's result is undefined and why it gives me error in second one?
    Also can I access "audi" use "feature" in for loop instead car.model?

### Answer

The `for...in statement` iterates over all enumerable properties of an object that are keyed by strings (ignoring ones keyed by Symbols), including inherited enumerable properties. [learn more about `for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in).

As you can see from your `console.log`, `feature` will take the value of the properties of the Object, not the values. There isn't a way to directly iterate over the values of an object. However, you can access the car property using your iterator:

```js
const car = {
  model: 'audi',
  year: '2020',
  gear: [1, 2, 3, 4, 5, 6],
};

for (let feature in car) {
  console.log(car[feature]);
}
```

## Question

When I run this code const `a = [8]`;
const `b = [10]`;
`console.log(a < b);` the result is false

### Answer

This is because JS compares arrays and objects by _reference_ and not by value. The reference is the object's location in the heap. To compare the values of two arrays, you have to compare the primitive values that are contained within them. Which can be complicated depending on the structure of your array.

## Question

Why their outputs are different?

```js
const arr = [1, 2, 3, 4, 5];
delete arr[0];
console.log(arr.length);

//Output: 5;

const arr = [1, 2, 3, 4, 5];
arr.splice(0, 1);
console.log(arr.length);

// Output: 4;
```

### Answer

[Let's see the answer in JStutor](https://pythontutor.com/render.html#code=const%20arr1%20%3D%20%5B1,%202,%203,%204,%205%5D%3B%0Adelete%20arr1%5B0%5D%3B%0Aconsole.log%28arr1.length%29%3B%0A%0A//Output%3A%205%3B%0A%0Aconst%20arr2%20%3D%20%5B1,%202,%203,%204,%205%5D%3B%0Aarr2.splice%280,%201%29%3B%0Aconsole.log%28arr2.length%29%3B&cumulative=false&curInstr=6&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false).

Although you _can_ use `delete` on arrays, you should avoid it as it can lead to unexpected results.
