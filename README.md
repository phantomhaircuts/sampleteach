# Javascript Classes

## Learning Objectives
* Illustrate the importance of OOP.
* Explore Javascript Classes
* Create instances using the keyword **new**

## Opening
### Object Literals
  - We have worked with objects in Javascript. As a collection of properties associated with  key value pairs.
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
  - When we have an endless cast of rotating heroes it can be cumbersome, confusing, and tedius to literally instantiate literal objects for each of these.

* Classes!
  - **Classes** to the rescue!
  **Classes**, Classes are "special functions”, which serve as blueprints for objects and methods.

  But Why and What for?
* A class enables us to easily define methods to all instances while saving memory. The methods and properties applied to the class are advantageous because they are only stored in the memory once.

* Classes help us to save memory, to keep our code DRY.
 * It also helps with Encapsulation, enclosing all the functionalities so that methods and properties are hidden from the rest of the application.
  - Encapsulation... We cloak our superheroes methods and properties from allowing the super powers falling into the wrong hands.

## Introduction
* Classes and Constructors?

```javascript
//ES6...

class Superhero {
  constructor(firstName, lastName, superPower){
    this.firstName = firstName;
    this.lastName = lastName;
    this.superPower = superPower;
  }
  speak(){
     console.log(this.firstName + " " + this.lastName + "  is here to save the day with my " + this.superPower + "!" );
  }
}

let superman = new Superhero("Clark", "Kent", "Flight");
let batman = new Superhero("Bruce", "Wayne", "money");
let wonderwoman = new Superhero("Diana", "Prince", "Super Strength");
batman.speak();
superman.speak();
wonderwoman.speak();


//ES5...

function Superhero(firstName, lastName, superPower){

 // Add object properties like this
 this.firstName = firstName;
 this.lastName = lastName;
 this.superPower = superPower
}

// Add methods like this.  All Person objects will be able to invoke this
Superhero.prototype.speak = function(){
  console.log(this.firstName + " " + this.lastName + "  is here to save the day with my " + this.superPower + "!" );
};

// Instantiate new objects with 'new'
let superman = new Superhero("Clark", "Kent", "Flight");
let batman = new Superhero("Bruce", "Wayne", "money");
let wonderwoman = new Superhero("Diana", "Prince", "Super Strength");
batman.speak();
superman.speak();
wonderwoman.speak();

```
