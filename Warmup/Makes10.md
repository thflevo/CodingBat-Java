### Makes10 (Boolean)

> Given 2 ints, a and b, return true if one if them is 10 or if their sum is 10.
> * makes10(9, 10) → true 
> * makes10(9, 9) → false
> * makes10(1, 9) → true

```java
public boolean makes10(int a, int b) {
  return (a == 10 || b == 10 || a+b == 10);
}
```

Although this code and concept is rather simple, the biggest thing I learned was that __you can have multiple conditions within logical operators__, as long as you don't muck up the variable types (i.e. piping the end result of an || into an &&, which would leave a boolean with some other variable).

So something like 

```java
a == 1 || b == 1 || c == 1  // Is fine

x == (a || b) // would compare x to true or false, so unless x is also a boolean it would cause an error(?) 

```

Logically speaking, it should also be fine to have multiple && conditions (i.e. a && b && c...) but I have yet to confirm this.
