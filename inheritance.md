Inheritance
-----------



### Let's refactor using inheritance

```dart [1-5 | 7-9 | 11-13 | 15-17 | 19-25]
class Animal {
  void breathe() {
    print('Inhale exhale!');
  }
}

class Dog extends Animal {

}

class Cat extends Animal {

}

class Horse extends Animal {

}

// main.dart
final dog = Dog();
final cat = Cat();
final horse = Horse();
dog.breathe();
cat.breathe();
horse.breathe();
```

Dog, Cat, and Horse copied (**inherited**) the `breathe` method from Animal!



### corgo iz much pleasd

![dry](images/dry.jpg)

Inheritance allows us to reuse code from another class, and stay DRY.



### Terminologies

* __Inheritance__ is the mechanism of basing a class upon another class, _retaining similar 
  implementation_. 
  - one of the three pillars of OOP
* Animal is a **superclass**
  - base class or parent class in some languages/books
  - you can also tell by the _keyword_ they're using
    + C# `base`
    + PHP `parent`
* Dog, Cat, and Horse are **subclass**es
  - a.k.a. derived class, child class



### Should you inherit if the implementation is the same?

```dart
class Ventilator extends Animal {

}

// main.dart
final vent = Ventilator();
vent.breathe();
```

A Ventilator extends an animal('s life)?

Ventilator extends Animal!  Genius!

Don't rely on the `extends` keyword.  Use the _is-a_ test


### The _is-a_ test (1/3)

If it makes sense, then proceed with `extends`

* a dog **is a**n animal <span style="color: green">✔</span>
  - `class Dog extends Animal`
* a cat **is a**n animal <span style="color: green">✔</span>
  - `class Cat extends Animal`
* a horse **is a**n animal <span style="color: green">✔</span>
  - `class Horse extends Animal`
* a ventilator **is a**n animal <span style="color: red">❌</span>



### The _is-a_ test (2/3)

Some might be _has-a_ relationships, _has-a_ **is not** _is-a_
has-a (composition) will be the next next topic

* `class House extends Roof` // hhmmm?
  - a house **is a** roof <small style="color: red">sounds wrong</small>
  - a house **has a** roof <small style="color: blue">definitely not inheritance</small>
* `class Leash extends Dog` // maybe?
  - a leash **is a** dog <small style="color: red">sounds wrong</small>
  - a leash **has a** dog <small style="color: blue">definitely not inheritance</small>
* `class Biologist extends Scientist`
  - a biologist **is a** scientist <span style="color: green">✔</span>



### The _is-a_ test (3/3)

Roses are red, violets are blue.  
Mango is a fruit, but the reverse ain't true.

* `class Animal extends Dog`
  - an animal **is a** dog <span style="color: red">❌</span>
* `class Dog extends Animal`
  - a dog **is a**n animal <span style="color: green">✔</span>
* inheritance is one-way only.
  - an instrument **is a** guitar <span style="color: red">❌</span>
  - a guitar **is a**n instrument <span style="color: green">✔</span>