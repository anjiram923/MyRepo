# Java Collection Framework

- Any group of individual objects which are represented as a single unit is known as the collection of the objects. In Java, a separate framework named the “Collection Framework” has been defined in JDK 1.2 which holds all the collection classes and interface in it.

- The Collection interface (java.util.Collection) and Map interface (java.util.Map) are the two main “root” interfaces of Java collection classes.

**Advantages of the Collection Framework:** Since the lack of a collection framework gave rise to the above set of disadvantages, the following are the advantages of the collection framework.

**Consistent API:** The API has a basic set of interfaces like Collection, Set, List, or Map, all the classes (ArrayList, LinkedList, Vector, etc) that implement these interfaces have some common set of methods.
Reduces programming effort: A programmer doesn’t have to worry about the design of the Collection but rather he can focus on its best use in his program. Therefore, the basic concept of Object-oriented programming (i.e.) abstraction has been successfully implemented.
Increases program speed and quality: Increases performance by providing high-performance implementations of useful data structures and algorithms because in this case, the programmer need not think of the best implementation of a specific data structure. He can simply use the best implementation to drastically boost the performance of his algorithm/program.


|Sr.No.|	Interface Name|  Description|
|------|------------------|-------------|
|1|	The Collection Interface| This enables you to work with groups of objects; it is at the top of the collections hierarchy.|
|2|	The List Interface|This extends Collection and an instance of List stores an ordered collection of elements.|
|3|	The Set|This extends Collection to handle sets, which must contain unique elements.|
|4|	The SortedSet|This extends Set to handle sorted sets.|
|5|	The Map|This maps unique keys to values.|
|6|	The Map.Entry|This describes an element (a key/value pair) in a map. This is an inner class of Map.|
|7|	The SortedMap|This extends Map so that the keys are maintained in an ascending order.|
|8|	The Enumeration|This is legacy interface defines the methods by which you can enumerate (obtain one at a time) the elements in a collection of objects. This legacy interface has been superceded by Iterator.|

#### ArrayList
- The ArrayList class implements the List interface. It uses a dynamic array to store the duplicate element of different data types. The ArrayList class maintains the **insertion order and is non-synchronized.** The elements stored in the ArrayList class can be randomly accessed. Consider the following example.

    ````java
        import java.util.*;  
        class TestJavaCollection1{  
            public static void main(String args[]){  
                ArrayList<String> list=new ArrayList<String>();//Creating arraylist  
                list.add("Ravi");//Adding object in arraylist  
                list.add("Vijay");  
                list.add("Ravi");  
                list.add("Ajay");  
                //Traversing list through Iterator  
                Iterator itr=list.iterator();  
                while(itr.hasNext()){  
                    System.out.println(itr.next());  
                }  
            }  
        } 
        /* 
        Output:

        Ravi
        Vijay
        Ravi
        Ajay
        */
    ````


#### LinkedList
- LinkedList implements the Collection interface. It uses a doubly linked list internally to store the elements. It can store the duplicate elements. **It maintains the insertion order and is not synchronized. In LinkedList, the manipulation is fast because no shifting is required.**

    Consider the following example.
    
    ````java
    import java.util.*;  
    public class TestJavaCollection2{  
        public static void main(String args[]){  
            LinkedList<String> al=new LinkedList<String>();  
            al.add("Ravi");  
            al.add("Vijay");  
            al.add("Ravi");  
            al.add("Ajay");  
            Iterator<String> itr=al.iterator();  
            while(itr.hasNext()){  
                System.out.println(itr.next());  
            }  
        }  
    }  
    /*
    Output:

    Ravi
    Vijay
    Ravi
    Ajay
    */
    ````

#### Vector
- Vector uses a dynamic array to store the data elements. **It is similar to ArrayList. However, It is synchronized and contains many methods that are not the part of Collection framework**.

    Consider the following example.

    ````java
    import java.util.*;  
    public class TestJavaCollection3{  
        public static void main(String args[]){  
            Vector<String> v=new Vector<String>();  
            v.add("Ayush");  
            v.add("Amit");  
            v.add("Ashish");  
            v.add("Garima");  
            Iterator<String> itr=v.iterator();  
            while(itr.hasNext()){  
                System.out.println(itr.next());  
            }  
        }  
    } 
    /* 
    Output:

    Ayush
    Amit
    Ashish
    Garima
    */
    ````

#### Stack
- The stack is the subclass of Vector. **It implements the last-in-first-out data structure, i.e., Stack. The stack contains all of the methods of Vector class and also provides its methods like boolean push(), boolean peek(), boolean push(object o), which defines its properties**.

    - Consider the following example.

    ````java
    import java.util.*;  
    public class TestJavaCollection4{  
        public static void main(String args[]){  
            Stack<String> stack = new Stack<String>();  
            stack.push("Ayush");  
            stack.push("Garvit");  
            stack.push("Amit");  
            stack.push("Ashish");  
            stack.push("Garima");  
            stack.pop();  
            Iterator<String> itr=stack.iterator();  
            while(itr.hasNext()){  
                System.out.println(itr.next());  
            }  
        }  
    }  
    Output:

    Ayush
    Garvit
    Amit
    Ashish
    ````


#### Queue Interface
#### PriorityQueue
#### Deque Interface
#### ArrayDeque

#### Set Interface
- Set Interface in Java is present in java.util package. It extends the Collection interface. **It represents the unordered set of elements which doesn't allow us to store the duplicate items. We can store at most one null value in Set.** Set is implemented by HashSet, LinkedHashSet, and TreeSet.

    Set can be instantiated as:
    ````java
    Set<data-type> s1 = new HashSet<data-type>();  
    Set<data-type> s2 = new LinkedHashSet<data-type>();  
    Set<data-type> s3 = new TreeSet<data-type>();  
    ````

#### HashSet
- HashSet class implements Set Interface. It represents the collection that uses a hash table for storage. Hashing is used to store the elements in the HashSet. **It contains unique items. (it will allow one null element to store)**

    Consider the following example.

    ````java
    import java.util.*;  
    public class TestJavaCollection7{  
        public static void main(String args[]){  
            //Creating HashSet and adding elements  
            HashSet<String> set=new HashSet<String>();  
            set.add("Ravi");  
            set.add("Vijay");  
            set.add("Ravi");  
            set.add("Ajay");  
            //Traversing elements  
            Iterator<String> itr=set.iterator();  
            while(itr.hasNext()){  
                System.out.println(itr.next());  
            }  
        }  
    }  
    Output:

    Vijay
    Ravi
    Ajay
    ````


#### LinkedHashSet
- LinkedHashSet class represents the LinkedList implementation of Set Interface. It extends the HashSet class and implements Set interface. Like HashSet, **It also contains unique elements. It maintains the insertion order and permits null elements (only one).**

    Consider the following example.

    ````java
    import java.util.*;  
    public class TestJavaCollection8{  
        public static void main(String args[]){  
            LinkedHashSet<String> set=new LinkedHashSet<String>();  
            set.add("Ravi");  
            set.add("Vijay");  
            set.add("Ravi");  
            set.add("Ajay");  
            Iterator<String> itr=set.iterator();  
            while(itr.hasNext()){  
                System.out.println(itr.next());  
            }  
        }  
    }  
    Output:

    Ravi
    Vijay
    Ajay
    ````

#### SortedSet Interface
- SortedSet is the alternate of Set interface **that provides a total ordering on its elements.** The elements of the SortedSet are arranged in the **increasing (ascending) order.** The SortedSet provides the additional methods that inhibit the natural ordering of the elements.

    The SortedSet can be instantiated as:

    ````java
    SortedSet<data-type> set = new TreeSet();  
    ````

#### TreeSet
- Java TreeSet class implements the Set interface that uses a tree for storage. **Like HashSet, TreeSet also contains unique elements. However, the access and retrieval time of TreeSet is quite fast. The elements in TreeSet stored in ascending order. TreeSet does not permit null value.** If you insert null value into TreeSet, it will throw NullPointerException.

    Consider the following example:
    ````java
    import java.util.*;  
    public class TestJavaCollection9{  
        public static void main(String args[]){  
            //Creating and adding elements  
            TreeSet<String> set=new TreeSet<String>();  
            set.add("Ravi");  
            set.add("Vijay");  
            set.add("Ravi");  
            set.add("Ajay");  
            //traversing elements  
            Iterator<String> itr=set.iterator();  
            while(itr.hasNext()){  
                System.out.println(itr.next());  
            }  
        }  
    }  
    /*
    Output:

    Ajay
    Ravi
    Vijay
    */
    ````


#### Differences Between HashSet, LinkedHashSet, and TreeSet: 

|Features|HashSet|LinkedHashSet|TreeSet|
|--------|-------|-------------|-------|
|Internal Working|HashSet internally uses HashMap for storing objects|LinkedHashSet uses LinkedHashMap internally to store objects|TreeSet uses TreeMap internally to store objects|
|When To Use|If you don’t want to maintain insertion order but want to store unique objects|If you want to maintain the insertion order of elements then you can use LinkedHashSet|If you want to sort the elements according to some Comparator then use TreeSet|
|Order|HashSet does not maintain insertion order|LinkedHashSet maintains the insertion order of objects|While TreeSet orders the elements according to supplied Comparator. By default, objects will be placed according to their natural ascending order.|
|Complexity of Operations|HashSet gives O(1) complexity for insertion, removing, and retrieving objects|LinkedHashSet gives insertion, removing, and retrieving operations performance in order O(1).|While TreeSet gives the performance of order O(log(n)) for insertion, removing, and retrieving operations.|
|Performance|The performance of HashSet is better when compared to LinkedHashSet and TreeSet.|The performance of LinkedHashSet is slower than TreeSet. It is almost similar to HashSet but slower because LinkedHashSet internally maintains LinkedList to maintain the insertion order of elements|TreeSet performance is better than LinkedHashSet except for insertion and removal operations because it has to sort the elements after each insertion and removal operation.|
|Compare|HashSet uses equals() and hashCode() methods to compare the objects|LinkedHashSet uses equals() and hashCode() methods to compare it’s objects|TreeSet uses compare() and compareTo() methods to compare the objects|
|Null Elements|HashSet allows only one null value.|LinkedHashSet allows only one null value.|TreeSet does not permit null value. If you insert null value into TreeSet, it will throw NullPointerException.|
|Syntax|HashSet obj = new HashSet();|LinkedHashSet obj = new LinkedHashSet();|TreeSet obj = new TreeSet();|

- Differences Between HashSet, LinkedHashSet, and TreeSet According to Insertion Order and Time Taken:
 

    ````java
    // Java program to demonstrate difference between
    // HashSet, LinkedHashSet and TreeSet according
    // to insertion order and insertion time
    
    import java.util.Arrays;
    import java.util.HashSet;
    import java.util.LinkedHashSet;
    import java.util.TreeSet;
    
    class GFG1 {
        // Function show insertion order of
        // LinkedHashSet, TreeSet and HashSet
    
        private static void insertionOrder()
        {
            LinkedHashSet<String> geekLinkSet
                = new LinkedHashSet<>();
            TreeSet<String> geekTreeSet = new TreeSet<>();
            HashSet<String> geekHashSet = new HashSet<String>();
    
            // Add three object in
            // LinkedHashSet and TreeSet
            for (String str : Arrays.asList("Geek2", "Geek1",
                                            "Geek3", "Geek1")) {
    
                geekLinkSet.add(str);
                geekTreeSet.add(str);
                geekHashSet.add(str);
            }
    
            // should be sorted order HashSet
            // stores element in sorted order
            System.out.println("Insertion Order"
                            + " of objects in HashSet :"
                            + geekHashSet);
    
            // insertion order or elements LinkedHashSet
            // storeds elements as insertion
            System.out.println("Insertion Order of "
                            + "objects in LinkedHashSet :"
                            + geekLinkSet);
    
            // should be sorted order TreeSet
            // stores element in sorted order
            System.out.println("Insertion Order of"
                            + " objects in TreeSet :"
                            + geekTreeSet);
        }
    
        // Function calculate insertion time of
        // 1000 objects of LinkedHashSet,
        // TreeSet and HashSet
    
        private static void insertionTime()
        {
            // HashSet performance Test
            // inserting 1000 elements
            HashSet<Integer> numbersHS = new HashSet<>();
            long startTime = System.nanoTime();
            for (int i = 0; i < 1000; i++) {
                numbersHS.add(i);
            }
            long endTime = System.nanoTime();
            System.out.println("Total time to insert"
                            + " 1000 elements in"
                            + " HashSet in nanoseconds: "
                            + (endTime - startTime));
    
            // LinkedHashSet performance Test
            // inserting 1000 elements
            LinkedHashSet<Integer> numbersLLS
                = new LinkedHashSet<>();
    
            startTime = System.nanoTime();
            for (int i = 0; i < 1000; i++) {
                numbersLLS.add(i);
            }
            endTime = System.nanoTime();
            System.out.println("Total time to insert"
                            + " 1000 elements in"
                            + " LinkedHashSet nanoseconds: "
                            + (endTime - startTime));
    
            // TreeSet performance Test inserting 1000 objects
            TreeSet<Integer> numbersTS = new TreeSet<>();
    
            startTime = System.nanoTime();
            for (int i = 0; i < 1000; i++) {
                numbersTS.add(i);
            }
            endTime = System.nanoTime();
            System.out.println("Total time to insert"
                            + " 1000 elements in"
                            + " TreeSet in nanoseconds: "
                            + (endTime - startTime));
        }
    
        // Function calculate deletion time
        // of 1000 objects LinkedHashSet,
        // TreeSet and HashSet
        // Deletion time always vary
        private static void deletion()
        {
            // HashSet performance Test inserting
            // and deletion 1000 elements
            HashSet<Integer> deletionHS = new HashSet<>();
    
            for (int i = 0; i < 1000; i++) {
                deletionHS.add(i);
            }
    
            long startingTime = System.nanoTime();
            for (int i = 0; i < 1000; i++) {
                deletionHS.remove(i);
            }
    
            long endedTime = System.nanoTime();
            System.out.println(
                "Total time to Deletion "
                + "1000 elements in HashSet in nanoseconds: "
                + Math.abs(startingTime - endedTime));
    
            // LinkedHashSet  performance Test inserting
            // and deletion 1000 elements
            LinkedHashSet<Integer> deletionLLS
                = new LinkedHashSet<>();
    
            for (int i = 0; i < 1000; i++) {
                deletionLLS.add(i);
            }
            startingTime = System.nanoTime();
            for (int i = 0; i < 1000; i++) {
                deletionLLS.remove(i);
            }
    
            endedTime = System.nanoTime();
            System.out.println(
                "Total time to Deletion 1000"
                + " elements in LinkedHashSet in nanoseconds: "
                + Math.abs(startingTime - endedTime));
    
            // TreeSet performance Test inserting
            // and deletion 1000 elements
            TreeSet<Integer> deletionTS = new TreeSet<>();
    
            for (int i = 0; i < 1000; i++) {
                deletionTS.add(i);
            }
    
            startingTime = System.nanoTime();
            for (int i = 0; i < 1000; i++) {
                deletionTS.remove(i);
            }
    
            endedTime = System.nanoTime();
            System.out.println(
                "Total time to Deletion 1000"
                + " elements in TreeSet in nanoseconds: "
                + Math.abs(startingTime - endedTime));
        }
    
        public static void main(String args[])
        {
    
            insertionOrder();
            insertionTime();
            deletion();
        }
    }
    /*
    Output
    Insertion Order of objects in HashSet :[Geek3, Geek2, Geek1]
    Insertion Order of objects in LinkedHashSet :[Geek2, Geek1, Geek3]
    Insertion Order of objects in TreeSet :[Geek1, Geek2, Geek3]
    Total time to insert 1000 elements in HashSet in nanoseconds: 791869
    Total time to insert 1000 elements in LinkedHashSet nanoseconds: 882417
    Total time to insert 1000 elements in TreeSet in nanoseconds: 11797657
    Total time to Deletion 1000 elements in HashSet in nanoseconds: 834509
    Total time to Deletion 1000 elements in LinkedHashSet in nanoseconds: 898922
    Total time to Deletion 1000 elements in TreeSet in nanoseconds: 7437577
    */
    ````

    - Similarities Between HashSet, LinkedHashSet, and TreeSet:

    - **Duplicates:** HashSet, LinkedHashSet and TreeSet are implements Set interface, so they are not allowed to store duplicates objects.
    
    - **Thread-safe:** If we want to use HashSet, LinkedHashSet, and TreeSet in a multi-threading environment then first we make it externally synchronized because both LinkedHashSet and TreeSet are not thread-safe. 
    
    - All three are Cloneable and Serializable.
    When to use HashSet, TreeSet, and LinkedHashSet in Java: 

    - **HashSet:** If you don’t want to maintain insertion order but want to store unique objects. 
    - **LinkedHashSet:** If you want to maintain the insertion order of elements then you can use LinkedHashSet. 
    - **TreeSet:** If you want to sort the elements according to some Comparator then use TreeSet.



#### Map Interface
- A map contains values on the basis of key, i.e. key and value pair. Each key and value pair is known as an entry. A Map contains unique keys. A Map is useful if you have to search, update or delete elements on the basis of a key.

- A Map doesn't allow duplicate keys, but you can have duplicate values. HashMap and LinkedHashMap allow null keys and values, but TreeMap doesn't allow any null key or value.

- A Map can't be traversed, so you need to convert it into Set using keySet() or entrySet() method.

|Class|	Description|
|-----|------------|
|HashMap|	HashMap is the implementation of Map, but it doesn't maintain any order.|
|LinkedHashMap|	LinkedHashMap is the implementation of Map. It inherits HashMap class. It maintains insertion order.|
|TreeMap|	TreeMap is the implementation of Map and SortedMap. It maintains ascending order.|


#### Map.Entry Interface

- Entry is the subinterface of Map. So we will be accessed it by Map.Entry name. It returns a collection-view of the map, whose elements are of this class. It provides methods to get key and value.

#### HashMap
- **HashMap** is similar to the HashTable, but it is unsynchronized. **It allows to store the null keys as well, but there should be only one null key object and there can be any number of null values.**  This class makes no guarantees as to the order of the map. To use this class and its methods, you need to import java.util.HashMap package or its superclass.

    ````java
    // Java program to illustrate
    // Java.util.HashMap
    
    import java.util.HashMap;
    
    public class GFG {
        
        public static void main(String[] args)
        {
            // Create an empty hash map
            HashMap<String, Integer> map = new HashMap<>();
    
            // Add elements to the map
            map.put("vishal", 10);
            map.put("sachin", 30);
            map.put("vaibhav", 20);
    
            // Print size and content
            System.out.println("Size of map is:- "
                            + map.size());
            System.out.println(map);
    
            // Check if a key is present and if
            // present, print value
            if (map.containsKey("vishal")) {
                Integer a = map.get("vishal");
                System.out.println("value for key"
                                + " \"vishal\" is:- " + a);
            }
        }
    }
    Output
    Size of map is:- 3
    {vaibhav=20, vishal=10, sachin=30}
    value for key "vishal" is:- 10
    ````


#### LinkedMap

- The **LinkedHashMap** is just like HashMap with an additional feature of maintaining an order of elements inserted into it. HashMap provided the advantage of quick insertion, search, and deletion but it never maintained the track and **order of insertion which the LinkedHashMap provides** where the elements can be accessed in their insertion order. 

- Important Features of a LinkedHashMap:

    - A LinkedHashMap contains values based on the key. It implements the Map interface and extends the HashMap class.
    - It contains only unique elements.
    - It may have one null key and multiple null values.
    - It is non-synchronized.
    - It is the same as HashMap with an additional feature that it maintains insertion order. For example, when we run the code with a HashMap, we get a different order of elements.

    ````java
    // Java program to demonstrate working of LinkedHashMap
    
    import java.util.*;
    
    public class LinkedHashMapExample {
        
        public static void main(String a[])
        {
            // create an instance of LinkedHashMap
            LinkedHashMap<String, String> lhm
                = new LinkedHashMap<String, String>();
    
            // Add mappings using put method
            lhm.put("one", "practice.geeksforgeeks.org");
            lhm.put("two", "code.geeksforgeeks.org");
            lhm.put("four", "quiz.geeksforgeeks.org");
    
            // It prints the elements in same order
            // as they were inserted
            System.out.println(lhm);
    
            System.out.println("Getting value for key 'one': "
                            + lhm.get("one"));
    
            System.out.println("Size of the map: "
                            + lhm.size());
    
            System.out.println("Is map empty? "
                            + lhm.isEmpty());
    
            System.out.println("Contains key 'two'? "
                            + lhm.containsKey("two"));
    
            System.out.println(
                "Contains value 'practice.geeks"
                + "forgeeks.org'? "
                + lhm.containsValue("practice"
                                    + ".geeksforgeeks.org"));
    
            System.out.println("delete element 'one': "
                            + lhm.remove("one"));
    
            // print mappings to the console
            System.out.println("Mappings of LinkedHashMap : "
                            + lhm);
        }
    }
    /*
    Output
    {one=practice.geeksforgeeks.org, two=code.geeksforgeeks.org, four=quiz.geeksforgeeks.org}
    Getting value for key 'one': practice.geeksforgeeks.org
    Size of the map: 3
    Is map empty? false
    Contains key 'two'? true
    Contains value 'practice.geeksforgeeks.org'? true
    delete element 'one': practice.geeksforgeeks.org
    Mappings of LinkedHashMap : {two=code.geeksforgeeks.org, four=quiz.geeksforgeeks.org}
    */
    ````


#### TreeMap
- The **TreeMap** in Java is used to **implement Map interface and NavigableMap along with the AbstractMap Class. The map is sorted according to the natural ordering of its keys, or by a Comparator provided at map creation time, depending on which constructor is used.** This proves to be an efficient way of sorting and storing the key-value pairs. The storing order maintained by the treemap must be consistent with equals just like any other sorted map, irrespective of the explicit comparators. The treemap implementation is not synchronized in the sense that if a map is accessed by multiple threads, concurrently and at least one of the threads modifies the map structurally, it must be synchronized externally.


    ````java
    // Java code to show creation, insertion,
    // searching, and traversal in a TreeMap
    
    import java.util.*;
    import java.util.concurrent.*;
    
    public class TreeMapImplementation {
    
        // Declaring a TreeMap
        static TreeMap<Integer, String> tree_map;
    
        // Function to create TreeMap
        static void create()
        {
            // Creating an empty TreeMap
            tree_map
                = new TreeMap<Integer, String>();
    
            System.out.println(
                "TreeMap successfully"
                + " created");
        }
    
        // Function to Insert values in
        // the TreeMap
        static void insert()
        {
            // Mapping string values to int keys
            tree_map.put(10, "Geeks");
            tree_map.put(15, "4");
            tree_map.put(20, "Geeks");
            tree_map.put(25, "Welcomes");
            tree_map.put(30, "You");
    
            System.out.println(
                "\nElements successfully"
                + " inserted in the TreeMap");
        }
    
        // Function to search a key in TreeMap
        static void search(int key)
        {
    
            // Checking for the key
            System.out.println(
                "\nIs key \""
                + key + "\" present? "
                + tree_map.containsKey(key));
        }
    
        // Function to search a value in TreeMap
        static void search(String value)
        {
    
            // Checking for the value
            System.out.println(
                "\nIs value \""
                + value + "\" present? "
                + tree_map.containsValue(value));
        }
    
        // Function to display the elements in TreeMap
        static void display()
        {
            // Displaying the TreeMap
            System.out.println(
                "\nDisplaying the TreeMap:");
    
            System.out.println(
                "TreeMap: " + tree_map);
        }
    
        // Function to traverse TreeMap
        static void traverse()
        {
            System.out.println("\nTraversing the TreeMap:");
            for (Map.Entry<Integer, String> e : tree_map.entrySet())
                System.out.println(e.getKey()
                                + " "
                                + e.getValue());
        }
    
        // Driver code
        public static void main(String[] args)
        {
    
            // Creating the TreeMap
            create();
    
            // Inserting values in the TreeMap
            insert();
    
            // Search key "50" in the TreeMap
            search(50);
    
            // Search value "Geeks" in the TreeMap
            search("Geeks");
    
            // Display the elements in TreeMap
            display();
    
            // Traverse the TreeMap
            traverse();
        }
    }
    /*
    Output:
    TreeMap successfully created
    Elements successfully inserted in the TreeMap
    Is key "50" present? false
    Is value "Geeks" present? true
    Displaying the TreeMap:
    TreeMap: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
    Traversing the TreeMap:
    10 Geeks
    15 4
    20 Geeks
    25 Welcomes
    30 You
    */
    ````

#### hashmap vs linkedhashmap vs treemap

|Property|	HashMap|	TreeMap|	LinkedHashMap|
|--------|---------|-----------|-----------------|
|Iteration Order|	no guaranteed order, will remain constant over time|	sorted according to the natural ordering|	insertion-order|
|Get / put / remove / containsKey|	O(1)|	O(log(n))|	O(1)|
|Interfaces|	Map|	NavigableMap, Map, SortedMap|	Map|
|Null values/keys|	allowed|	only values|	allowed|
|Fail-fast behavior|	Fail-fast behavior of an iterator cannot be guaranteed, impossible to make any hard guarantees in the presence of unsynchronized concurrent modification	|Fail-fast behavior of an iterator cannot be guaranteed, impossible to make any hard guarantees in the presence of unsynchronized concurrent modification	|Fail-fast behavior of an iterator cannot be guaranteed, impossible to make any hard guarantees in the presence of unsynchronized concurrent modification|
|Implementation|	buckets|	Red-Black Tree|	double-linked buckets|
|Is synchronized|	implementation is not synchronized|	implementation is not synchronized|	implementation is not synchronized|




