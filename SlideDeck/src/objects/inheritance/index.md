title: Inheritance and Polymorphism
subtitle: Two Important Principles of OOP
theme: league

## Topics

 - What is Inheritance?
 - What is Polymorphism?
 - Why are these principles essential to Object Oriented Programming?

## Example of a Base Class

```csharp
public class Shape
{
    private int sides;
 
    public Shape()
    {

    }
    public Shape(int sides)
    {
        this.sides = sides;
    }
 
    public int Sides
    {
        get { return this.sides; }
        set { this.sides = value; }
    }
}
```
 

## Derived Classes

- A derived class (also called a child class or a subclass) is any class that inherits from another class.
- To create a derived class, include a colon and the name of the base class.

```csharp
//Example:
public class ChildClass : ParentClass
```


## Example of Derived Class

```csharp
public class Rectangle : Shape
{
    private double area;
 
    public Rectangle(double area)
    {
        this.area = area;
    }
 
    public double Area
    {
        get { return this.area; }
        set { this.area = value; }
    }
}
```

## Your Turn! 

- What are some examples of base classes? 
<div class="fragment">
- What are some examples of classes that could be derived from those base classes?
</div>

## Members of a Derived Class

- In OOP, the states and behaviors of a class are, all together, called the "members" of that class.
- Let's talk about what makes the members of a derived class different from the members of a base class.

## Constructors 

- A derived class does NOT inherit the constructors of the base class.
- However, the constructors of the base class can still be accessed using the “base” keyword.

```csharp
public ChildClass(int num) : base(“string”)
{
        // body of constructor
}

```
!SLIDE 

-  Let's break this down piece by piece. Focusing on the left side of the equals sign we have:
```csharp 
    Cat mittens 
```
- This is the same form we've seen since day one. The type of the variable come first, followed by the name of the variable. The type of our variable here is `Cat` and our variable is called `mittens`. 
- Instead of storing an int or string like we've seen so far, this variable stores an _instance_ of a `Cat` object.

!SLIDE

```csharp 
    new Cat(); 
```
The part after the equals sign is where we initialize our object. `new` is a keyword we use to instantiate an object and invoke the constructor. 
`Cat();` is the <mark>constructor</mark> being called. We need both of these parts to instantiate an object. 

## Building classes

All classes start out with the keyword `class` followed by the name of the class. We can choose any name we like as long as it hasn't been used already.

Here we are defining a `class Cat`. It doesn't contain anything yet.
```csharp
class Cat
{


}

```

## Adding a constructor

Next let's add a constructor and a field. The constructor we added is called a default constructor, i.e. it takes no arguments.

```csharp
class Cat
{
    private string name;

    public Cat()
    {

    }
}

```

## Completing our class

We have no way set the name to our cat. Let's complete our class and talk about it.

!SLIDE

```csharp
class Cat
{
    private string name;
    private int age;
    private string furColor;
    private isHungry = true;


    public string Name
    {
        get {return this.name;}
        set {this.name = value;}
    }

    public Cat()
    {

    }

    public Cat(string name, int age, string furColor)
    {
        this.name = name;
        this.age = age;
        this.furColor = furColor

    }
```

## Below our Constructors, we'll include a method

```csharp
    public void Eat()
    {
        if(isHungry)
        {
            isHungry = false;
        }

        Console.WriteLine("Is the cat hungry? " + isHungry );
    }
}
```
## Breaking down each part of our class

- In the class we defined a number of fields at the top. These are where we store all the information that belongs to each instance(our object) of our class. 
- Remember, each instance comes from the same template. That means each object created from this class will have the same fields, but each instances variables will hold unique values. 
- We use camel case when we name our fields.

!SLIDE

- We have a public property called `Name`. This will allow for code outside of our class to access the field called `name`.  
- Properties should be named Pascal case, this is important as it differentiate it from our fields.

!SLIDE

- Our class `cat` has two constructors. We're allowed as many constructors as we need as long as they each have a unique signature. 
- Our first constructor is a default constructor that doesn't do any thing. 
- Our second constructor takes a string, an int, and a string as parameters. 
- Our constructors <mark>always share the same name</mark>!! 

!SLIDE

- The keyword `this` allows us to select only the field, the variable that belongs to the class. 
- In a situation where a method's parameter and a field have the same name we can use the keyword `this` to differentiate the two.

!SLIDE

- We have a public method `Eat`. The return type is void, which means after it completes it doesn't provide us any new information.

## Do It
 - Create a class Dog
 - The class Dog should have the following fields
   - hairLength
   - height
   - runningSpeed
   - weight
 - The class should have the following behaviors
   - Run()
   - Bark()
   - Potty()
   - Cuddle()
   
## Do It
 - Create a class Superhero
 - The class Superhero should have 4 fields
   - An example might be strengthLevel or hasCape
 - The class Superhero should have 4 Properties
   - An example might be StrengthLevel or SecretIdentity
 - The class Superhero should have 3 Constructors
 - The class Superhero should have at least two methods
   - One method should impact the Superhero's health (could be Health, could be StrengthLevel, could be Speed, etc.)
   - One method should give your Superhero a power boost. (could be EatsSpinach() or AbsorbsYellowSun(), etc.)

<style type="text/css">
/* should we move this into the template, or will it break existing slides. Maybe those slides are wrong. */
.reveal h3 {
	font-size: 4.4rem;	
}
</style>