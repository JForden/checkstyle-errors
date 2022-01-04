## ArrayTrailingComma

### Description:

double brace initialization.


### :x: Problematic code:

```java
public static void main(String[] args)
    {
 
        // Creating an empty HashSet
        Set<String> sets = new HashSet<String>()
 
        // Double brace
        {
            {
                // Adding elements to above HashSet
                // This is double brace initialization
                add("one");
                add("two");
                add("three");
            }
        };
 
        // ...
        // Now pass above collection as parameter to method
        // Calling method 2 inside main() method
        useInSomeMethod(sets);
    }
```A

### :heavy_check_mark: Correct code:

```java
public static void main(String[] args)
    {
 
        // Creating an empty HashSet
        Set<String> sets = new HashSet<String>()
 
        // Double brace
        {
            {
                // Adding elements to above HashSet
                // This is double brace initialization
                add("one");
                add("two");
                add("three");
            }
        };
 
        // ...
        // Now pass above collection as parameter to method
        // Calling method 2 inside main() method
        useInSomeMethod(sets);
    }
```

### Rationale:

Double brace initialization (set of Instance Initializers in class body) may look cool, but it is considered as anti-pattern and should be avoided. This is also can lead to a hard-to-detect memory leak, if the anonymous class instance is returned outside and other object(s) hold reference to it. Created anonymous class is not static, it holds an implicit reference to the outer class instance. See this blog post and article for more details. Check ignores any comments and semicolons in class body.

###Resources  
https://www.geeksforgeeks.org/double-brace-initialization-java/ 
https://checkstyle.sourceforge.io/config_coding.html#AvoidDoubleBraceInitialization


