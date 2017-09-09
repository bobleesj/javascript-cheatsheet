# object-oriented-javascript
Mastering Javascript OOP

Study Materials: 
  - http://javascriptissexy.com/oop-in-javascript-what-you-need-to-know/
  - https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
  

### First Way to Create Object 
```javascript 
var person = {
  name: 'Bob',
  age: 21,
  bio: function() {
    alert('I'm Bob');
  }
};
```

### Second Way to Create Object 
```javascript 
function Person(name, age) {
  this.name = {
    first,
    last
  };
  this.age = age;
  this.gender = gender;
  this.interests = interests;
  this.bio: function() {
    alert('I'm Bob');
  }
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

### Fitfh Way to Create Object 
```swift
var person2 = Object.create(person1); // inheritance
person2.name
person2.greeting()
```


