# Prototypal Inheritance

## Learning Objectives
* Demonstrate a use case that explains prototypal inheritance
* Demonstrate what kind of flexibility prototypal inheritance gives programmers
* Explore Prototypal Inheritance
* Explore Inheritance with Classes and ES6
* Understand Prototype Constructor Patterns


## Opening
### Object Literals
  - We have worked with objects in Javascript. As a collection of properties associated with a name (key) and a value.
  - Thus far we have created and initialized objects like this:

```javascript
  var superman = {
     name: 'clark kent',
     superpower: 'flight'
  }
```

  - instantiating an object in this way is known as an **object literal**.

* Benefits of Object Literals.
  - They are simple and easy to read.
  - We have created a variable of superman who has a name and a super power.
  - Good to use when you need a simple container for data. Such as when we want to create a variable for the hero above.
  
* The case of Multiple Instances
  - But what happens when we have a team of superheroes like the X-men?
  - When we have an endless cast of rotating heroes it can be cumbersome and confusing literally instantiate an object for     each of these.

* Prototype and Constructor Pattern.
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

*  Prototypal (es5) Inheritance
```javascript
function Vehicle (name, type) {
  this.name = name;
  this.type = type;
};
 
Vehicle.prototype.getName = function getName () {
  return this.name;
};
 
Vehicle.prototype.getType = function getType () {
  return this.type;
};
function Car (name) {
  Vehicle.call(this, name, ‘car’);
}
Car.prototype = Object.create(Vehicle.prototype);
Car.prototype.constructor = Car;
Car.parent = Vehicle.prototype;
Car.prototype.getName = function () {
  return 'It is a car: '+ this.name;
};
var car = new Car('Tesla');
console.log(car.getName()); // It is a car: Tesla
console.log(car.getType()); // car
```

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

* ES6 Class Inheritence
```javascript
class Vehicle {
 
  constructor (name, type) {
    this.name = name;
    this.type = type;
  }
 
  getName () {
    return this.name;
  }
 
  getType () {
    return this.type;
  }
 
}
class Car extends Vehicle {
 
  constructor (name) {
    super(name, 'car');
  }
 
  getName () {
    return 'It is a car: ' + super.getName();
  }
 
}
let car = new Car('Tesla');
console.log(car.getName()); // It is a car: Tesla
console.log(car.getType()); // car
```
