# Virtual Pet Shelter

So, you have some experience under your belt in the care and feeding of a virtual pet. It's time to share that with the community! Time to volunteer!

## Skills Required
-  Loops
-  Lists
-  Methods
-  Intro to OOP
-  Defining Classes
-  Creating Classes and Access Modifiers
-  Inheritance and Polymorphism

## Requirements

- [ ] Create a C# project in Visual Studio named `VPShelter`.
- [ ] Create a GitHub repository also named `VPShelter` and set it up so that you can push your code there from your Visual Studio project. Do this *now*. It's the least fun part, so just get it out of the way.
- Create the following classes:
	- [ ] `VirtualPet`: You can start with your class from last week's assignment or create another.
	- [ ] A class that is derived and has `VirtualPet` as its base class.
		- [ ] Fields/Properties for the type of pet and the pet's diet
	- [ ] `VirtualPetShelter`: Homeless virtual pets need a place to stay.
		- [ ] Fields/Properties to store all of the pets and all of the employees
	- [ ] `Employee` base class.
		- [ ] One property (perhaps EmployeeID)
		- [ ] Two abstract methods
	- [ ] `Volunteer` class derived from `Employee`
		- [ ] An override method
		- [ ] An additional property
		- [ ] A method for feeding all of the pets
		- [ ] A method for giving water to all of the pets
	- [ ] `Manager` class derived from `Employee`
		- [ ] An override method
		- [ ] An additional property
		- [ ] A method for adopting a pet
- Your Program class will house your `main` method, and be responsible for reading user input and writing output to the console.

## Details

We're going to create an application that simulates employees taking care of the pets in a shelter.

Include a game loop in this project, too. It should prompt the user, then call the appropriate method(s) on any of the required classes.

### NOTE:

The following examples are _GUIDELINES ONLY_, you can customize your user interface as you see fit as long as you meet all of the above requirements.

### Example Employee Set Up

```bash
Welcome to Big Al's Virtual Pet Shelter. What employee type are you?
1. Manager
2. Volunteer
```
### Example Interactions

For volunteer:

```bash
Thank you for volunteering at Big Al's Virtual Pet Shelter and Delicatessen!

This is the status of your pets:

Name	|Hunger	|Thirst	|Boredom
--------|-------|-------|-------
Joey	|83     |34     |23
Johnny	|69     |49     |2
Dee Dee	|39     |18     |88
Tommy	|59     |19     |37

What would you like to do next?

1. Feed the pets
2. Water the pets
3. Play with a pet
4. Quit
```
For manager:

```bash
Thank you for working at Big Al's Virtual Pet Shelter and Delicatessen!

What would you like to do?
1. Adopt a pet
2. Feed the pets
3. Play with a pet
4. Pay the bills
5. Quit
```

#### Example Pet Selection Interaction

```bash
Ok, so you'd like to play with a pet. Please choose one:

[Joey] looks like he's seen better days.
[Johnny] is a bit nervous.
[Dee Dee] probably didn't start with that many legs.
[Tommy] smells like a Stargazer lily fresh with morning dew.

Which pet would you like to play with?
Tommy

Ok, you play with Tommy.
```

## Required Tasks

### Program class

- In the `main` method have a program that…
	- [ ] asks for user input.
	- [ ] writes output to the console.

- Available user interface actions should include (at minimum)…
	- [ ] `Volunteer` feeding all the pets
	- [ ] `Volunteer` watering all the pets
	- [ ] `Volunteer` or `Manager` playing with an individual pet
	- [ ] `Manager` to coordinate adoption of a pet, which should display a list of pet names and descriptions, allowing a user to select one


### VirtualPetShelter class

- [ ] include appropriate instance variable(s) (fields/Properties) to store the pets who reside at the shelter
- [ ] include appropriate instance variable(s) (fields/Properties) to store all of the employees who volunteer or work at the shelter.

### VirtualPet class
	
In addition to the requirements from last week's project,
- include instance variables (fields/Properties) representing:
	- [ ] name
	- [ ] description
- include a constructor that accepts a name and description only
- include a constructor that, in addition to name and description, accepts starting values for the pet's attributes (hunger, boredom, etc)

Remember that it is OK to have more than one constructor. This will be called an **overloaded** constructor

### Class derived from VirtualPet

- Include instance variables (fields/Properties) representing:
	- [ ] type of pet
	- [ ] pet's specific diet

### Employee Classes
- [ ] `Employee` base class.
		- [ ] One property (perhaps EmployeeID)
		- [ ] Two abstract methods (for example, ClockIn() or ShowID())
	- [ ] `Volunteer` class derived from `Employee`
		- [ ] An override method (How does a Volunteer do one of the Employee methods differently?)
		- [ ] An additional property (for example HoursAvailable, VolunteerType, or VolunteerSpecialty)
		- [ ] A method for feeding all of the pets
		- [ ] A method for giving water to all of the pets
	- [ ] `Manager` class derived from `Employee`
		- [ ] An override method (How does a Manager do one of the Employee methods differently?)
		- [ ] An additional property (for example, Salary, YearsEmployed, or Department)
		- [ ] A method for adopting a pet

## Stretch Tasks

- [ ] Consider any stretch tasks from last week's project that you did not attempt.
- [ ] Keep track of the cleanliness of individual pets' cages and offer an option in the user interface to clean pet cages
- [ ] DNA! In order to give your pets individual character, include as part of each pet's state one or more specific parameters for needs so that one pet may become hungrier/thirstier/more bored slower/faster than another pet. (*Tip: you could create a class to encapsulate this.*)
