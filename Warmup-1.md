# Warmup-1


### Monkey Trouble (Boolean) 

> We have two monkeys, a and b, and the parameters aSmile and bSmile indicate if each is smiling. We are in trouble if they are both smiling or if neither of them is smiling. Return true if we are in trouble.
> * monkeyTrouble(true, true) → true
> * monkeyTrouble(false, false) → true
> * monkeyTrouble(true, false) → false

```java
public boolean monkeyTrouble(boolean aSmile, boolean bSmile) {
  return (aSmile == bSmile);
}
```
Because the end result is always going to be either __true__ or __false__ we don't actually have to have an 'if' statement. The statement inside is a boolean, so we can simplify the code to be just one line. 

As for the logic behind the code, we are in trouble if they are *both* smiling or if *neither* of them is smiling. Thus, we can infer that when they are __equal__,  we are in trouble. They are both boolean values, thus when they are ==, we should return the value true. 

The other way to do this of course would simply to code for both cases, as there are only two options in this case. Something like ((aSmile && bSmile) || (!aSmile && !bSmile)) 


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

### Near Hundred (Boolean)

> Given an int n, return true if it is within 10 of 100 or 200. Note: Math.abs(num) computes the absolute value of a number.
> * nearHundred(93) → true
> * nearHundred(90) → true
> * nearHundred(89) → false

```java
public boolean nearHundred(int n) {
  return ((n >= 90 && n <= 110) || (n >= 190 && n <= 210));
}
```

Although the above solution works, it fails to take into account the provided hint within the problem. Namely, the 'Maths.abs(num)' function. To use this, you approach the question without using bounds, but rather finding out if the absolute difference between the number is <= 10. 

```java
return ((Maths.abs(n-100) <= 10) || (Maths.abs(n-200) <= 10));
// let n = 93, |93-100| = 7, therefore returning true.  
// let n = 89, |89=100| = 11, therefore returning false. 
// (ibid with n-200)
```

### posNeg (Boolean)

> Given 2 int values, return true if one is negative and one is positive. Except if the parameter "negative" is true, then return true only if both are negative.
> * posNeg(1, -1, false) → true
> * posNeg(-1, 1, false) → true
> * posNeg(-4, -5, true) → true

```java
public boolean posNeg(int a, int b, boolean negative) {
  if (negative) {
    return (a < 0 && b < 0);
  }
  
  else {
    return ((a < 0 && b > 0) || (a > 0 && b < 0));
  }
}
```

Trying to read this code backwards (or any long sequence of logical operators really is honestly speaking, tiresome and annoying. This problem was solved by carefully reading the parameters given, and taking into account how they would affect each other via a piece of paper. By effectively translating the words to code, you can pretty easily solve this one.

Given __2 int values__, return true if *one* is negative and *one* is positive. __Except__ if the parameter 'negative' is true, then return true __only if both are negative__.



By breaking it down, 
> __Except__ if the parameter 'negative' is true

```java
if (negative) {
//then do something
}
else {
//otherwise if negative == false, do this 
}
```
If the parameter negative is true
> return true __only if both are negative__.

If the parameter negative is false
> return true if *one* is negative and *one* is positive.

```java
if (negative) {
  return (a < 0 && b < 0);
  //returning true if BOTH are negative
}
else {
  return ((a < 0 && b > 0) || (a > 0 && b < 0));
  //returning true if ONE is negative & ONE is positive
}
```
