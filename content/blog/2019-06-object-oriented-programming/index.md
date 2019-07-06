---
title: Object Oriented Programming
date: "2019-06-29T22:30:03.284Z"
description: ""
---

### Important Note
This article is not completed yet. I'll continue it.

---

Object Oriented Programming is a programming paradigm that uses objects.
Objects are instance of the classes. Classes are kind of data structure that holds
data in their attributes. Except holding data, it has procedures. In object oriented programming,
we call them as methods. And classes can manipulate data, communicate with the other classes using that methods.

It has some cool features like abstraction, encapsulation (data-hiding), inheritance, polymorphism.
We'll talk about, be patient! :)

## Encapsulation

It's one of fundementals of Object Oriented Programming. It's basically known as data-hiding.
We can think about light switches if we need to find a real example in the world to understand it.

The light switches only provides 2 action. You can turn it on and turn it off. 
But what about the things that happened behind the scene? We don't know. We don't need to know it.
Electrician guy handles everything for us and provides us to be able use only on and off actions without thinking about
how it works.

So, some classes that we'll create would need to hide some of its data and implementations from consumers.
Consumers of that classes can't access the data directly, can't modify them directly. Only way to access and modify is using the
public methods provided by class.

Let me show an example

```php
<?php

class Computer
{
    public function on()
    {
        $this->runCpu();
        $this->runRam();
    }

    private function runCpu()
    {
        // implementation here...
        // we can't access the private method from outside
    }

    private function runRam()
    {
        // implementation here...
        // we can't access the private method from outside
    }
}
```

If we try to access `runRam` or `runCpu` in this example, we will encounter with an error.
Because they are **private** methods. Thus, the class hid the implementations from outside.

```php
<?php

$myComputer = new Computer;

$myComputer->runCpu(); // I encounter with an error, I'm not be able to run cpu myself.

$myComputer->on(); // the computer will handle all process instead of us
```

## Inheritance

Thanks to inheritance, we can derive a class from another one. What's that mean? Actually,
that's the way copy all behaviors and attributes of a class to the another one. In that way,
it prevents the duplicates and provides us to re-use existing one. Also we can apply abstraction
in that way.

Let's explain in with an example

```php
<?php

class Person
{
    private $name;

    public function __construct($name)
    {
        $this->name = $name;
    }

    public function sayName()
    {
        echo $this->name;
    }
}

class Programmer extends Person
{

}

$programmer = new Programmer('Selahattin');
$programmer->sayName(); // output => 'Selahattin'
```

So, how is it working without have `sayName` method?
Yes, you're right it has not `sayName` method in own class definition.
But it extends the `Person` class. So we applied inheritance from Person to Programmer class.
So, thanks to its parent class, `Programmer` class has `sayName` method as well.

## Abstraction

...

## Polymorphism

...