---
title: 
- Java Placement Cource (DSA) notes
author:
- Chaitanya Shahare
numbersections: true
header-includes: |
	\usepackage{float}
	\let\origfigure\figure
	\let\endorigfigure\endfigure 
	\renewenvironment{figure}[1][2] {
		\expandafter\origfigure\expandafter[H]
		} {
		\endorigfigure
		}
---

\maketitle
\tableofcontents

\newpage

> [ Lecture 1](https://youtu.be/yRpLlJmRo2w)

> 22.12.2022
> Thursday

# Introduction to Java Language

## Set of Instructions

- Flowchart
- Psudocode

## Flowchart

![Flowchart](img/2022-12-22-18-47-41.png){ width=250px }

## Psudocode

1. Start
1. Input 2 number
1. Calculate Sum = number1 + number2
1. Print Sum
1. Exit

## Java Class 1

### Installation

1. Java Development Kit (JDK)
1. Code Editor / IDE
	- VS Code
	- Intellij
	- Eclipse

### First Code

- Extension -> .java

#### Hello World

```java
class FirstClass {
	public static void main(String args[]) {
		System.out.println("Hello World");
	}
}
```

### How is code running?

![Java Development Kit (JDK)](img/2022-12-22-18-55-50.png){width=300px}

1. Compilation

![Java compilation](img/2022-12-22-18-56-17.png){width=300px}

2. Execution

![Java Execution](img/2022-12-22-18-57-16.png){width=300px}

### Code Components

#### Function

```java
void main(){

}
```

#### Class

```java
class Main{
	void main() {

	}
}
```

\newpage

> [ Lecture 2](https://www.youtube.com/watch?v=LusTv0RlnSU&list=PLfqMhTWNBTe3LtFWcvwpqTkUSlB32kJop&index=3)

> 22.12.2022
> Thursday

# Variables in Java | Input Output

## Output

```java
System.out.print("Hello World");
```

`Hello world` is the string which is printed.

- Use double quotes for strings

### Boilerplate code

```java
package com.apnacollege;

public class Main{
	public static void main(String[] args) {
		// Output
		System.out.print("Hello World");
	}
}
```

Here:
- System -> class
- print -> function

```java
System.out.println("Hello world with java");
```

- print -> for output on the same line
	```
	System.out.print("Hello World");
	```
- println -> for output on the next line
	```
	System.out.println("Hello world with java");
	```
- "\\n" ->
	```
	System.out.print("Hello World\n");
	```

### Q. Print the pattern

![right triangle pattern](img/2022-12-22-19-21-06.png){ width=150px }

```java
public class Main{
	public static void main(String[] args) {
		// Output
		System.out.println("*");
		System.out.println("**");
		System.out.println("***");
		System.out.println("****");
	}
}
```

## Variables

`Perimeter = 2 * (a + b)`

here,

- 2 -> constant
- a&b -> variable

![Variables in memory](img/2022-12-22-19-36-14.png){width=400px}

```java
public class Main{
	public static void main(String[] args) {
		// Variables
		String name = "tony stark";
		int age = 48;
		double price = 23.25;
		int a = 25;
		int b = 1;

		b = 20;
		name = "ironman";
	}
}
```

## Data Type

Java is a typed language.
i.e; you need to tell the datatype.

### Types of Datatypes

- Primitive
- Non-Primitive

Primitive               Non-Primitive
-----------------  --------------------
byte               String
short              Array
char               Class
boolean            Object
int                Interface
long
float
double

---

### Data Type sizes

Primitive               Size (in bytes)
-----------------  --------------------
byte               1
short              
char               2
boolean            1
int                4
long               8
float 			   4
double 			   8	


_Above sizes are for a 64-bit System_

---

```java
public class Main {
	public static void main(String[] argss) {
		// Variables
		int a = 10;
		int b = 25;

		int sum = a + b;
		System.out.println(sum);

		int diff = b - a;
		System.out.println(diff);

		int mul = a * b;
		System.out.println(mul);

	}
}
```

![Memory allocation for the above program](img/2022-12-22-20-18-31.png){width=400}

## Inputs in Java

```java
import java.util.*;

public class Main {
	public static void main(String[] args) {
		// Input
		Scanner sc = new Scanner(System.in);
		String name = sc.next(); // next() -> for next token ie; next word
		String name1 = sc.nextLine(); // nextLine() -> for taking a sentence as Input
		// Similarly
		// nextInt()
		// nextFloat()
		System.out.println(name);
	}
}

```

## Q. Take 2 variables 'a' & 'b' and print their sum.

```java
import java.util.*;

public class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int a = sc.nextInt();
		int b = sc.nextInt();
		int sum = a + b;
		System.out.println(sum);
	}
}
```

\newpage

> [Lecture 3](https://youtu.be/I5srDu75h_M)

> 23.12.2022
> Friday

# Conditional Statements

Topics covered

- if, else
- else if
- switch
- break

## if, else

### Syntax

```java
if (condition){

}
else {

}
```

---

Example

### Q. Write a program to identify if a person is an adult.

```java
import java.util.*;

public class Conditions {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int age = sc.nextInt();

		if (age > 18) {
			System.out.println("Adult");
		} else {
			System.out.println("Not Adult");
		}
	}
}
```

### Q. Write a program to check if a number is odd or even.

```java
import java.util.*;

public class Conditions {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int x = sc.nextInt();

		if (x % 2 == 0) {
			System.out.println("Even");
		} else {
			System.out.println("Odd");
		}
	}
}
```

## else if

### Q. Write a program to know if a is greater of lesser than b.

```java
import java.util.*;

public class Conditions {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int a = sc.nextInt();
		int b = sc.nextInt();

		if (a == b) {
			System.out.println("Equal");
		}
		else if (a > b) {
			System.out.println("a is greater than b");
		}
		else {
			System.out.println("a is lesser than b")
		}
	}
}
```

## Switch

### Syntax

```java
switch (variable) {
case 1:
	break;
case 2:
	break;
default:

}
```

### Q. Using switch write a program to greet in different languages

```java
import java.util.*;

public class Conditions {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int button = sc.nextInt();

		switch(button) {
			case 1: System.out.println("hello");
			break;
			case 2: System.out.println("namaste");
			break;
			case 3: System.out.println("bonjour");
			break;
			dafault: System.out.println("Invalid Button");
		}
	}
}

```

### Q. Make a calculator

Make a Calculator. Take 2 numbers (a & b) from the user and an operation as follows : 

- : + (Addition) a + b
- : - (Subtraction) a - b
- : * (Multiplication) a * b
- : / (Division) a / b
- : % (Modulo or remainder) a % b

Calculate the result according to the operation given and display it to the user.

```java

```

### Q. Ask the user to enter the number of the month & print the name of the month. 
For eg - For ‘1’ print ‘January’, ‘2’ print ‘February’ & so on.

```java

```

\newpage

> Lecture 4

> 23.12.2022
> Friday

# 



