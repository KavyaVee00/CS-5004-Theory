# CS-5004-Theory


## Chapter 1: Getting Started with Java 




## Chapter 2: Object Oriented Design with Java 

OOP is a way of creating objects and we do that by creating a class. A class has two things, member data and member functions. 

Classes are pretty much blueprints for objects. Blueprints detail the general structure. For example, let’s say we have a blueprint for making a robot. We would start off by creating a class. 

```c
public class Robot {

} 
```
Class names in Java always are written in TitleCase, and field names are always written in camelCase. Primitive type names, like int and boolean , are lowercase.

As the engineer, we would probably want the Robot to have some attributes or variables. The attributes could be individual strings, numbers, or booleans.

```c
public class Robot {
// Attributes or variables
    private String name;
    private String model;
    private int size;
} 
```
For this example, the attributes could be like its size (number), or model (string), or name(string). These attributes only define what makes up a Robot and what we would want it to have. I like to think of these as empty boxes with labels of what is supposed to go inside of them.

But in order for the robot to actually recieve a size, model, or name, we would have to create a constructor. A constructor is what actually brings the robot to life by assigning it a name, model, size. But how exactly does it do that? This is where the "this" pointer comes in to play. 

```c
// Constructor to initialize the attributes
    public Robot(String name, String model, int size) {
        this.name = name;
        this.model = model;
        this.size = size;
    }
```
In the constructor, when you use "this.name = name;", it means you're assigning the value of the "name" parameter to the "name" variable of the current robot object. Same goes for "this.model = model;". You're assigning the value of the "model" parameter to the "model" variable of the robot object. So if we're thinking about it in the sense of boxes, when we use "this" in the constructor, it's like the robot talking to itself, saying "Hey, I'm the robot we're talking about, so put my name in my name box, my model in my model box, and my size in my size box." It'w what essentially gives the each box what is supposed to go inside them.

But these aren’t enough to create a WHOLE robot. It needs to be able to do something or have a functionality.  Maybe we might want it to walk or lift a box. These actions are known as methods. 

```c
// Method to make the robot walk
    public void walk() {
        System.out.println(name + " is walking.");
    }

    // Method to make the robot lift a box
    public void liftBox() {
        System.out.println(name + " is lifting a box.");
    }
```

These are like commands that we can give to the robot to make them do things. Just like how you may press buttons to make a toy robot move, in Java, you use methods to make our object, the robot, toe move. 













So, after we bring our robot to life with the constructor, sometimes we might want to know what's inside its brain, right? Like, we might want to ask our robot what its name is, or what model it is. That's where getters come in! Getters are like little windows into the robot's brain. They let us peek inside and see what's there.

Now, what if we decide we want to change something in the robot's brain? Maybe we want to give it a new name or update its size. For that, we use setters! Setters are like magic wands that let us change what's inside the robot's brain. We can tell the robot, "Hey, your name is now this," or "Your size is now that," and the robot will update its brain accordingly.

So, in our robot example, after we bring our robot to life with the constructor, we can use getters to ask the robot about its name, model, or size. And if we want to change any of those things, we can use setters to update the robot's information. It's like having a little chat with our robot friend to learn more about it and make it even cooler!












As the engineer, we would probably want the Robot to have some attributes or variables. The attributes could be individual strings, numbers, or booleans. For this example, the attributes could be like its size (number), or model (string), or name(string). These attributes define what makes up a Robot.. But attributes aren’t enough to create a WHOLE robot. It needs to be able to do something or have a functionality.  Maybe we might want it to walk or lift a box. These actions are known as methods. They are going to do things within the class. 

So for example
