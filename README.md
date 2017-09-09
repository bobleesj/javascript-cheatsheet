# object-oriented-javascript
Mastering Javascript OOP

Study Materials: 
  - http://javascriptissexy.com/oop-in-javascript-what-you-need-to-know/
  - https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
  

### First Way to Create Object 
```javascript 
var person = {
  name: ['Bob', 'Smith'],
  age: 32,
  gender: 'male',
  interests: ['music', 'skiing'],
  bio: function() {
    alert(this.name[0] + ' ' + this.name[1] + ' is ' + this.age + ' years old. He likes ' + this.interests[0] + ' and ' + this.interests[1] + '.');
  },
  greeting: function() {
    alert('Hi! I\'m ' + this.name[0] + '.');
  }
};
```

### Second Way to Create Object 
```javascript 
function Person(first, last, age, gender, interests) {
  this.name = {
    first,
    last
  };
  this.age = age;
  this.gender = gender;
  this.interests = interests;
  this.bio = function() {
    alert(this.name.first + ' ' + this.name.last + ' is ' + this.age + ' years old. He likes ' + this.interests[0] + ' and ' + this.interests[1] + '.');
  };
  this.greeting = function() {
    alert('Hi! I\'m ' + this.name.first + '.');
  };
}

var person1 = new Person('Bob', 'Smith', 32, 'male', ['music', 'skiing']);
```

### Third Way to Create Object
```javascript 
var person1 = new Object();
person1.name = 'Chris';
person1['age'] = 38;
person1.greeting = function() {
  alert('Hi! I\'m ' + this.name + '.');
};
```

### Fourth Way to Create Object 
```javascript 
var person1 = new Object({
  name: 'Chris',
  age: 38,
  greeting: function() {
    alert('Hi! I\'m ' + this.name + '.');
  }
});
```

### Fitfh Way to Create Object 
```swift
var person2 = Object.create(person1); // inheritance
person2.name
person2.greeting()
```


