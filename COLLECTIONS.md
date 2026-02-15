###### -> so its a framework where dynamically allocated ds are supported in a unified architecture . {hashmaps  hashset , arraylist , linkedlist }.

###### -> its simply a collection of objects , where each item in a collection is called an element . 

###### -> a framework is a set of interfaces that forces you to hold up some designing practices to improve productivity and maintenance.

###### -> Java Collections Framework is a set of reusable data structures and algorithms which are designed to free programmers from implementing data structures themselves so that they can focus on business logics. 

###### 

###### there are some hierarchy associated with collections that everyone should follow . 

###### 

1. ###### top of the chain is :
2. ###### &nbsp;***Iterable<E> Interface*** =>is an interface which takes a generic type E and read as Iterable of element of type E, declares one abstract method called iterator() to retrieve the Iterator<E> object associated with all the collections. 

###### ex:  Iterator<E> iterator();  Returns the associated Iterator ,that can be used to transverse thru all the elements of the collection , all implemenatations of this collection must implement this method . 

###### 

###### 2\. ***Iterator<E> interface***: it has 3 abstract methods a) boolean **hasnext**() : Returns true if it has more elements 

###### b) E **next**() : Returns the next element of generic type E. c) void **remove**() : Removes the last element returned by the iterator 

###### ex: list<String> lst = new Arraylist<String>(); lst.add("sidd") , lst.add("roman")

###### // retreiving iterator associated with the list via iterator method : Iterator<String> iter=lst.iterator();

###### 

###### 3\. ***Collection interface***: The Collection<E>, which takes a generic type E and read as Collection of element of type E, is the root interface of the Collection Framework. It defines the common behaviors expected of all classes, such as how to add or remove an element, via the following abstract methods: 

###### 

###### a) ***List<e>*** : list interface is a resizable linear array which allows indexed access, duplicates are allowed. ex: ArrayList, LinkedList, Vector 

###### 

###### b) **Set<e>** : here no duplicate elements are allowed. ex: hashset , treeset

###### 

###### c) **Queue<E>** : interface models queues such as First-in-First-out (FIFO) queue and priority queue . ex: priority queue , ArrayDeque 

###### 

###### d) **Map<K,V>,** : it takes 2 generic types k and v which are basically key and value pairs. no dupicates are allowed. ex: hashmap , hashtable.

###### 

###### -> common methods include add(), addall() , remove , removeall , size, clears , contains, containsall , itreator ,  toarray , isempty

###### 



###### ***LIST***<i> :</i> this interface provides2 major implementations that are arraylist and linkedlist.

###### a) Arraylist : java ArrayList class uses a dynamic array (Resizable Array Data Structure) for storing the elements. It extends AbstractList class and implements List interface. it contains duplicates , non synchronized and ordering matters and allows random access due to indexing. slower in compared to array and also not thread safe.

###### 

###### ex: List<Integer> lst = new Arraylist<>(); here we have created arrlst using empty constructor. it means list has an initial capacity of 10. 

###### --> It’s also possible to construct a list that takes elements from an existing collection, for example: 

###### List<Integer> listNumberOne;      // existing collection 

###### List<Integer> listNumberTwo = new ArrayList<>(listNumberOne); 

###### 

###### **q.) suppose i declare a iterator and print the values. then after some time when i made some changes like update and rmove so do i need to make the new iterator or can use the same one**

###### **ans=> yes we need to create a new iterator when we have some modifications in the list as iterator will traverse the list as it exists at that moment.**

###### 

###### MEthods : for **insertion**: add , insertion at specific posn: add(1,"sidd") , **update**: set(1,"asjka") , **retreival** : get(index\_no) , for the **remove** method it compares ele in the list using the equals method. if there are duplicates then it only removes the first occurence. to remove all ele we use clear() .

###### 

###### \# iterating over list : create an iterator that points to the list iterator.

###### Iterator<string> it=lst.iterator() ;

###### while(it.hasNext() ) {

###### &nbsp;	

###### &nbsp;	print(it.next() );

###### }

###### 

###### \# **searching** the ele : lst.contains (" ") ;



###### **q.) for searching we use contains so does contains methods runs a loop internally or we need to have our loop**

###### **ans=> The contains() method in Java’s List (like ArrayList) does run a loop internally — you don’t need to write your own loop for it.**

###### **--> internally it has contains(object o) so it - it iterates through the list elements one by one and checks each element using .equals(o).**

###### **--> returns a boolean value as a result.** 

###### 

###### \# Copying one list into another :  we can copy using collections.copy(dest , src) where src list is copied to destination list.

###### \# reverse : collections.reverse(lst) used to reverse the list using collections .

###### 

###### \# converting list to array : using toArray function ex: Integer\[] num = lst.toArray (new Integer \[0])

###### 

--> ▪	Vector is similar to arraylist but with 2 differences i.e vector is synchronized ,Vector contains many legacy methods that are not part of the collections framework 



STACK : Stack is a subclass of Vector that implements a standard last-in, first-out stack. similar to vector that is synchronized . has push, pop, peek, empty.

###### 



\# iteration in Collections : there are 4 ways : traditional for loop , iterator based loop , enhanced for loop (uses iterator behind the scenes) and the

&nbsp;for each loop list.forEach(a -> print a); it takes a lambda expression.







2\) ***SET COLLECTION :*** Set is a type of collection that does not allow duplicate elements. also Elements are not stored in order so no sorting.

-> abstractSet implements the set<e> and hashset , treeset extends the abstractSet



a) HashSet : no duplication and unordered, uses hashtable to store the elements , extends abstractSet and implements the set interface. no ordering means no sorting . stores info using a mechanism called as hashing where info content of a key is used to determing a unique content called as hashcode. suppose every content is treated as a key and for every key a unique hashcode is generated and due to this we can store only unique ele .

imp : default capacity of hashset is 16.

-> has methods like add , clear , contains , isempty , remove . ex:  Set<Integer> st=new HashSet<>();

-> if(st.add("" )) then add() method returns true if the set does not contain the specified element, and returns false if the set already contains the specified element

-> set can contain null ele.













































