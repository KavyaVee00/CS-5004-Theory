# CS-5004-Theory


## Chapter 1: Getting Started with Java 




## Chapter 2: Object Oriented Design with Java 

OOP is a way of creating objects and we do that by creating a class. A class has two things, member data and member functions. 

Classes are pretty much blueprints for objects. Blueprints detail the general structure. For example, let’s say we have a blueprint for making a robot. We would start off by creating a class. 

```c
public class Robot {

} 
```
Class names in Java always are written in TitleCase. Primitive type names, like int and boolean , are lowercase. Note that the class is public. This means that it can be used in other classes. 

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

* Note that the variables are labeled as private. This means that they can only be accessed from inside the Robot class. Keeping these variables private help keep the classes separated from each other so that if you change one thing in a class, you won't be required to make any changes in other classes since the classes are isolated from each other. 

Now in order for the robot to actually recieve a size, model, or name, we would have to create a constructor. A constructor is what actually brings the robot to life by assigning it a name, model, size. But how exactly does it do that? This is where the "this" pointer comes in to play. 

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

These are like commands that we can give to the robot to make them do things. Just like how you may press buttons to make a toy robot move, in Java, you use methods to make our object, the robot, to move. 

So once we bring our robot to life with a constructor, we might want to actually know what's it name is or what it's size is. That's where Getter's come in. Getter's allow us to peek inside the box and see what's inside there. Here are some examples of getters. 

```c
    public String getName() {
        return name;
    }


   public String getModel() {
        return model;
    }

```


But what if we want to change what it's inside the box. Maybe we don't like the name of the robot or the size of it. This is where Setters come in. Setters allow is to change what's inside the box. We can tell the robot " Your name is now this ___" or "Your size is now this ___". Here are some examples of setters: 

```c
public void setName(String name) {
        this.name = name;
    }


public void setModel(String model) {
        this.model = model;
    }
```
Now the robot will update what's inside the box accordingly to, for example, what name or size you want it to be. Note the "this." pointer again. It's telling the program to stick the new name value into the name box. Or telling the program to stick the new model value into the model box. It directs where each value should correctly be. 


Now the blueprint is ready! This is the code in it's entirety: 

```c
// Define the Robot class
public class Robot {
    // Attributes or variables
    private String name;
    private String model;
    private int size;

    // Constructor to initialize the attributes
    public Robot(String name, String model, int size) {
        this.name = name;
        this.model = model;
        this.size = size;
    }

    // Method to make the robot walk
    public void walk() {
        System.out.println(name + " is walking.");
    }

    // Method to make the robot lift a box
    public void liftBox() {
        System.out.println(name + " is lifting a box.");
    }

    // Getters and setters for the attributes
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getModel() {
        return model;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public int getSize() {
        return size;
    }

    public void setSize(int size) {
        this.size = size;
    }
}

```c





