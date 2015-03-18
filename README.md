<a id="top"></a>
# Intermediate Java
 
## Table of Contents
1. [Variables](#variables)
  1. [Primitives](#primitives)
  2. [Objects](#objects)
  3. [Wrappers](#wrappers)
2. [Abstraction]
3. [Patterns]
 
-------------------------
 
<a id="variables"></a>
## 1.0 Variables

<a id="primitives"></a>
### 1.1 Primitives

Primitives are data types that are defined by the language.

In Java there are 8 primitives:

| Primitive Type  |  Bytes  |
|-----------------|---------|
| byte | 1 |
| boolean | 1 |
| char | 2 |
| short | 2 |
| int | 4 |
| float | 4 |
| double | 8 |
| long | 8 |

Let's look at some quick examples of primitive declarations:

```java
byte a = -128;
boolean b = true;
char c = 'q';
short d = 128;
int e = 32768;
float f = 9.81;
double g = 3.14159265358979;
long h = 12345678901234567890;
```

Primitives values have independent states. Changing the value of one does not influence another.

```java
int a = 5;
int b = a;
b = 7;
System.out.println("a is " + a);
System.out.println("b is " + b);
```

Gives us:

```
a is 5
b is 7
```

Now let's look at what happens when we do the same thing to objects.

<a id="objects"></a>
### 1.2 Objects

Here's a simple class declaration:

```java
public class Car
{
  public int year;
  
  public Car(int y)
  {
    year = y;
  }
}
```

What happens when we execute the following piece of code?

```java
public static void main(String[] args)
{
  Car a = new Car(1996);
  Car b = a;
  b.year = 2015;
  
  System.out.println("a's year is " + a.year);
  System.out.println("b's year is " + b.year);
}
```

We get:

```
a's year is 2015
b's year is 2015
```

Why?

The answer lies in <b>references</b>.

When we instantiate an object, we create a reference to that object in memory. A reference can be thought of as an arrow pointing to location of the object.

```java
Car a = new Car();
```

This line of code calls the default constructor of the Car class to instantiate a new reference of a Car object. `a` is <b>not</b> actually the Car object, it is a <b>reference</b> to the Car object.

So when we tell `a` to execute a method, we are actually telling whatever `a` points at to execute the method. Since multiple variables can reference the same object, it sometimes gets confusing. Let's look back at our code above:

```java
public static void main(String[] args)
{
  Car a = new Car(1996);
  Car b = a;
  b.year = 2015;
  
  System.out.println("a's year is " + a.year);
  System.out.println("b's year is " + b.year);
}
```

`a` is a reference to a Car object that has a year of 2015.
`b` is a reference to that same Car object. You don't see the keyword `new`, so you know that there are no other Car objects in play.
When we change the year of `b`, we change the year of the Car object that `a` and `b` both refer to. This is why we get:

```
a's year is 2015
b's year is 2015
```



<a id="wrappers"></a>
### 1.3 Wrappers

Java provides built-in <b>primitive wrappers</b> for all 8 primitive types.

| Primitive Type  |  Wrapper class  |
|-----------------|---------|
| byte | Byte |
| boolean | Boolean |
| char | Character |
| short | Short |
| int | Integer |
| float | Float |
| double | Double |
| long | Long |


Here we can see three different ways of integer creation:

```java
int a = 3;
Integer b = new Integer(3);
Integer c = new Integer("3");
```

And due to <b>autoboxing</b> in Java, we do not have to worry about the differences between Wrappers and primitives--they are implicitly wrapped and unboxed for us. For example:

```java
ArrayList<Integer> list = new ArrayList<Integer>();
int i = 5;
list.add(i);
```

This is perfectly valid code even though the ArrayList only holds `Integer` objects and `i` is a primitive int.
