


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
