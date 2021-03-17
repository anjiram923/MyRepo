# Interview Questions

#### OOPs (Object-Oriented Programming System)
    
- Object means a real-world entity such as a pen, chair, table, computer, watch, etc. Object-Oriented Programming is a methodology or paradigm to design a program using classes and objects. It simplifies software development and maintenance by providing some concepts:

    - Object
    - Class
    - Inheritance
    - Polymorphism
    - Abstraction
    - Encapsulation

    Apart from these concepts, there are some other terms which are used in Object-Oriented design:

    - Coupling
    - Cohesion
    - Association
    - Aggregation
    - Composition
    - Java OOPs Concepts  


- **Object**

    Java Object
    Any entity that has state and behavior is known as an object. For example, a chair, pen, table, keyboard, bike, etc. It can be physical or logical.

    An Object can be defined as an instance of a class. An object contains an address and takes up some space in memory. Objects can communicate without knowing the details of each other's data or code. The only necessary thing is the type of message accepted and the type of response returned by the objects.

    Example: A dog is an object because it has states like color, name, breed, etc. as well as behaviors like wagging the tail, barking, eating, etc.

- **Class**

    Collection of objects is called class. It is a logical entity.

    A class can also be defined as a blueprint from which you can create an individual object. Class doesn't consume any space.

- **Inheritance**

    When one object acquires all the properties and behaviors of a parent object, it is known as inheritance. It provides code reusability. It is used to achieve runtime polymorphism.

- **Polymorphism**

    If one task is performed in different ways, it is known as polymorphism. For example: to convince the customer differently, to draw something, for example, shape, triangle, rectangle, etc.

    In Java, we use method overloading and method overriding to achieve polymorphism.

    Another example can be to speak something; for example, a cat speaks meow, dog barks woof, etc.

- **Abstraction**

    Hiding internal details and showing functionality is known as abstraction. For example phone call, we don't know the internal processing.

    In Java, we use abstract class and interface to achieve abstraction.

- **Encapsulation**
    Binding (or wrapping) code and data together into a single unit are known as encapsulation. For example, a capsule, it is wrapped with different medicines.

    A java class is the example of encapsulation. Java bean is the fully encapsulated class because all the data members are private here.

- **Coupling**

    Coupling refers to the knowledge or information or dependency of another class. It arises when classes are aware of each other. If a class has the details information of another class, there is strong coupling. In Java, we use private, protected, and public modifiers to display the visibility level of a class, method, and field. You can use interfaces for the weaker coupling because there is no concrete implementation.

- **Cohesion**

    Cohesion refers to the level of a component which performs a single well-defined task. A single well-defined task is done by a highly cohesive method. The weakly cohesive method will split the task into separate parts. The java.io package is a highly cohesive package because it has I/O related classes and interface. However, the java.util package is a weakly cohesive package because it has unrelated classes and interfaces.

- **Association**

    Association represents the relationship between the objects. Here, one object can be associated with one object or many objects. There can be four types of association between the objects:

    - One to One
    - One to Many
    - Many to One, and
    - Many to Many
    
    Let's understand the relationship with real-time examples. For example, One country can have one prime minister (one to one), and a prime minister can have many ministers (one to many). Also, many MP's can have one prime minister (many to one), and many ministers can have many departments (many to many).

    Association can be undirectional or bidirectional.

- **Aggregation**

    Aggregation is a way to achieve Association. Aggregation represents the relationship where one object contains other objects as a part of its state. It represents the weak relationship between objects. It is also termed as a has-a relationship in Java. Like, inheritance represents the is-a relationship. It is another way to reuse objects.

- **Composition**

    The composition is also a way to achieve Association. The composition represents the relationship where one object contains other objects as a part of its state. There is a strong relationship between the containing object and the dependent object. It is the state where containing objects do not have an independent existence. If you delete the parent object, all the child objects will be deleted automatically.



#### Comparable vs Comparator in Java

    Java provides two interfaces to sort objects using data members of the class: 

        1. Comparable
        2. Comparator
    


- **Using Comparable Interface**

    A comparable object is capable of comparing itself with another object. The class itself must implements the java.lang.Comparable interface to compare its instances. 
    Consider a Movie class that has members like, rating, name, year. Suppose we wish to sort a list of Movies based on year of release. We can implement the Comparable interface with the Movie class, and we override the method compareTo() of Comparable interface. 

    ````java
        // A Java program to demonstrate use of Comparable
        import java.io.*;
        import java.util.*;
        
        // A class 'Movie' that implements Comparable
        class Movie implements Comparable<Movie>
        {
            private double rating;
            private String name;
            private int year;
        
            // Used to sort movies by year
            public int compareTo(Movie m)
            {
                return this.year - m.year;
            }
        
            // Constructor
            public Movie(String nm, double rt, int yr)
            {
                this.name = nm;
                this.rating = rt;
                this.year = yr;
            }
        
            // Getter methods for accessing private data
            // need to implement setters and getters
        }
        
        // Driver class
        class Main
        {
            public static void main(String[] args)
            {
                ArrayList<Movie> list = new ArrayList<Movie>();
                list.add(new Movie("Force Awakens", 8.3, 2015));
                list.add(new Movie("Star Wars", 8.7, 1977));
                list.add(new Movie("Empire Strikes Back", 8.8, 1980));
                list.add(new Movie("Return of the Jedi", 8.4, 1983));
        
                Collections.sort(list);
        
                System.out.println("Movies after sorting : ");
                for (Movie movie: list)
                {
                    System.out.println(movie.getName() + " " +
                                    movie.getRating() + " " +
                                    movie.getYear());
                }
            }
        }

        /*
            Output: 

                Movies after sorting :
                Star Wars 8.7 1977
                Empire Strikes Back 8.8 1980
                Return of the Jedi 8.4 1983
                Force Awakens 8.3 2015
        */
    ````

- **Using Comparator**

    Unlike Comparable, Comparator is external to the element type we are comparing. It’s a separate class. We create multiple separate classes (that implement Comparator) to compare by different members.
    Collections class has a second sort() method and it takes Comparator. The sort() method invokes the compare() to sort objects.
    To compare movies by Rating, we need to do 3 things : 
 

    1. Create a class that implements Comparator (and thus the compare() method that does the work previously done by compareTo()).
    2. Make an instance of the Comparator class.
    3. Call the overloaded sort() method, giving it both the list and the instance of the class that implements Comparator.

    ````java
        //A Java program to demonstrate Comparator interface
        import java.io.*;
        import java.util.*;
        
        // A class 'Movie' that implements Comparable
        class Movie implements Comparable<Movie>
        {
            private double rating;
            private String name;
            private int year;
        
            // Used to sort movies by year
            public int compareTo(Movie m)
            {
                return this.year - m.year;
            }
        
            // Constructor
            public Movie(String nm, double rt, int yr)
            {
                this.name = nm;
                this.rating = rt;
                this.year = yr;
            }
        
            // Getter methods for accessing private data
        }
        
        // Class to compare Movies by ratings
        class RatingCompare implements Comparator<Movie>
        {
            public int compare(Movie m1, Movie m2)
            {
                if (m1.getRating() < m2.getRating()) return -1;
                if (m1.getRating() > m2.getRating()) return 1;
                else return 0;
            }
        }
        
        // Class to compare Movies by name
        class NameCompare implements Comparator<Movie>
        {
            public int compare(Movie m1, Movie m2)
            {
                return m1.getName().compareTo(m2.getName());
            }
        }
        
        // Driver class
        class Main
        {
            public static void main(String[] args)
            {
                ArrayList<Movie> list = new ArrayList<Movie>();
                list.add(new Movie("Force Awakens", 8.3, 2015));
                list.add(new Movie("Star Wars", 8.7, 1977));
                list.add(new Movie("Empire Strikes Back", 8.8, 1980));
                list.add(new Movie("Return of the Jedi", 8.4, 1983));
        
                // Sort by rating : (1) Create an object of ratingCompare
                //                  (2) Call Collections.sort
                //                  (3) Print Sorted list
                System.out.println("Sorted by rating");
                RatingCompare ratingCompare = new RatingCompare();
                Collections.sort(list, ratingCompare);
                for (Movie movie: list)
                    System.out.println(movie.getRating() + " " +
                                    movie.getName() + " " +
                                    movie.getYear());
        
        
                // Call overloaded sort method with RatingCompare
                // (Same three steps as above)
                System.out.println("\nSorted by name");
                NameCompare nameCompare = new NameCompare();
                Collections.sort(list, nameCompare);
                for (Movie movie: list)
                    System.out.println(movie.getName() + " " +
                                    movie.getRating() + " " +
                                    movie.getYear());
        
                // Uses Comparable to sort by year
                System.out.println("\nSorted by year");
                Collections.sort(list);
                for (Movie movie: list)
                    System.out.println(movie.getYear() + " " +
                                    movie.getRating() + " " +
                                    movie.getName()+" ");
            }
        }  
        /*
        Output : 

            Sorted by rating
            8.3 Force Awakens 2015
            8.4 Return of the Jedi 1983
            8.7 Star Wars 1977
            8.8 Empire Strikes Back 1980

            Sorted by name
            Empire Strikes Back 8.8 1980
            Force Awakens 8.3 2015
            Return of the Jedi 8.4 1983
            Star Wars 8.7 1977

            Sorted by year
            1977 8.7 Star Wars 
            1980 8.8 Empire Strikes Back 
            1983 8.4 Return of the Jedi 
            2015 8.3 Force Awakens
        */
    ````


- **Here are the main differences between Java Comparable vs Comparator:**

    |Comparable|Comparator|
    |----------|----------|
    |Comparable provides compareTo() method to sort elements in Java.	|Comparator provides compare() method to sort elements in Java.|
    |Comparable interface is present in java.lang package.|	Comparator interface is present in java.util package.|
    |The logic of sorting must be in the same class whose object you are going to sort.	|The logic of sorting should be in separate class to write different sorting based on different attributes of objects.|
    |The class whose objects you want to sort must implement comparable interface.	|Class, whose objects you want to sort, do not need to implement a comparator interface.|
    |It provides single sorting sequences.	|It provides multiple sorting sequences.|
    |This method can sort the data according to the natural sorting order.|	This method sorts the data according to the customized sorting order.|
    |It affects the original class. i.e., actual class is altered.|	It doesn't affect the original class, i.e., actual class is not altered.|
    |Implemented frequently in the API by: Calendar, Wrapper classes, Date, and String.|	It is implemented to sort instances of third-party classes.|
    |All wrapper classes and String class implement comparable interface.|	The only implemented classes of Comparator are Collator and RuleBasedColator.|

































