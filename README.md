# 10.ABX-Ifs

## 5.2 Instructions

An instruction can be viewed as a single 'order' in a given programming language, to be performed by the computer. It does not correspond to one instruction at the machine level; rather, it corresponds to a (probably very long) sequence of such basic instructions. Instructions that do not have any value are sometimes called statements, as opposed to instructions (or parts of instructions) that do have values — these are called expressions, or expression statements.

Of course, the form and syntax of instructions may be different in different languages, but usually, at least for languages of the same 'family', there are more similarities than differences (this applies in particular to languages like C, C++, Java, C#, in which the main syntactic constructs are almost identical).

Very often, when only one instruction is required by the syntax, we would like to use more; in such situations, we can use the so-called compound instruction, i.e., a set of instructions enclosed in curly braces and therefore constituting a block. Important: local variables of primitive types (numbers, characters, reference variables, etc.) defined in a block are not visible — actually, they simply don’t exist — outside of the block.

```java
{
    // block
    // ...
    int k = 7;
    // ...
}
// k does not exist here
```

### 5.2.1 Conditional statements

Conditional statements may look like this:

```java
if (cond) {
    // ...
}
```

or

```java
if (cond1) {
    // ... (code 1)
} else if (cond2) {
    // ... (code 2)
} else if (cond3) {
    // ... (code 3)
} else {
    // ... (code 4)
}
```

where `cond` are expressions whose values are of type boolean (i.e., true or false). The `else if` clauses are optional, as is the `else` clause; however, if they are used, the `else` clause must be the last. Conditions are checked in order, and for the first one that evaluates to true, the corresponding block of code will be executed (subsequent blocks will be ignored). If the `else` clause is present, the corresponding block will be executed if none of the previous conditions is true. If there is only one instruction in the block corresponding to a condition, the curly braces are not obligatory (although recommended).

In the following example, we check if a given year is a leap year or not:

### Listing 10 ABX-Ifs/LeapYear.java Page 31

```java
import java.util.Scanner;

public class LeapYear {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.print("Enter a year (integer) -> ");
        int year = scan.nextInt();
        scan.close();

        boolean is_leap;

        if (year % 400 == 0)
            is_leap = true;
        else if (year % 100 == 0)
            is_leap = false;
        else if (year % 4 == 0)
            is_leap = true;
        else
            is_leap = false;

        // ?: operator used below!
        System.out.println("Year " + year + " is " + (is_leap ? "" : "not ") + "a leap year");
    }
}
```
