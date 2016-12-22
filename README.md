# Prototypal Inheritance

## Learning Objectives
* Demonstrate a use case that explains prototypal inheritance
* Demonstrate what kind of flexibility prototypal inheritance gives programmers.
* Explore Prototypal Inheritance.
* Understand Prototype Constructor Patterns


## Opening
* Start with Object Literals
  - We have worked with objects in Javascript. As a collection of properties associated with a name (key) and a value.
  - Thus far we have created and initialized objects like this:

```javascript
  var superman = {
     name: 'clark kent',
     superpower: 'flight'
  }
```

  - This is known as object literals.

* Explain Benefits of one off objects.
  - This is simple and easy to read.
  - We have created a variable of superman who has a name and a super power.

* Explain Scenario of multiple objects.
  - But what happens when he have a team of superheroes like the X-men?
  - When we have a limitless cast of rotating heroes it can be cumbersome and confusing literally instantiate an object for each of these.

* Explain use case Prototypes and Constructor Pattern.
  - Prototypes to the rescue!
  Prototype, a prototype is an object used as a fallback source of properties. The prototype is the parent object. New objects *inherit* properties of the parent object (prototype).

  Buy Why?
    - Benefits... Saves memory, encapsulation.
    - The Prototype enables us to easily define methods to all instances while saving memory. The methods and properties applied to the prototype are advantageous because they are only stored in the memory once.

  Prototypes and constructors help us to save memory, to keep our code DRY.
  It also helps with Encapsulation, enclosing all the functionalities so that methods and properties are hidden from the rest of the application.
  - We cloak our superheroes from allowing the super powers falling into the wrong hands.
  So let's get into it:

## Introduction
* What is a Prototype?

```javascript
function Superhero () {}
​
Superhero.prototype.firstName = "Clark";
Superhero.prototype.lastName = "Kent";
Superhero.prototype.superPower = “Flight”;
};
​
​var superman = new Superhero () //​
console.log(superman.fullName()); // Clark Kent​
console.log(superman.superPower); // flight

```

* What is a Constructor?

```javascript
function Superhero(firstName, lastName, superPower) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.superPower = superPower;
};
var superman = new Superhero(‘Clark’, ‘Kent’, ‘Flight’);
var spiderman = new Superhero(‘Peter’, ‘Parker’, ‘Web Slinging’);

```

* Explain Benefits of this pattern.

* Encapsulation and Inheritance

* Explain Syntactical benefits of classes in JS.
ES6 classes are not something that is radically new: They mainly provide more convenient syntax to create old-school constructor functions.


```javascript
// Define a class like this
    class Point {
        constructor(x, y) {
            this.x = x;
            this.y = y;
        }
        toString() {
            return '(' + this.x + ', ' + this.y + ')';
        }
    }
    
function Superhero(firstName, lastName, superPower){

 // Add object properties like this
 this.firstName = firstName;
 this.lastName = lastName;
 this.superPower = superPower
}

// Add methods like this.  All Person objects will be able to invoke this
Superhero.prototype.speak = function(){
  alert("Howdy, my name is" + this.firstName + ‘  ‘ + this.lastName + ‘  is here to save the day!’ );
};

// Instantiate new objects with 'new'
let superman = new Superhero("Clark", “Kent”, “Flight”);
let batman = new Superhero("Bruce", "Wayne", "rich");
batman.speak();

```
