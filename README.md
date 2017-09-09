# object-oriented-javascript
Mastering Javascript OOP

Study Materials: 
http://javascriptissexy.com/oop-in-javascript-what-you-need-to-know/


### Every javascript funciton has a prototype property

```javascript 
function PrintStuff (myDocuments) {
 this.documents = myDocuments;
}  
```


```javascript 
PrintStuff.prototype.print = function() {
  console.log(this.documents);
}
```

Create an object 

```javascript 
var newObj = new PrintStuff("I am a new Object and I can print.");
```

```javascript 
newObj.print()
```

### Implementing of Comibation Constructor/Prototype Pattern'

```javascript
	function User (theName, theEmail) {
    this.name = theName;
    this.email = theEmail;
    this.quizScores = [];
    this.currentScore = 0;
}
```

```javascript
	User.prototype = {
    constructor: User,
    saveScore:function (theScoreToAdd)  {
        this.quizScores.push(theScoreToAdd)
    },
    showNameAndScores:function ()  {
        var scores = this.quizScores.length > 0 ? this.quizScores.join(",") : "No Scores Yet";
        return this.name + " Scores: " + scores;
    },
    changeEmail:function (newEmail)  {
        this.email = newEmail;
        return "New Email Saved: " + this.email;
    }
}
```

```javascript
firstUser = new User("Richard", "Richard@examnple.com"); 
firstUser.changeEmail("RichardB@examnple.com");
firstUser.saveScore(15);
```


### Inheritance 
```javascript 
car cars = {
    type:"sedan",
    wheels:4​
};
```

```javascript
var toyota = Object.create (cars); // now toyota inherits the properties from cars
console.log(toyota.type); // sedan
```



### The primitive data type String is stored as a value​
var person = "Kobe";  
var anotherPerson = person; // anotherPerson = the value of person​
person = "Bryant"; // value of person changed​

console.log(anotherPerson); // Kobe
console.log(person); // Bryant

