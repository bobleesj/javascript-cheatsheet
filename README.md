# object-oriented-javascript
Mastering Javascript OOP

Study Materials: 
  - http://javascriptissexy.com/oop-in-javascript-what-you-need-to-know/
  - https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
  - https://www.thecodeship.com/web-development/methods-within-constructor-vs-prototype-in-javascript/

### First Way to Create Object 
```javascript 
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

var bob = new Person('Bob', 20);
```

### Third Way to Create Object
```javascript 
var person1 = new Object();

person1.name = 'Bob';
person1['age'] = 21;
person1.greeting = function() {
  consoloe.log("Hi, I'm Bob");
};
```

### Fourth Way to Create Object 
```javascript 
var person1 = new Object({
  name: 'Bob',
  age: 21,
  greeting: function() {
    consoloe.log("Hi, I'm Bob");
  }
});
```

### Fifth Way to Create Object 
```swift
var person2 = Object.create(person1); // inheritance
person2.name
person2.greeting() // "Hi, I'm Bob"
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

let bob = Person("Bob", 21)
bob.greet() // "Hi, I'm Bob"
bob.introduce() // "Hi, I'm Bob"
```



