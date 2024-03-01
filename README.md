# CS-5004-Theory


## Chapter 1: Getting Started with Java 

The reason why Java was chosen as the programming language for this class is because it’s an incredibly versatile programming language, easier to maintain and it’s reusable. It allows for a more separated program which is well structured and more organized. This can help when you have to deal with more complex code which is often in object oriented programming. Java is great for object-oriented design because it's built with object-oriented principles in mind. 

It provides a good base for things like classes, inheritence, polmorphism, etc. With Java, you can reuse code by creating classes that define how objects should behave. This saves time and effort because you can use the same code in different parts of your program. Java's class-based structure helps keep your code organized and allows you to change and update it without affecting other parts of your program. And because of this, Java is well-suited for big projects because it make it easier to manage and maintain complex code. 

Comparing it to python, I feel like python emphasizes simplicity while java emphasizes consistency. In python, you don't have to say what type of data a variable is. In Java, you need to explicitly declare the varible type. C/C++ syntax is closer to Java in terms of requiring explicit type declarations. As far as the compilation process, Java turns code into bytecode which is then read by the Java Virtual Machine (JVM). For python, code is read line by line and turned into bytecode on the fly. C/C++ code is compiled directly into machine code for the specific computer it's going to run on with specific compilers (gcc/g++). Again, for java, you have to say what type of data each variable is and this is checked before running the code. For python, you don't have to say what type of data a variable is and it is checked while running. C/C++ is like java, you have to say what type of data each variable is and it is also checked before running. Another comparison is syntax. Java uses curly braces {} to label code blocks and also need semicolons ; at the end of statements. Python syntax is easier in that it uses indentation to label code blocks and does not require semicolons at the end of statements. C/C++ syntax is closer to Java in that they do need the types to be declared and also their statements end with a semicolon. 


Java can be used for many things in the world such as web development, mobile apps,etc. Java can also work with larger projects, like software systems for big companies, like banking systems, for example. Java is also great for working with big data. It helps process and analyze huge amounts of information which makes it useful for things like analyzing trends,  making decisions based on data. Java is an incredibly versatile programming language so it can be applied to so many different things. 



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
In the constructor, when you use "this.name = name;", it means you're assigning the value of the "name" parameter to the "name" variable of the current robot object. Same goes for "this.model = model;". You're assigning the value of the "model" parameter to the "model" variable of the robot object. So if we're thinking about it in the sense of boxes, when we use "this" in the constructor, it's like the robot talking to itself, saying "Hey, I'm the robot we're talking about, so put my name in my name box, my model in my model box, and my size in my size box." It'w what essentially directing the data into it's corrosponding box. 

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

So once we bring our robot to life with a constructor, we might want to actually know what's it name is or what it's size is. That's where Getter's come in. Getter's allow us to peek inside the box and see what's inside there. It's like asking the robot to tell us what it's name or model is. Here are some examples of getters. 

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


Now the blueprint is ready! This is the code in it's entirety which we can use for the next part.  

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
```


So all of this is part of the Class which is still just a blueprint, so it doesn’t really exist yet. When we create a class, we tell the language what this new data type looks like and what it does, but all we’re doing at this point is DESCRIBING what the data type looks like, we’re not actually creating a robot that we can work with.


Now let's move on to how to actually create the Robot, the object. 


## Chapter 3:  Getting Deeper with Class Objects 

As a refresher, this is our newly made class: 

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
```

To create an object of Robot, we need to do it in the main class. We will specify the class name , followed by the object name, which can be Robbie, and use the keyword new:

```c
// Main class to test the Robot class
public class Main {
    public static void main(String[] args) {
Robot myRobot = new Robot("Robbie", "Ultron", 3);
```
This is how we create a Robot object. We have to ask the program to make a Robot for us. But just making the robot isn't enough; you also need to give it some the features, like its name, model, and size. So when you write new, it tells Java to make a new robot and it follows instructions from the constructor to make sure the robot has everything it needs.

So to make it clearer, it this example, 
- "Robot" is the class name 
- myRobot is the object name. 

The arguments are the name "Robbie", model "Ultron", size "3". That's where the constructor comes in. It's like a set of instructions that tells the machine how to build the robot with all those features. These arguments invoke the constructor to start assigning those parameters to the correct "box". 

But what if we wanted to change the variables again. Let's say that we hate the name Robbie and want to update the name. We can use Setters! 

```c
// Update Robot name 
        myRobot.setName(Jeremy);
```

So now we've updated the robot. A Robot that goes by the name of Jeremy, Model Ultron, and Size 3.  

Now how do we make class objects actually do things? That's where methods come in to play. We have to call the methods in the main class for the object to start doing them. 

```c
myRobot.walk();
myRobot.liftBox();
```

The output for this would be: 

```c
Jeremy is walking.
Jeremy is lifting a box.
```

Now let's talk about dynamic and static variables. In the Robot class, the variables name, model, and size are all dynamic variables. Why? Because they can vary from one robot instance/object to another. For example, one robot "Robbie" has the name "Robbie", the model "Ultron", and the size 3, while another robot "Jeremy" could have different values for these variables, like name "Jeremey, model "Transformer, and size 2.  

Another dynamic variables would be the methods we created. The methods walk() and liftBox() are dynamic functions because they perform actions specific to each robot object. When we call myRobot.walk(), it prints out "Robbie is walking.", indicating that "Robbie" is the one walking. If we had another robot named "Jeremy", calling myRobot2.walk() would print "Jeremy is walking.". 

So essentially, dynamic variables mean that they are variables that can constantly be changed. They are variables that are unique to each object. 

Static variables, on the other hand, are shared among all objects of the class and are not unique to each object. They have the same value for all of the objects. 

 In this code, there are no static variables or functions defined. However, let's create one. 

 Let's add a static variable manufacturer to the Robot class. This variable will store the name of the manufacturer of all robot objects.
```c
 public class Robot {
    // Attributes or variables
    private String name;
    private String model;
    private int size;
    private static String manufacturer = "Stark Industries"; // Static variable for the manufacturer


.... rest of the code


// Static method to get the manufacturer
    public static String getManufacturer() {
        return manufacturer;
    }

    // Static method to set the manufacturer
    public static void setManufacturer(String newManufacturer) {
        manufacturer = newManufacturer;
    }
}
```
So as you can see, I've added a manufactor variable. So one thing that I remember I was intially confused about when I was learning about this is why do the other methods not have getters or setter, but the static one does? I realized this is because the static variable is an actual variable that is instansized in the class, like name or size, and so it needs to have a getter or setter. The methods to lift a box or walk don't need getters or setters because they are not actual variables instanized in the class.  

Now, manufacturer is a static variable that stores the name of the manufacturer of all robot objects. We can access it using Robot.getManufacturer() and modify it using Robot.setManufacturer(). This variable is shared among all objects of the Robot class. Note how we had to use the word "static" when setting up our methods. 

This is an example of what it would look like if the method was called. 

```c
public class Main {
    public static void main(String[] args) {
        // Create two Robot objects
        Robot myRobot1 = new Robot("Robbie", "Ultron", 3);
        Robot myRobot2 = new Robot("Jeremy", "Transformer", 2);

        // Display the manufacturer
        System.out.println("The Manufacturer for " + myRobot1.getName "is" + Robot.getManufacturer());
        System.out.println(The Manufacturer for " + myRobot2.getName "is" + Robot.getManufacturer());
```
        
Note how I'm calling to get the corrosponding name for each robot but when I call the manufactoer, it's not a specific object because it is a variable that is shared among all the objects of the Robot class. 

This would be the output: 

```c
The Manufacturer for Robbie is Stark Industries
The Manufacturer for Jeremy is Stark Industries
```

When I approach class design, I think of it like building with lego blocks.  I start off by thinking about what I want to actually create. Once I have that in mind, I start thinking of the different types of pieces that I would need in order to build what I'm thinking of. These pieces are what I like to think as the variables of the class. For example, if I'm going to make a car out of legos, I would need parts like wheel, doors, steering wheel, side mirros, seats, etc. Now I have to think about what I want my object to do, what actions I want it to do. These are what I think of methods as. Methods are what enables the object to be able to interact or move. For the lego car example, I might want it to maybe drive or turn. I also think about the access modifiers, like public, private, etc and making sure that I'm implementing the correct ones for the variables or methods. Overall, when it comes to class design, I try to make it as organized as possible since personally looking at long code can be kind of overwhelming so making it as structured as possible is key to making my understanding clearer. Carefully planning and organizing your code to the proper structure also makes it more efficient and easier to use, which is something else that I like to keep in mind when I start creating a class. 


This is an example of efficient class:

```c
// T Robot class
public class Robot {
    // Attributes or variables
    private String name;
    private String model;
    private int size;
    private static String manufacturer = "Stark Industries"; // Static variable for the manufacturer
    // Constructor 
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

// Static method to get the manufacturer
    public static String getManufacturer() {
        return manufacturer;
    }

    // Static method to set the manufacturer
    public static void setManufacturer(String newManufacturer) {
        manufacturer = newManufacturer;
}


// Main class for Robot class
public class Main {
    public static void main(String[] args) {

 // Create two Robot objects
    Robot myRobot1 = new Robot("Robbie", "Ultron", 3);
    Robot myRobot2 = new Robot("Jeremy", "Transformer", 2);

  // Display the manufacturer
     System.out.println("The Manufacturer for " + myRobot1.getName "is" + Robot.getManufacturer());
     System.out.println(The Manufacturer for " + myRobot2.getName "is" + Robot.getManufacturer());

myRobot1.walk();

myRobot2.liftBox();

}
```

## All about Unit Testing 

Test driven development is the practice in which we write our tests before we develop the actual code. In my eyes, it’s like laying the framework of what we expect we want the code to do by writing tests that would write the code accordingly to pass.

Test driven development is key in making sure that our code executes what we want to. It gives us direct information about what part of the code we need to improve on, increasing our productivity. It allows us to hone in on what exact part of the code needs fixing, so it’s more efficient since we won’t waste time figuring out what part of the code is wrong or rework the entire code. 

Let’s dive into how to implement Test Driven Development using Junit by using the Robot Class we created before. 
- We would first disregard the class that we just created, or pretened that we didn't, and build tests that adhere to the code that we want to implement.
- Then we would write what I consider like the first draft of the code, simple and straight to the point and passes the tests with no errors
- Once I get the code running and passing the tests, I can then go back in and increase the functionality, 

Let’s start with common naming conventions.

The name of the class we are testing is “Robot”. So the name of the test class should be called RobotTest. 

This naming convention can also be applied to methods as well. One of our methods is “liftBox”. So the name of the test that we would create for that method would be “testliftBlock”. 

Now let’s dive into annotations. 

Annotations are what tells the program what we want to do with the code. 

The “@Before" annotation is used to run the code before every test. We basically set up the variables or methods that we want to test. If our tests need certain objects to be created before we run the test, we can use this annotation to set it up. 

Here is an example: 

```c
import org.junit.Before;
import org.junit.Test;
import static org.junit.Assert.*;

public class RobotTest {
    private Robot myRobot;

    @Before
    public void setUp() {
     // This will run before each test
        myRobot = new Robot("Robbie", "R2-D2", 3);
    }

    @Test
    public void testWalk() {
        // This test checks if the robot can walk
        assertEquals("Robbie is walking.", myRobot.walk());
    }

    @Test
    public void testLiftBox() {
        // This test checks if the robot can lift a box
        assertEquals("Robbie is lifting a box.", myRobot.liftBox());
    }
}

```

So as you can see, we are setting up by creating an object that the tests will be using. 

The "@Test" annotation wants the code written following it executed as a test. This is pretty self explanatory. 

Another annotation is "@After". So just like how the @Before annotation prepares us for the test before, the @After annotation is when we clean up or or release any resources that we were using before the test, so essentially wiping the slate clean for a fresh start for the next test. 

```c
@After
    public void tearDown() {
        // Release any resources that were used during testing
        myResource.close();
    }
```
So as you can see in this example, it ensures that the resources that are used are all cleaned up. 

Another equally important one is the assertEquals annotaton

assertEquals: This is an assertion method provided by JUnit. It checks if the actual result of a test matches the expected result. If the actual result matches the expected result, the test passes; otherwise, it fails

Here's some tests that I've created: 
```c
import static org.junit.Assert.assertEquals;
import org.junit.Before;
import org.junit.Test;

public class RobotTest {
    
    private Robot robot;

@Before
    public void setUp() {
        robot = new Robot("Robbie", "Ultron", 3);
    }

    @Test
     public void testGetName() {
        // Testing the getName method
        assertEquals("Robbie", robot.getName());
    }

    @Test
    public void testGetModel() {
        // Testing the getModel method
        assertEquals("Ultron", robot.getModel());
    }

    @Test
    public void testGetSize() {
        // Test the getSize method
        assertEquals(3, robot.getSize());
    }

    @Test
    public void testSetName() {
        // Test the setName method
        robot.setName("Jeremy");
        assertEquals("Jeremy", robot.getName());
    }

    @Test
    public void testSetModel() {
        // Test the setModel method
        robot.setModel("Transformer");
        assertEquals("Transformer", robot.getModel());
    }

    @Test
    public void testSetSize() {
        // Test the setSize method
        robot.setSize(5);
        assertEquals(5, robot.getSize());
    }

    @Test
    public void testWalk() {
        // Testing the walk method
        assertEquals("Robbie is walking.", robot.walk());
    }

    @Test
    public void testLiftBox() {
        // Testing the liftBox method
        assertEquals("Robbie is lifting a box.", robot.liftBox());
    }
}
```


Now let's dive into comparing the driver testing to the unit testing! 

I like to think of Drivers as the big picture while Unit tests are like a magnifying glass. A driver makes sure that the whole code works as a whole while Unit tests look at each specific part of the code seperately to ensure those parts are working. With driver testing we get feedback on how well the code performs overall. Unit Testing gives much more specific feedback, like what part is not working. 

Driver testing would be like assembling the entire robot and making sure it can walk, talk, and do everything it's supposed to do. We want to make sure if the whole robot works as expected. 

Unit testing is like checking each part individually to see if it works well on its own. That's when we think about testing each part of the robot separately, like making sure the arms can move correctly, the legs can walk properly, etc. 

We use driver testing to ensure that our entire application works correctly from end to end, just like making sure our entire robot functions as expected. We use JUnit testing, or unit testing in general to make sure that each individual piece of our code works correctly on its own, just like making sure each part of our robot functions properly. 

This an example of a Driver test for the Robot class: 

```c
public class RobotDriverTest {

    @Test
    public void testRobotActions() {
        Robot myRobot = new Robot("Robbie", "R2-D2", 3);

        // Test walking action
        System.out.println("Testing walking action:");
        myRobot.walk(); // This should print "Robbie is walking."

        // Test lifting a box action
        System.out.println("\nTesting lifting a box action:");
        myRobot.liftBox(); // This should print "Robbie is lifting a box."
    }
}

```
This is an example of a JUNit test: 

```c
import static org.junit.Assert.assertEquals;
import org.junit.Test;

public class RobotTest {

    @Test
    public void testWalk() {
        Robot myRobot = new Robot("Robbie", "R2-D2", 3);
        assertEquals("Robbie is walking.", myRobot.walk());
    }

    @Test
    public void testLiftBox() {
        Robot myRobot = new Robot("Robbie", "R2-D2", 3);
        assertEquals("Robbie is lifting a box.", myRobot.liftBox());
    }
}
```

In the driver test, we had to write the code out to test the Robot class by calling the methods and we have to observe the output ourselves to make sure that it's the output we want. 

On the other hand, the JUnit test is more like hands free automatic testing. With JUnit, it all kind of layed out for us and it makes it easier because it already has a framework of annotations and assertions that do the work for us. These tests are executed automatically by the JUnit framework and the results are reported back us. So the framework goes ahead and checks to see if the ouput is what we expected, tells us what worked and didn't work, we dont have to verify it ourselves like we had to with the driver test.  


## Exception Handling

Exception handling is part of when we try to understand what is the exact nature of the problem. What if the problem is that we have an unexpected condition? Like lets say for our Robot class, I didn't give the robot a name? We would call this an Exception. An exception is basically something that stores information about the problem and what caused it. It basically notifies java to tell us what the problem is. 

Now in the robot scenario, I tried to not give the robot a name. This would be called an illegal argument. There already is an exception class is is specially built for that. It's called the illegal argument exception. Let's look at an example to see how we would write this. 
```c
   // Constructor with parameter validation
    public Robot(String name, String model, int size) {
        if (name == null || name.isEmpty()) {
             new IllegalArgumentException("Name cannot be null or empty");
        }
        this.name = name;
        this.model = model;
        this.size = size;


....//rest of the code


 public void setName(String name) throws  {
        if (name == null || name.isEmpty()) {
             new IllegalArgumentException("Name cannot be null or empty");
        }
        this.name = name;
    }
    }
```


In this example, I changed the Robot constructor to have a  IllegalArgumentException if the name argument is empty. I added an if statement at the beginning of the constructor to check if the name is valid. 

If the provided name is not valid, we "throw" an IllegalArgumentException with a descriptive error message. The term "throw" basically is basically like "throwing" the problem at Java and saying "There's a problem, you need to fix it". 

```c
    // Constructor 
    public Robot(String name, String model, int size) {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Name cannot be null or empty");
        }
        this.name = name;
        this.model = model;
        this.size = size;
    }

...//rest of the codee

    public void setName(String name) {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Name cannot be null or empty");
        }
        this.name = name;
    }

       
```

We can also declare an entire method with throws IllegalArgumentException. It's like putting a caution sticker on it and letting the other parts of the program know that this method might run into a problem. 

```c
    // Constructor 
    public Robot(String name, String model, int size) throws IllegalArgumentException {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Name cannot be null or empty");
        }
        this.name = name;
        this.model = model;
        this.size = size;
    }
...//rest of code
    public void setName(String name) throws IllegalArgumentException {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Name cannot be null or empty");
        }
        this.name = name;
    }

```

So if we throw the problem at Java, it needs to catch it in order to fix the problem? How does it do that? It does that by using the try-catch method. 

The first step in fixing the problem would be bundling the problem code into a set of curly braces with the key word "try". This is called a try block. 

```c
public class Main {
    public static void main(String[] args) {
        try {
            // Trying to create a robot with no name (illegal argument)
            Robot myRobot = new Robot("", "Ultron", 3);
       } 
```

This try block is saying that "We're calling the method to create an object but there might be a problem with it and it might throw an exception". 

If any part of the code inside the block throws an exception, we then move on to a catch block. The catch block catches the exception thrown within the try block. It hones in and specifies the type of exception it can handle (IllegalArgumentException in this case) and provides code to handle the exception. 

```c
public class Main {
    public static void main(String[] args) {
        try {
            // Trying to create a robot with no name (illegal argument)
            Robot myRobot = new Robot("", "Ultron", 3);
        }
        catch (IllegalArgumentException e) {
            // Handle the exception by setting a default name
            System.out.println("Error: Name cannot be null or empty");
            Robot myRobot = new Robot("DefaultName", "Ultron", 3);
           
        }
    }
}
```

IllegalArgumentException e specifies the type of exception that this catch block will try to handle. It catches any IllegalArgumentException thrown within the try block.

So the catch block in this example handles the exception by providing an error messags and then setting the empty name with a default name. 

What if the catch blocks dont match the type of the exception thrown? It would be like there was no try catch block implemented in the first place and the exception doesn't get caught at all. It'll keep going up and up each catch block to see one that matches and would be able to handle it. If it isn't able to find one, it'll keep going up the ladder until it reaches the main part of the program. If it still can't find a matching catch block there, the program will stop running and terminate, and you'll see an error message that will try to help figure what went wrong. Which is something that we use the try-catch blocks in the first place to avoid. 


So taking a step back overall and looking at the syntax involved in exception handling will look like this:  

```c
try {
    // Code that may throw an exception
} catch (ExceptionType1 e) {
    // Handle ExceptionType1
} catch (ExceptionType2 e) {
    // Handle ExceptionType2
} 
```

Throws Statement: 
```c
throw new ExceptionType("Error message");

```

Throws Statement with method: 
```c
public void method() throws ExceptionType {
    // Method code that may throw an exception
}
```

Flow Control During Exception Handling:

When an exception occurs inside the try block, the control will jump to the corresponding catch block that matches the type of the thrown exception.

If no catch block matches the thrown exception type, the control will jump up to the next higher level of the program.

If an exception occurs inside a catch block, then the exception will be handled. 


### Inheritance

Inheritance is a tool we use to be able to reuse code. The convenience of reusing the code is why we opt to do inheritance comapred to anything else. Basically what the word entails. We inherit things from our parents. In that same way, classes can inherit things from their parent classes. It’s like a chain. You can have a parent class (superclass) that have some variables and methods. You can pass that all down to a child class (subclass) that can “inherit” and use all of the variables and methods of the parent class, plus it can have it’s own special features as well. We use se the word “extends" to be able to do so. 

For example let's say we have a parent class for a camera. We want it to have the basic functions of being able to take a picture, zoom in, and zoom out. We can create a subclass of this Car class, let's say it's a GX 750 camera, and this will inherit all the basic fucntions of the parent class - being able to take a picture, zoom, etc. But there's a special feature in this type of camera. It can also record. So it has all the functionalities of the parent class + it's own special features. 

For inhertince, some parent classes can be abstract. This means that they can have abstract methods. These are methods that don't have any specific way of implemetation in the parent class, meaning we can use it however we want to in the subclass. It serves as a kind of like the baseline for the child classes to follow and build upon. Additionally, abstract classes cannot be instantiated. You can’t make an object with it. 

Let's look at an example: 

```c
// Abstract parent class for Camera
public abstract class Camera {
    // Method to take a picture - concrete method
    public void takePicture() {
        System.out.println("Taking a picture...");
    }

    // Method to zoom in - concrete method
    public void zoomIn() {
        System.out.println("Zooming in...");
    }

    // Method to zoom out - concrete method
    public void zoomOut() {
        System.out.println("Zooming out...");
    }

    // Recording - abstract method 
    public abstract void record();
}

// Child class -  GX750Camera extending the Camera class
public class GX750Camera extends Camera {
    // Implementation of the record method specific to GX750Camera
    @Override
    public void record() {
        System.out.println("Recording...");
    }
}

// Main class to test the Camera classes
public class Main {
    public static void main(String[] args) {
        // Create an instance of GX750Camera
        GX750Camera gx750 = new GX750Camera();

        // Use the inherited methods from the Camera class
        gx750.takePicture();
        gx750.zoomIn();
        gx750.zoomOut();

        // Use the specific method of GX750Camera
        gx750.record();
    }
}

```

In this example, Camera is an abstract class, but GX750Camera is a concrete class.  since it inherits all methods from Camera and provides concrete implementations for them. The record() method in the Camera class is declared as abstract, indicating that the concrete subclass of Camera must provide its own implementation for the record() method. When a subclass, such as GX750Camera, extends Camera, it must override the record() method and provide its own implementation, as shown here. 

A difference between concrete and abstract classes is that abstract classes can have both concrete and abstrat methods, but concrete classes can only have concrete methods and cannot have abstract methods.  Concrete classes are required to provide implementations for all methods, including any abstract methods inherited from their superclass. If a class has even one abstract method, it must be declared as abstract itself.

Abstract methods are meant to be implemented by the child classes, so they are only allowed in abstract classes or interfaces. Once a child clasass extends an abstract class and provides implementations for all abstract methods, it becomes a concrete class.

Also, abstract classes cannot be instantiated. This means you can't create objects of an abstract class directly using the "new" keyword. Concrete classes, on the other hand, you can directly create objects of concrete classes and use them in your code.


Superchaining is also a key part of inheritence. when you're building a new class that inherits from another class, super chaining helps you do that in a smooth way.

Constructor Chaining: Let's say you're making a new kind of camera, gx470, that's a bit different from a regular camera. But it still has some of the same basic features. When you make your new camera class, you can call the setup stuff from the regular camera class first, using super(), before adding your own unique setup for your new camera.

Superclass Methods: If your new camera class wants to use a function that's already defined in the regular camera class, you can do that easily with super. It's like saying, "Hey, regular camera, I want to use your function for taking pictures" before adding your own special stuff.

So, super chaining helps you take advantage of what's already built in the parent class while still adding your own flavor to the new class you're creating. It's like building on top of a solid foundation.


Inheritance is like passing down traits from parents to children.

Polymorphism (dynamic dispatching) s like having multiple shapes that can fit into the same hole. In programming, it means that objects of different classes can be treated as objects of the same parent class. 

So, how do they relate?

Well, when you use inheritance to create child classes, those child classes can be treated as objects of their parent class. This means that you can use polymorphism to work with objects of different child classes using a common interface provided by the parent class. In other words, you can treat objects of different child classes as if they were objects of the same parent class. 

So let's look at an example: 
```c
// Abstract parent class for Camera
public abstract class Camera {
    // Method to take a picture - concrete method
    public void takePicture() {
        System.out.println("Taking a picture...");
    }

    // Method to zoom in - concrete method
    public void zoomIn() {
        System.out.println("Zooming in...");
    }

    // Method to zoom out - concrete method
    public void zoomOut() {
        System.out.println("Zooming out...");
    }

    // Recording - abstract method
    public abstract void record();

    // Special feature - abstract method
    public abstract void specialFeature();
}

// child class GX750Camera extending the Camera class
public class GX750Camera extends Camera {
    // Implementation of the record method specific to GX750Camera - its only recording one second 
    @Override
    public void record() {
        System.out.println("Recording for one second...");
    }

    //  Another method specific to GX750Camera 
    @Override
    public void specialFeature() {
        System.out.println("Zooming by 0.5x...");
    }
}

// Subclass CanonShot extending the Camera class
public class CanonShot extends Camera {
    // Implementation of the record method specific to CanonShot
    @Override
    public void record() {
        System.out.println("Recording for two seconds...");
    }

    // Another method specific to CanonShot
    @Override
    public void specialFeature() {
        System.out.println("Taking a flash photo...");
    }
}

// Main class to test the Camera classes
public class Main {
    public static void main(String[] args) {
        // Create instances of GX750Camera and CanonShot
        Camera gx750 = new GX750Camera();
        Camera canonShot = new CanonShot();

        // Test GX750Camera
        System.out.println("Using GX750Camera:");
        gx750.takePicture();
        gx750.zoomIn();
        gx750.zoomOut();
        gx750.record();
        gx750.specialFeature();

        // Test CanonShot
        System.out.println("\nUsing CanonShot:");
        canonShot.takePicture();
        canonShot.zoomIn();
        canonShot.zoomOut();
        canonShot.record();
        canonShot.specialFeature();
    }
}

```
We have a parent class called Camera which contains common methods like taking a picture, zooming in, and zooming out.

There are two child classes: GX750Camera and CanonShot, each representing a specific type of camera.

Both child classes  specify how each camera records, and also specify the special feature

In the Main class:
We create instances of GX750Camera and CanonShot.

We treat them as Camera objects which means we can use the methods defined in the Camera class.

We call methods like takePicture, zoomIn, zoomOut, record, and specialFeature on each camera object.

Despite treating them as Camera objects, the specific methods in the child classes are executed and this is all thanks to polymorphism. This means that each camera behaves according to its specific type even though we interact with them through the Camera interface.


Both composition and inheritance are mechanisms for building relationships between classes, but they serve different purposes. To summarize, inheritance is more all about code reuse and specialization through an "is-a" relationship. So how like a "circle is a shape" sort of thing. Composition on the other hand is more has-a" relationship. Like how a "car has a wheel". It's more about like what it has instead of what it is. It's more about being flexible. 


But there are problems that come with inheritance. 

When you create different classes with different subclasses for each, it can get a little messy and disorganized. 

It can also get risky when two or more classes are highly dependent on each other. In other words, changes in one class may require you to change something in another class due to their close interconnection. This dependence on each other can make more difficult to maintain. 

Here's an example: 
```c
// Vehicle class
public class Vehicle {
    private String brand;
    private String model;

    // Constructor
    public Vehicle(String brand, String model) {
        this.brand = brand;
        this.model = model;
    }

   
    public String getBrand() {
        return brand;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }

    public String getModel() {
        return model;
    }

    public void setModel(String model) {
        this.model = model;
    }

    // Method to start the vehicle
    public void start() {
        System.out.println("Starting the vehicle...");
    }
}

// Car class inheriting from Vehicle
public class Car extends Vehicle {
    private int numDoors;

    // Constructor
    public Car(String brand, String model, int numDoors) {
        super(brand, model);
        this.numDoors = numDoors;
    }

    
    public int getNumDoors() {
        return numDoors;
    }

    public void setNumDoors(int numDoors) {
        this.numDoors = numDoors;
    }
}

// Boat class inheriting from Vehicle
public class Boat extends Vehicle {
    // Constructor
    public Boat(String brand, String model) {
        super(brand, model);
    }
}

// Main class to test the inheritance
public class Main {
    public static void main(String[] args) {
        // Creating a Car object
        Car car = new Car("Toyota", "Camry", 4);
        car.start(); // Car inherits the start() method from Vehicle

        // Creating a Boat object
        Boat boat = new Boat("SeaRay", "SRX230");
        boat.start(); // Boat also inherits the start() method, but boats don't have a start button
    }
}

```
SO in this example, we have a Vehicle class representing different types of vehicles and we have a Car subclass to represent cars and a Boat class to represet boats. The issue is that
Boat inherits the start() method from Vehicle andit doesn't make sense for boats to have a start() method because they don't operate like cars with a start button. This creates confusion and violates the principle of logical inheritance.

To fix this, we want to make sure that classes are less dependent on each other's details. 

Instead of directly depending on another class, we can define interfaces that outline what functionalities a class should have. Then, classes can interact through these interfaces rather than directly. This way, other classes don't need to know about the inner details and won't be affected if those details change.

Composition is another approach to address tight coupling. Instead of inheriting behavior from parent classes, a class can contain instances of other classes as members. This way, the class doesn't rely on the implementation details of other classes but rather on their interfaces or functionalities. With composition, we can easily change or replace the behavior of a class by changing the objects it contains without any harm. 

Let's fix the example: 

```c
public class Engine {
    public void start() {
        System.out.println("Starting the engine...");
    }
}


public class Vehicle {
    private String brand;
    private String model;
    private Engine engine; // Composition

    // Constructor
    public Vehicle(String brand, String model) {
        this.brand = brand;
        this.model = model;
        this.engine = new Engine(); // Create an Engine object
    }

   
    public String getBrand() {
        return brand;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }

    public String getModel() {
        return model;
    }

    public void setModel(String model) {
        this.model = model;
    }

    // Method to start the vehicle with engline
    public void start() {
        engine.start();
    }
}

// Car class
public class Car extends Vehicle {
    private int numDoors;

    // Constructor
    public Car(String brand, String model, int numDoors) {
        super(brand, model);
        this.numDoors = numDoors;
    }

    
    public int getNumDoors() {
        return numDoors;
    }

    public void setNumDoors(int numDoors) {
        this.numDoors = numDoors;
    }
}

// Boat class
public class Boat extends Vehicle {
    // Constructor
    public Boat(String brand, String model) {
        super(brand, model);
    }
}

// Main class to test the composition
public class Main {
    public static void main(String[] args) {
        // Creating a Car object
        Car car = new Car("Toyota", "Camry", 4);
        car.start(); // Car can start as it has an Engine

        // Creating a Boat object
        Boat boat = new Boat("SeaRay", "SRX230");
        boat.start(); // Boat can also start using its Engine
    }
}
```
So we introduced an Engine class that represents the engine of the vehicle. This means that the Vehicle class now has an Engine object as a member variable via composition. 
Each Vehicle can start using its Engine by calling the start() method call to the Engine object.

This approach separates everything more now the Boat class is now not inheriting unnecessary methods from the Vehicle class. 

## Interfaces

Interfaces are like blueprints for what a class is supposed to do or follow. It's like what lists out the requirements. For example, let's use our robot example. Interfaces only have abstract methods, which mean they don't have any bodies. 

Java interfaces help us to to model types. A type specificies the behavior without specifcying HOW that type should be implemented. It leaves it to us in how we want to use it. This is different from inheritanc because a parent class - child class relationship is not the same as a supertype - subtype relationship. 

WHen we implement a type in java, wer'e creating a supertype-subtype relationship even if we haven't used inheritance. So to summarize, inheritance is one form of code reuse. We could opt for convenience to create a superclass subclass relationship in order to reuse a package of code without caring whether the subclass that is reusing that code is actually a subtype of the superclass.

Let's say we want to create an interface that will allow us to upgrade our robot. This is how we would write it out: 

```c
// Upgradable interface
interface Upgradable {
    void upgrade();
}
```

We would then want to implement that using our Robot class. 

```c
public class Robot implements Upgradable {
    // Attributes or variables
    private String name;
    private String model;
    private int size;

   
    public Robot(String name, String model, int size) {
        this.name = name;
        this.model = model;
        this.size = size;
    }

    
    public void walk() {
        System.out.println(name + " is walking.");
    }

    
    public void liftBox() {
        System.out.println(name + " is lifting a box.");
    }

    // Method to upgrade the robot
    public void upgrade() {
        System.out.println(name + " is being upgraded with new arms.");
    }
}
```
We can make it our own depending on what we want it to do to the robot. For this one, we want to upgrade it with new arms. Let's say we want to implement it in a class Car. We can also implement Upgradable using class Car, but we can change the method to say "being upgraded with new wheels". 

This is how it'll look like in the main class: 

```c
public class Main {
    public static void main(String[] args) {
        // Create a Robot object
        Upgradable robot = new Robot("Robbie", "R2-D2", 3);

        //Methods from the Upgradable interface
        robot.upgrade();
    }
}
```

Now it'll upgrade the robot. We can change the method accordingly to whatever class we use to implement it. For example, if we implemented the method in a car class, we could alter it and say that it's being upgraded with new wheels. It's all up to us. 


Abstract class is like a half-built blueprint for classes to follow and it gives room for both completed and incomplete parts. Interface is like a strict set of rules that classes promise to obey while specifying only what methods should exist without providing the code for them. You can't directly use it to create objects but you can make new classes based on it. However, a class can only inherit or extend from one asbstract class. 

So essentially, abstract classes are used when you have a parent class that shares common behavior among several child classe and you expec them to have many common methods. 
Interfaces are used when you want to lay down a requirement for classes that share no commonality but need to provide a certain set of methods. 

Interfaces are also primarily used to enable polymorphism. Polymorphism is the ability of different objects to be treated as objects of a common type. Because different objects can be treated as instances of the same interface type, you can write code that works with objects of multiple classes without needing to know their specific types.


Here's an example of Polymorphism: interface Camera {
    void capturePhoto();
}

class Canon implements Camera {
    public void capturePhoto() {
        System.out.println("Capturing photo with Canon camera");
       
    }
}

class MirrorlessCamera implements Camera {
    public void capturePhoto() {
        System.out.println("Capturing photo with Mirrorless camera");
    }
}

class PointAndShootCamera implements Camera {
    public void capturePhoto() {
        System.out.println("Capturing photo with Point-and-Shoot camera");
    }
}

public class Main {
    public static void main(String[] args) {
        Camera dslrCamera = new DSLRCamera();
        Camera mirrorlessCamera = new MirrorlessCamera();
        Camera pointAndShootCamera = new PointAndShootCamera();

        dslrCamera.capturePhoto(); // Output: Capturing photo with Canon camera
        mirrorlessCamera.capturePhoto(); // Output: Capturing photo with Mirrorless camera
        pointAndShootCamera.capturePhoto(); // Output: Capturing photo with Point-and-Shoot camera
    }
}

We have different types of cameras, like Cannon, Mirrorless, and Point-and-Shoot. Even though these cameras work differently, they all share a common function: capturing a photo.
We create an interface called Camera that has a method capturePhoto(). This means any camera that wants to be part of our system must know how to capture a photo. Each type of camera (like Canon, Mirrorless, etc.) implements the Camera interface and provides its own way of capturing a photo. For example, a Canon might have a different process for capturing a photo compared to a Point-and-Shoot camera. In our code, we treat all cameras as instances of the Camera interface. This means we can call the capturePhoto() method on any camera object and the correct implementation for that specific type of camera will be use which we can do thanks to polymorphism.

You would typically use an interface when you want to make a rule sheet for classes that need to share common behavior but don't have a relationship. On the other hand, you would use an abstract class when you want to provide a common implementation for closely related classes that share a close relationship.


You don't need to use interfaces in all scenarios though. If you only need one way of doing something, using an interface might be overcomplicating things. Stick to simpler solutions by maybe making concrete classes. Also, if a behavior is only used inside one class and doesn't need to be shared, you don't need an interface. Keep it private to that class.
