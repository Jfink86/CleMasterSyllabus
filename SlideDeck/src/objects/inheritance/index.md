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
## Base Constructor Example 

```csharp 
public class Rectangle : Shape
{
    private double area;
 
    public Rectangle(double area) : base(4)
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
- By including the `base(4)`, the public `Shape(int sides)` is included and sets sides equal to 4. 


## Access Modifiers in Derived Classes

Let's review access modifiers
<div class="fragment">
public - can be accessed from every class
</div>
<div class="fragment">
private - can not be accessed from any other class (default for elements of a class)
</div>
<div class="fragment">
<mark>protected - can be accessed from its class and all descendent classes</mark>
</div>
<div class="fragment">
internal - can only be accessed from the same assembly (default for classes) → More later.
</div>

## Access Modifiers Example

```csharp
public class Rectangle : Shape
{
    private double area;
 
    public Rectangle(int sides, double area)
    {
        this.Sides = sides;
        this.area = area;
    }
 
    public double Area
    {
        get { return this.area; }
        set { this.area = value; }
    }
}
```
QUESTION: Why do we have to use the property `Sides` in the `Rectangle` class?  
<div class="fragment">ANSWER: The field `sides` is set to `private` in the `Shape` class.</div>
<div class="fragment">QUESTION: What access modifier can be used so the field sides can be accessed by a child class?</div>


## PRACTICE!!

In Visual Studio, open a new project and create a base class and 2 classes that are derived from that base class.
<div class="fragment">Add four fields to your base class.</div>
<div class="fragment">Add two Properties to your class.</div>
<div class="fragment">Add a constructor to your derived class that includes a call to your base class.</div>
<div class="fragment">Add two methods to your derived classes.</div>
<div class="fragment">Add a method to your base class and use it in both of your derived classes.</div>



## “virtual” keyword

```csharp
public virtual void Clean()
{
	// body of the method
}
```
In order to give the derived classes permission to create their own version of a method, the keyword `virtual` must be included in the method declaration in the base class.

## Example

```csharp
class Appliances
{
	public virtual void Clean()
	{
		// general cleaning instructions
	}
}

```

## “override” keyword

```csharp
public override void Clean()
{
	// body of the method
}
```
When implementing a new version of the method in the derived class, add the keyword override. 

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