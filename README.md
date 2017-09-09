# Object Oriented Javascript
## Create Object 
There are multiple ways to create an object in Javascript. 

### First Way to Create Object 
```javascript 
// Create Object
var person = {
  name: 'Bob',
  age: 21,
  bio: function() {
    consoloe.log("Hi, I'm Bob");
  };
};
```

### Second Way to Create Object 
```javascript 
function Person(name, age) {
  this.name = name
  this.age = age;
  this.bio: function() {
    consoloe.log("Hi, I'm Bob");
  };
 };
}

// Create Object
var bob = new Person('Bob', 20);
```

### Third Way to Create Object
```javascript 
// Create Object
var person = new Object();

person.name = 'Bob';
person['age'] = 21;
person.greeting = function() {
  consoloe.log("Hi, I'm Bob");
};
```

### Fourth Way to Create Object 
```javascript 
// Create Object
var person = new Object({
  name: 'Bob',
  age: 21,
  greeting: function() {
    consoloe.log("Hi, I'm Bob");
  }
});
```

### Fifth Way to Create Object 
```swift
// Create Object
var newPerson = Object.create(person); // inheritance

newPerson.name
newPerson.greeting() // "Hi, I'm Bob"
```

### Fifth and Half Way to Create Object 
```javascript 
function Animal(name) {
    this.name = name;
}

Animal.prototype.sleep = function() {
    console.log(this.name + ': Zzz...');
}

function Dog(name) {
    this.name = name;
}

// Create a reference for the prototype
Dog.prototype = Object.create(new Animal());
```



### Sixth Way to Create Object 
```javascript 
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.greet = function() {
      console.log("Hi, I'm Bob")
    }
};

Person.prototype.introduce = function() {
  console.log("Hi, I'm Bob")
};

// Create Object
let bob = Person("Bob", 21)
bob.greet() // "Hi, I'm Bob"
bob.introduce() // "Hi, I'm Bob"
```


## Inheritance 

### Design Parernt
```javascript 
var Parent = function() {
    this.name = "Paremt";
}

Parent.prototype.print = function() {
    console.log(this.name);
}

var parent = new Parent();

parent.print(); // "Parent"
```

## Design Child
```javascript
var Child = function() {
    this.name = "Child";
    this.initial = "Jr.";
}
```

## Design Function
```javascript
var inheritsFrom = function (child, parent) {
    child.prototype = Object.create(parent.prototype);
};

inheritsFrom(Child, Parent);
```

### Method Available 
```javascript 
var son  = new Child();
son.print(); // "Child"
```

### Override Method
```javascript 
Child.prototype.print = function() {
    Parent.prototype.print.call(this);
    console.log(this.initial);
}

son.print() // "Jr."
```

### Child to Grand Child

```javascript
var GrandChild = function() {
    this.name = "Grand Child";
    this.initial = "JrJr.";
}

inheritsFrom(GrandChild, Child);
```

```javascript 
GrandChild.prototype.dance = function() {
  console.log("Let me dance for you, Bob")
}

GrandChild.prototype.print = function () {
    Child.prototype.print.call(this);
    console.log(this.initial);
}
```

```javascript 
var grandChild = new GrandChild();
grandChild.print(); // "JrJr."
```

## `Call`
```javascript
function Product(name, price) {
  this.name = name;
  this.price = price;
}

function Food(name, price) {
  Product.call(this, name, price);
  this.category = 'food';
}

function Toy(name, price) {
  Product.call(this, name, price);
  this.category = 'toy';
}

var cheese = new Food('feta', 5);
var fun = new Toy('robot', 40);
```
Another example of `call`

```javascript
function greet() {
  var reply = [this.person, 'is a', this.role].join(' ');
  console.log(reply);
}

var i = {
  person: 'Bob', 
  role: 'Javascript Developer'
};

greet.call(i); // Bob is a Javascript Developer
```

## `Apply()`
> `apply` is very similar to `call()`, except for the type of arguments it supports. You use an arguments array instead of a list of arguments (parameters). With `apply`, you can also use an `array` literal, for example, `func.apply(this, ['eat', 'bananas'])`, or an `Array` object, for example, `func.apply(this, new Array('eat', 'bananas'))`.
```javascript 
```

## `Bind()`
```javascript
this.x = 9;    // this refers to global "window" object here in the browser
var module = {
  x: 81,
  getX: function() { return this.x; }
};

module.getX(); // 81

var retrieveX = module.getX;
retrieveX();   
// returns 9 - The function gets invoked at the global scope
var boundGetX = retrieveX.bind(module);
boundGetX(); // 81
```


#### Need to Study More

> __proto__ is the actual object that is used in the lookup chain to resolve methods, etc. prototype is the object that is used to build __proto__ when you create an object with new:

```javascript 
( new Foo ).__proto__ === Foo.prototype
( new Foo ).prototype === undefined
```

``prototype` is a property of a Function object. It is the prototype of objects constructed by that function.


```javascript
function Point(x, y) {
    this.x = x;
    this.y = y;
}

var myPoint = new Point();

// the following are all true
myPoint.__proto__ == Point.prototype
myPoint.__proto__.__proto__ == Object.prototype
myPoint instanceof Point;
myPoint instanceof Object;
```

Here `Point` is a constructor function, it builds an object (data structure) procedurally. `myPoint` is an object constructed by `Point()` so `Point.prototype` gets saved to `myPoint.__proto__` at that time.







#### Study Materials: 
  - http://javascriptissexy.com/oop-in-javascript-what-you-need-to-know/
  - https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
  - https://www.thecodeship.com/web-development/methods-within-constructor-vs-prototype-in-javascript/
  - https://www.sitepoint.com/simple-inheritance-javascript/
  - http://archive.oreilly.com/oreillyschool/courses/advancedjavascript/Advanced%20JavaScript%20Essentials%20v1.pdf
  - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply
