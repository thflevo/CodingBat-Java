### missingChar

> Given a non-empty string and an int n, return a new string where the char at index n has been removed. The value of n will be a valid index of a char in the original string (i.e. n will be in the range 0..str.length()-1 inclusive).
> * missingChar("kitten", 1) → "ktten"
> * missingChar("kitten", 0) → "itten"
> * missingChar("kitten", 4) → "kittn"

```java
public String missingChar(String str, int n) {
  return str.substring(0, n) + str.substring(n+1);
}
```
I struggled a bit with this one - I think the biggest learning lesson was that there is no Java.string method to remove characters, and thus to remove just one character you basically just have to print all the characters before it and after it. 

The __substring()__ method also works such that you can specify a range (as can be seen above). The proposed solution split it up into two sections, and returned a "front" and a "back", but the inherent logic in the solutions is still the same. Something that the proposed solution does however is this

```java
String back = str.substring(n+1, str.length());
```
and the reason why they do this is to ensure that the substring stops printing at the end of the string (i.e the specified range) but I'm not sure what happens if you don't specify the end like I've done. Perhaps it may print hidden whitespaces? 
