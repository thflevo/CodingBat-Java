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
