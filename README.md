<a id="top"></a>
# Java Workshop
 
## Table of Contents
1. [Variables](#varibles)
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

| Primitive Name  |  Bytes  |
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

Primitives values are independent from one other. For example:

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

This is a distinction between primitives and objects.

<a id="objects"></a>
### 1.2 Objects

Here's a simple class declaration:

```java
public class Car
{
  public int year;
  public Color color;
  
  public Car(int y, Color c)
  {
    year = y;
    color = c;
  }
}
```

What happens when we execute the following piece of code?

```java
public static void main(String[] args)
{
  Car a = new Car(1997, Color.RED);
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


<a id="wrappers"></a>
### 1.3 Wrappers
