###### oops is basically a way for modelling software entities as a real world objects that have state(data) , behaviours(methods) AND interact with each other.

###### 

###### Banking Software

######         - Customer has data (name, account\_id, balance, KYC details, etc.)

######         - Customer can do actions (open accounts, deposit, withdraw, transfer etc.)

######         - different customer behave similarly but have different values (balance differs)

###### 

######     - OOP lets you represent this in code cleanly.

###### 

###### -> class is basically a blueprint/template which has data members and member functions.

###### -> object is basically instance of the class created at runtime. ex: classname a = new classname(); obj is always created using new keyword as its stored inside heap.

###### 

###### a) ***Static variables*** : its declared inside a class and has only one copy and is distributed among all the objects . ex: when we create bank class and objects as its customers then we can create a static variable an increase its val inside the constructor to know how many customers are there of that bank.

###### b) ***static methods*** : this are accessible without creating any object of the class like we dont need to create any object to access methods of static .

###### c) ***static class*** : such class cant be inherited and are somewhat final.

###### 

###### 

###### 1\) ***Encapsulation*** : just binding together data and information in a single unit. like having access modifiers so that not anyone can modify our data and also data that is inserted is also valid like our age cant be negative . all members should be private and getters and setters should be available.

###### 



###### 2\) ***Constructors*** : its a function that  gets created/executed when an object is created in runtime. name should be same as class and no return type. it ensures that object starts its life in a valid state. ex: the practical use case is basically used in file opening and resource management like when we hit the server , db allocates everyone its resources .

###### -> it can be default , parameterized , overloaded

###### -> valid access modifiers are : default => only accessible within same package

######  public : can be accessed from anywhere inside and outside the package

######  private : accessible within the same class

######  protected : accessible only within the same package , subclasses can access even in different package.

###### 



###### 3\) ***Method overloading*** : same method name, but diff parameters. its a compile type polymorphism. Java picks the “most specific” match, by matching the parameters between the calling method and declared methods . this decision is taken during compile time ex: if method overloaded is of int and main values passed is of byte, then its compilers work to so the things.

###### 



###### 4\) ***Static binding***:  When does the static binding happens?

######  -> when the method call is resolved at compile time it is called "Static binding"

######  -> static methods

######  -> final methods - always bound at compile time , because they cant be overridden and always invoked at compile time.

######  -> private methods - compiler binds private methods at compile time

######  -> method overloading - depends on parameters / parameter types, it is decided at compile time

###### 

######    class Parent {

######                 static void show(){

######                     sysout("Parent");

######                 }

######             }

###### 

######   class Child extends Parent {

######                 static void show(){

######                     sysout("Child");

######                 }

######             }

###### 

######             Parent p = new Child();

######  	    p.show();

###### 

###### // we have created child object and stored its reference inside p variable . when we do p.show() it generally calls the show function of parent as At runtime, the JVM looks at the actual object that p points to and object is of child type.

###### -> but for this code it will call parent class show() because method is static it is not overridden, and the method call is resolved by reference type so jvm will decide which function to call during compile time.

###### -> in java, a parent class variable can reference to a child object

######  



###### 5\) ***Inheritance*** : mechanism where a class (subclass/child class) acquires the properties and behavior of another class (parent class/superclass).  used for code reusability , local hierarchy , enable runtime polymorphism and reduces duplication.

###### -> represents a relationship between a superclass and subclass and it supports single inheritance and not multiple due to ambiguity.

###### 

###### **Q) Why java doesn't support multiple inheritance**

###### **Ans: avoid ambiguity in method resolution, data conflicts, constructor initialization issues , avoid commonly known diamond problem**

###### ** --\*\*Java supports multiple inheritance through interfaces - ensures clarity, type safety and predictable runtime behavior**

###### 

###### **-> super(): by default, child class constructor always invokes superclass's no-arg constructor , constructor are not inherited but parent class constr. can be invoked using super , super always refers to the immediate parent class. super helps subclasses access parent class members when they are hidden, overridden, or need explicit constructor calls.**

###### 

###### 

###### **--> Loose coupling :designing principle where classes or modules have minimal dependency on each other. we can achieve it through runtime polymorphism .  Classes interact through well-defined interfaces or abstractions, not direct implementation details. This makes the system more flexible, maintainable, and testable**

###### **--> Tight coupling : classes/modules are highly dependent on each other and some changes in one class often require changes in others. its difficult to maintain and update and also harder to test in isolation.**

###### 

###### 



###### 6\) **Object Class**: its the root class and super/top most class and all other class inherits from it. it provides some methods that all java objects should have like toString(), equals() and hashcode() , finalize() , wait().

###### 

###### 

###### 7\) **Abstract Classes** : its a class that cant be instantiated means object cant be created and its basically use mostly for laying out the blueprint of how the code structure looks like and abstract methods will always be overridden by the subclasses. it may or may not have abstract methods.

###### -> if a class has an abst. methods then that class must be declared abstract . abs methods are just declared without an implementation.

###### -> abstract modifier means that class will always be used as an superclass.

###### -> abstract methods will never be static or final as they will always be overridden.

###### -> abstract classes are not interfaces.

###### -> Abstract methods are usually declared where two ore more subclasses are expected to do a similar thing in different ways through different implementations

###### -> private and static methods can also not be abstract.

###### 



###### 

###### 8\) ***Interface*** : an interface in java is a "pure contract" that defines what a class "Can do" , that basically we define behaviour first, implementation later.

######  an interface defines set of requirements that a class has to implement . like animal interface will only define function make-sound but wont implement it.

###### --> class uses implements keyword to implement an interface. class that is implementing the interface must override all the abst. methods.

###### ->a class can implement several interfaces , an interface can extend several interfaces , java7 interface contains only "abstract" methods , java8 contains public and static meth as well.

###### in java9 private is also allowed.

###### -> Interface is used to achieve complete abstraction in java. Interface must contain abstract methods only . its also used to overcome the problem of multiple inheritance as multiple interfaces can be implemented by a single class.

###### -> it also enables loose coupling . ex: Real software must be: scalable , replaceable , loosely coupled

###### ex: suppose there are multiple Payment Gateway options like paypal , Razorpay , stripe. all have different options of payment. so we can create an interface of pay and every PaymentGateway

###### class can implement it . so when the option changes we can switch the pay option as pay function will be overridden by all the classes.

###### -> abstract classes represent real objects , interface represents "capabilities" / "requirements", not objects .

###### -> All variables declared inside interface are implicitly public static final variables

###### 

###### 

###### 

###### 9\) ***toString*** : The toString() method returns the string representation of the object ,If you print any object, java compiler internally invokes the toString() method on the object. usually when we print the obj it returns as an hashcode and classname . so to give our own implementation we use this method.

###### -> toString() is a method from the Object class. java.lang.Object, we can override this in any class for some meaningful info about the object .

###### @override

###### public String toString() {

######  	return {};

###### 

###### 

###### 10\) ***Equals*** : used to compare 2 objects and returns a Boolean value. == operator compares two objects technically (by comparing their references i.e. memory addresses). but this compares but comparing with data members of the class. ex: suppose class has name , id , age . multiple people can have same name and age but there id will always be unique. so the default equals object takes into consideration all the data members. so due to this we override the equals object so that we can have custom comparison of 2 objects. by default, it compare the references of the given variables, not the contents

###### 

###### @Override

###### public boolean equals(Object obj) {  --> - Must accept Object obj because it overrides Object.equals().

######     if (obj instanceof Student) {    --> - Ensures the passed object is actually a Student

######         Student another = (Student) obj;     --> just downcasting for safety

######         if (this.id.equals(another.id) \&\&

######             this.name.equals(another.name) \&\&  --> field comparison between 2 objects name,email and all

######             this.email.equals(another.email) \&\&

######             this.age == another.age) {

######             return true;

######         }

######     }

######     return false;

###### }

###### 



###### 

###### 11\) ***Hashcode*** : returns an int num. This hash number is used by hashtable-based collections like Hashtable, HashSet and HashMap to store objects in small containers called “buckets”. Each bucket is associated with a hash code, and each bucket contains only objects having identical hash code.when we add objects of a class to a hashtable-based collection (HashSet, HashMap), the class’s hashCode() method is invoked to produce an integer number (which can be an arbitrary value). This number is used by the collection to store and locate the objects quickly and efficiently, as a hashtable-based collection does not maintain order of its elements.

###### 

###### \# some rules between hash code and equals to be followed when using hash tables based ds:

###### 1\) When the equals() method is overridden, the hashCode() method must be overridden as well.

###### 2\) If two objects are equal, their hash codes must be equal as well. if two objects are not equal, there’s no constraint on their hash codes , if two objects have different hash codes, they must not be equal

###### 

###### 



###### 12\) ***Enum*** : - An enum is like a class, but instead of fields and methods, it primarily contains constants. Each constant is actually an instance of the enum type.

###### \- An enum is like a class, but instead of fields and methods, it primarily contains constants.

###### \- Each constant is actually an instance of the enum type.

###### 

###### Enum level{

######    low , medium , high

###### }

###### 

###### 



###### 13\) ***Wrapper classes*** : in java everything is oop but primitive dt are not objects. ex: int , char , double , float , Boolean .

###### -> Java created Wrapper Classes to convert these primitives into objects. So wrapper classes “wrap” primitive values inside objects.

###### Q) why ? -> Because collections in java only stores objects like arraylist and hashmap. Arraylist<int> arr is invalid . so due to this we use Arraylist<Integer>arr;

###### -> Many Java frameworks and APIs work only with objects. Primitive cannot store null, but wrapper can. they provide many utility methods like Integer.parseInt() ,Character.isDigit()

###### -> Integer a = 10; Java automatically converts primitive → object. This is called Autoboxing. stored in heap . The wrapper classes are immutable; we cannot change a wrapped value after the wrapper has been constructed. They are also final, so we cannot subclass them

###### 

##### ***New concept :***

###### **ex: Integer a=131, b=131; then if (a==b) if we see the ans should be true as both a and b points to the same memory reference. but the ans is false as in wrapper class Integer when we assign a primitive value, java calls the integer.valueof method behind the scenes.** 

###### **Integer class contains a private static inner class called IntegerCache that stores an array of pre created int objects. if value ffalls within the cache range, valueof returns same reference from this array insted of creating a new object. this saves memory by avoiding duplicate objects for frequently used values.**

###### **-> default range is -128 to 127.**

###### 

###### 

###### 14\) ***Exception Handling*** : Exception handling is a mechanism to handle runtime errors so that program doesn’t crash.

###### --> An exception is an abnormal event that arises during the execution of the program and disrupts the normal flow of the program. Abnormality do occur when your program is running.

###### -> 2types of this : compile time :IOException , SQLException , FileNotFoundException

###### and runtime : ArithmeticException , NullPointerException , ArrayIndexOutOfBoundsException .

######  .1. try = Code that may cause error is written here. ,2. catch=Handles the exception. ,3. finally =Always executes (optional). ,

###### 4\. throw=Used to throw exception manually.

###### -> finally is mostly used for closing db connection , files

###### -> we can create our own custom exception . ex: class ageException extends Exception { public ageException (String msg) { super (msg) } }

###### 

###### 

###### 

###### 

###### 

###### 

