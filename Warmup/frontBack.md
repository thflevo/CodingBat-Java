### frontBack

> Given a string, return a new string where the first and last chars have been exchanged.
> * frontBack("code") → "eodc"
> * frontBack("a") → "a"
> * frontBack("ab") → "ba"

```java
public String frontBack(String str) {
  if (str.length() >= 2) {
    return (str.charAt(str.length() - 1) + str.substring(1, str.length() - 1) + str.charAt(0));
  }
  
  else {
    return str;
  }
}
```

In this instance, my solution could have been simplified quite heavily. I guess this is what separates the 'good' code from the 'passable' - the ability to simplify things yet also ensure that it still works. My thought process for this was initially did not take into account instances whereupon the str was less than 2 characters, as in those situations the middle part of the code would get all iffy, returning indexes of -1. This was easy enough to solve, but it just goes to show how I still can't grasp all the parameters when looking at an issue, if I just jump straight into it. I need to take a step back and to kind of work through the code in my head, before I put hand to keyboard and start writing otherwise issues like this will crop up. 

Onto the actual code though, the structure is roughly as good as it gets. You're always going to need a way to rule out all of the cases which will cause an error, but the way in which I determine which parts are the front, middle and end of the String can be simplified.

First off , instead of writing __str.length()__ over and over again, I could just have set an __int variable__ to represent it. 
```java
int len = str.length();

  if (len >= 2) {
    return (str.charAt(len - 1) + str.substring(1, len - 1) + str.charAt(0));
  }
```
It's already looking a lot better, but to improve on this even more, if you notice how the only two operands used on the length integer are of "-1", I can add this line 
```java
  if (len >= 2) {
    --len
    return (str.charAt(len) + str.substring(1, len) + str.charAt(0));
  }
```

which cleans it up even more, and ends up looking like...

```java
public String frontBack(String str) {
  int len = str.length();

  if (len >= 2) {
    --len
    return (str.charAt(len) + str.substring(1, len) + str.charAt(0));
  }
  else {
    return str;
  }
}
```

The provided solution actually structures it a little differently, and I think this is where personal preference comes into play. The solution splits it into two separate return statements, instead of an if-else structure. The initial if statement determines whether or not the string is longer than 2 chars, and if not it returns the string (like my else statement) and then the second part (my if statement) is condensed into one "return" line. 

From my personal perspective, given my relative lack of experience the way I've done it is a lot easier to follow along, and is the intuitive structure which I work from. 
