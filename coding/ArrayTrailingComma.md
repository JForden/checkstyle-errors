## ArrayTrailingComma

### Description:

Checks that array initialization contains a trailing comma, From the [Java Specification:](https://docs.oracle.com/javase/specs/jls/se7/html/jls-10.html#jls-10.6)




### :x: Problematic code:

```java
int[] a = new int[]
{
  1,
  2,
  3
};
```

### :heavy_check_mark: Correct code:

```java
int[] a = new int[]
{
  1,
  2,
  3,
};
    
```

### Rationale:

Putting this comma in makes it easier to change the order of the elements or add new elements on the end. Main benefit of a trailing comma is that when you add new entry to an array, no surrounding lines are changed.

###Resources  
https://checkstyle.sourceforge.io/config_coding.html#ArrayTrailingComma  
https://docs.oracle.com/javase/specs/jls/se7/html/jls-10.html#jls-10.6


