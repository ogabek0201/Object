# <center>JavaScript lesson#5</center>

<p align="center">

<img src="https://img.shields.io/badge/Made%20by-Ogabek-yellow" >

<img src="https://img.shields.io/badge/Methods-Object-brown">

<img src="https://img.shields.io/badge/Keyword-this-brown">

<img src="https://img.shields.io/badge/Learn-Javascript-black">

</p>

---

 _<center>JavaScript object is a non-primitive data-type that allows you to store multiple collections of data.</center>_

```js
// object
const student = {
    firstName: 'Ogabek',
    class: 10
};
```

__Each member of an object is a key: value pair separated by commas and enclosed in curly braces {}.__

```js
const person = { name: 'Ogabek', age: 16 };
```

##### _`Name` and `age` are `keys`, and `Object` and `16` are `values` respectively._

#### objects can also contain functions

```js
// object containing method
const person = {
    name: 'Ogabek',
    heloo: function() { console.log('hello'); }
};
```

##### _A person `object` has two keys (`name` and `hello`), which have a string value and a function value, respectively._

### Hence basically, the JavaScript method is an object property that has a function value

---

# _<center>Object methods</center>_

### ENTERIES()

```
The Object.entries () method returns an array of a given
object's own enumerable string keyed property [key,value] pairs.
```

#### __enteries()__

```js
let obj={
  name:'Ogabek',
  age:16,
  work:false
}
console.log(object.enteries(obj));//[['name','Ogabek'],['age','16'],['work','false']]
```

### KEYS()

```
The Object.keys () method returns an array of a given
object's own enumerable property names, iterated in
the same order that a normal loop would.
```

#### __keys()__

```js
let obj={
  name:'Ogabek',
  age:16
}
console.log(object.key(obj));//['name','age']
```

### VALUES()

```
The Object.values() method returns an array of a given
object's own enumerable property values.
```

#### __values()__

```js
let obj={
  name:'Ogabek',
  age:16
}
console.log(object.values(obj));//['Ogabek','16']
```

---

# _<center>Keyword `this`</center>_
>
>`To access a property of an object from within a method of the same object, you need to use the`this`keyword.In order to access the properties of an object,`this`keyword is used following by`.`and`key`.`

```js
const person = {
    name: 'Ogabek',
    age: 16,
    hello: function() {
        let surname = 'Barotov';
        console.log('The name is' + ' ' + this.name + ' ' + surname); }
};

person.hello();//The name is Ogabek Barotov
```

>__Note:__ In JavaScript, `this` keyword when used with the object's method refers to the object. `this` is bound to an object.

---

### <center>`this` methods</center>

#### BIND()

>`The bind() method allows an object to borrow a method from another object without copying.`

```js
// object definition
const student1 = {
  name: "Jack",
  introduction: function (score) {
    console.log(this.name + "scored " + score + " in an exam.");
  },
};
// object definition
const student2 = {
  name: "Jimmy ",
};
console.log(student1.introduction.bind(student2,95));//Jimmy scored 95 in an exam.
```

#### APPLY()

>`The apply() method calls a function with the passed this keyword value and arguments provided in the form of an array.`

```JS
let color1 = ["Red", "Green", "Blue"];
let color2 = ["Yellow", "Black"];

// appending two arrays color1 and color2
color1.push.apply(color1, color2);

console.log(color1);//[ 'Red', 'Green', 'Blue', 'Yellow', 'Black' ]
```

#### CALL()

>`The call() method calls a function by passing this and specified values as arguments.`
```JS
// object definition
const human = {
  firstName: "Judah",
  lastName: "Parker",
  age: 26,
};

// function definition
function greet() {
  const string = `My name is ${this.firstName} ${this.lastName}. I am ${this.age} years old.`;
  console.log(string);
}

// passing object as this value in call() method
greet.call(human);//My name is Judah Parker. I am 26 years old.
```
>__Note:__ The difference between __call()__ and __apply()__ is that __call()__ accepts an argument list, while __apply()__ accepts a single array of arguments.

---