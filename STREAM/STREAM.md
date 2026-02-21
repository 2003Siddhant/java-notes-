JAVA STREAMS : 



-> A stream is used to process collections of data (like arrays, lists) efficiently using functional programming.

&nbsp;its like a pipeline through which data flows and gets processed step-by-step

-> earlier for collection processing we used to write foreach loop , temp list , manual counters. this approach is good but its often repetitive , error prone , harder to read .



Stream provides a better style . supports aggregate operations  and can be processed sequentially as well as parallel .

-> its a ds but doesn't store data and is not a collection. collections store the data and it processes them.

-> dont modify the original data and returns new result. Stream operations execute only when required.



\# Stream pipeline : 1) Source (collection / arr/ str) , 2) 0 or more Intermediate operations 3) 1 terminal operation



\# intermediate operations/methods : 1) every methods returns a new stream 2) dont execute immediately 3) ex: filter , map , sorted , limit , skip .



\# terminal operations : 1) it triggers execution 2) every stream must have 1 terminal operation 3) may produce final result 4) ends the stream.



1\) filter in streams: it takes a predicate function and do some condn check and remove ele that doesn't match the condn. no lazy execution.

ex: names

&nbsp;	.stream()

&nbsp;	.filter(x -> x%2==0)

&nbsp;	.forEach(print() )





Predicate : functional interface that represents a single-argument function returning a boolean value. - It has one abstract method: test(T t). returns true if yes else false. java internally converts the lambda into predicate . Predicate<Integer> even = x -> x%2==0;





2\) Map : is used to transform each element of a stream into another form. It does 1-to-1 transformation: i.e 1 i/p ele -> 1 o/p ele. doesn't remove ele , add extra ele or change stream size.

map accepts function<T,R>. so i/p type is T and o/p type is R and it converts T to R. returns stream<R>.

ex: using object employees.stream()

&nbsp;        		  .map(e -> e.salary + 5000)                                   

&nbsp;       		  .forEach(System.out::println);



->   list.Stream()

&nbsp;   .map(x -> "Number: " + x)

&nbsp;   .forEach(System.out::println);

-> we can chain multiple maps inside 1 another 



a) mapToInt: Converts stream elements into primitive int stream. usually normal map returns Stream<Integer> , but this returns IntStream (primitive int).

-> its imp because it Avoids boxing/unboxing overhead → faster.

-> it gives direct max , min , sum ,avg functions.



b) mapToDouble : Same as mapToInt but returns double stream.



c) flatmap: where each ele of map contains a collection. it takes a function t and returns a mapper stream. it merges all stream at once.

ex: 	  customers.stream()

&nbsp;        .flatMap(c -> c.getOrders().stream())

&nbsp;        .forEach(System.out::println);



d) distinct : removes duplicate ele . works using equals + hashcode . for custom object it must override equals and hashcode .

ex:  list.stream()

&nbsp;   .distinct()

&nbsp;   .forEach(System.out::println);





\### here **System.out::println** is a method reference in Java. shorthand for lambda expression . means call println method of System.out for each element . same as x -> System.out.println(x).

--> system is a class in java and out is A static object inside System class with type = printstream. println is a method of printstream class.  (::) is called method reference operator.



5\) sorted(Comparator): sorted(Comparator) in streams is used to sort elements using a custom sorting logic instead of default ordering. its a functional interface. 

ex: interface Comparator<T>{          negative → a comes before b

&nbsp;	int compare(T a, T b);	      positive → b comes before a

}				      zero     → equal

&nbsp;      













\- A functional interface is an interface with exactly one abstract method.

\- A lambda expression is a concise way to provide the implementation of that single abstract method.

\-  lambdas are used to implement functional interfaces.























































