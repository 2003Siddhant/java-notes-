Java is a high level programming language which says write once read everywhere (WORA)



Process flow of execution :

1\) we write the code in plain text file ending with .java extension.

2\) we run the java compiler and it checks error and converts it into .class file.

3\) The .class file doesn’t contain normal machine code; instead, it contains bytecode (a special set of instructions understood by the Java Virtual Machine).

4\) when we use the java launcher/command it starts the jvm . the JVM reads the bytecode and translates into the instructions that your computer processor can actually execute.





**JVM** : It is an abstract computing machine that is responsible for executing Java program. when we write a program then source code is compile code into bytecode which is understandable by jvm and jvm converts that into the instructions that your computer understands.

-> It is responsible for the very well-known feature of Java: cross-platform. That means you can write a Java program once and run it anywhere

-> JVM is platform-dependent (different implementations for Windows, Linux, etc.), but bytecode itself is platform-independent.





**JRE** : java runtime environment . its a package that provides everything needed to run Java programs.

-> it contains jvm and core libraries like collections and i/o.

-> it cant compile code . it only euns already compiled .class files. When you deploy your Java applications on client’s computer, the client needs a JRE to be installed.



**JDK** : java development kit. its superset of jre . its a full toolkit for developing java apps.

-> it contains jre as well as Development tools like javac (compiler), javadoc, jar, debugger, etc.





**PRIMITIVE DATATYPES** : this types are predefined by the language and named by a keyword. there are 8 of this ex: int , char, float, long, boolean, byte, short, double.

-> there default value is 0.



**REFERENCE DATATYPES** : Reference variables are created using defined constructors of the classes. They are used to access objects. These variables are declared to be of a specific type that cannot be changed. class , objects and various arrays variable are its ex.

-> its default value is null.







**VARIALBLE TYPES** : variable provide us with name storage that our program can manipulate . int a; means a can only store certain values that falls within certain range that int can hold.



a) local variable : its declared inside methods ,blocks . this are created when method is entered and will be destroyed when exited.

-> access modifiers can tbe used with local variables and this are implemented at stack internally. no default value so it should be initializes with some value



b) instance variable : Instance variables are declared in a class, but outside a method, constructor or any block.

-> this variables are created when an object is created with the use of the keyword 'new' and destroyed when the object is destroyed , when a space is allocated for an object in the heap, a slot for each instance variable value is created.

-> access modifiers can be used with them. for numbers the default values is 0, while for Boolean its false, and for object reference its null.can be accesed directly inside the class and is visible to every methods inside the class .



c) static/class variable : are declared with the static keyword in a class, but outside a method, constructor or a block. only 1 copy is created per variable as is distributed to every object . this are created when program starts and ends when it stops. ▪	Default values are same as instance variables





**MODIFIERS**: these are keywords that are added to the definition to change its meaning .



1\) default : we dont need to explicitly declare for the class , methods or constructors. this can be accesed by any other classes inside the package only and not outside.



2\) public : can be accesed from any other class inside or outside the packages .



3\) private : methods or constructors declared private can only be accesed inside that class. to access them outside the class we need to create the getter and setter methods.



4\) protected : those are declared protected can be accesed only within the package and only subclasses of that class can access outside the package



5\) final : this variables can be initialized only once and cant be overridden as its prevents methods from being modified in a subclass . also this class cant be inherited.





SCANNER CLASS : this is defined in java.util.package and it used to perform input operations . Scanner class breaks the input into tokens using a delimiter which is whitespace by default





\## **Logical OR** : java logical or operator used the concept of short circuiting . The || operator evaluates the left-hand operand first. If the left-hand operand evaluates to true, the operator immediately returns true and does not evaluate the right-hand operand. The second operand is only evaluated if the first one is false.

->improves performance by avoiding unnecessary computations and is essential for writing safe code, as it prevents potential errors like NullPointerException.



SWITCH : it is used to make a decision from the number of choices .First, the expression following the keyword switch is evaluated. The value is then matched, one by one, against the constant values that follow the case statements. when a value is matched in a switch statement, all subsequent case statements below that match will also be executed by default unless a break statement is encountered \[1, 2]. This behavior is known as "fall-through.



-> a do...while loop is similar to a while loop, except that a do...while loop is guaranteed to execute at least one time 



-> major diff between for and while loop is in for loop no of iterations is knows while its not in while loop.





-> variable storing reference means when obj is created it must be storedinside memory. so variable basically stores the address/refernce of the object inside the memory.



ARRAY : its a ds provided by java which is used to store ele of similar datatypes. its 0 based indexing. it provides some functions to manipulate array in arrays class.

--> asList : returns a fix sized list backed by an array ,  equals() , sort , copyof , 









































