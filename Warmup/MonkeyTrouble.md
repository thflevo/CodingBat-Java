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
