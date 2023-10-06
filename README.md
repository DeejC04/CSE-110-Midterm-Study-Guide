# CSE 110 Study Guide Questions Review

In this document, I'll go over the questions asked on the [midterm study guide](https://canvas.asu.edu/courses/161479/pages/midterm-exam-study-guide-and-important-info?module_item_id=11372019) that's provided on Canvas.

Some of these are very repetitive, so I may skip near-duplcicates.

I'm hoping that with this, I can further your understanding of the material and truly assist you to succeed.


All the best,  
Deej


### 1. **Trace and evaluate assignment sequences**
- What will be the output of this code?
```java
int x = 2;
int y = 10;
x = y + 1;
y = x - 1;
x = x + 1;
y = y - 1;
x = x - y;

System.out.print(x);
```

### Explanation

The two most important lines of this code are the top two. We have `int x = 2;` and `int y = 10;`. This makes the rest easy, although it's easy to make simple mistakes if you're not careful. Let's go line by line to solve this.

Before evaluating, make sure to make a small table to keep track of variable values. Currently, the values are as follows:

| Variable | Value |
| :----:   | :---: |
| x        | 2     |
| y        | 10    |

After the first two lines, we start manipulating these values. We first have `x = y + 1;`. We can substitute `y` with its current value from the table. So, `x = 10 + 1`. Once evaluated, we now know we've reassigned `x` to the sum of `10` and `1`, which is `11`.

Update the table to reflect this
| Variable | Value |
| :----:   | :---: |
| x        | 11    |
| y        | 10    |

Our next line says `y = x - 1;`. Following our substitution step, `y = 11 - 1`, which means `y = 10`. This leaves it unchanged since `11 - 1` is 10, `y`'s current value.

Following this, `x = x + 1;`. So, `x = 11 + 1`. `x = 12`.

| Variable | Value |
| :----:   | :---: |
| x        | 12    |
| y        | 10    |

Next, `y = y - 1;`. Which means `y = 10 - 1`, therefore `y = 9`.

| Variable | Value |
| :----:   | :---: |
| x        | 12    |
| y        | 9     |

Finally, we're given `x = x - y;`. We substitute both values to get `x = 12 - 9`, which evaluates to `x = 3`.

**The last line prints `x`, which we evaluated to `3`. The answer is `3`.**

### **2. Identify valid Java identifiers.**

- Which of the following are valid Java identifiers? Choose all that apply.

```
a) 1NAME  
b) a-bonus  
c) in_&_out  
d) My_vAlUe  
e) sum and difference  
f) Tax  
g) a123b  
h) name1  
i) Test Variable  
j) 00xGOLD
```

### Explanation

Let's refer to our knowledge of valid Java identifiers.

- The only valid characters are all alphanumeric characters ([`A-Z`], [`a-z`], [`0-9`]), dollar signs (`$`), and underscores (`_`).
- Identifiers cannot start with a numeric character.

So, with this knowledge, let's go over each.

**a) 1NAME**  
This is an **invalid identifier** because it starts with a numeric character.

**b) a-bonus**  
This is an **invalid identifier** because it contains a hyphen (`-`), which is not an alphanumeric character, a dollar sign, or an underscore.

**c) in_&_out**  
This is an **invalid identifier** because it contains an ampersand (`&`), which is not an alphanumeric character, a dollar sign, or an underscore.

**d) My_vAlUe**   
This is a **valid identifier**.

**e) sum and difference**  
This is an **invalid identifier** because it contains spaces, which are not an alphanumeric characters, dollar signs, or underscores.

**f) Tax**
This is a **valid identifier**.

**g) a123b**  
This is a **valid identifier**.

**h) name1**   
This is a **valid identifier**.

**i) Test Variable**  
This is an **invalid identifier** because it contains spaces, which are not an alphanumeric characters, dollar signs, or underscores.

**j) 00xGOLD**  
This is an **invalid identifier** because it starts with a numeric character.

### 3. Evaluate Java math expressions

- Given the following int (integer) variables, `a = 11, b = 37, c = 3, d = 5`, evaluate the expression:
```
a + b % c * d
```

### Explanation

First, let's recall the precedence rules in Java.

| Operator/Convention | Description |  
| :----:              | :---:       |
| `()`                | 	Items within parentheses are evaluated first   | $           |
|   unary `-`         | - used for negation (unary minus) is next        |         
| `*`, `/`, `%`,      |         Next to be evaluated are *, /, and %, having equal precedence.    |
| `+`, `-`            |           Finally come + and - with equal precedence.  |        
| `left-to-right`     |     If more than one operator of equal precedence could be evaluated, evaluation occurs left to right.        |        

With this information, we can evaluate the expression very easily! First, let's substitute our values (`a = 11, b = 37, c = 3, d = 5`)

```
11 + 37 % 3 * 5
```

Referring to our precedence rules, we can see that parentheses are first. Since we have none, we can bypass this. We also have no unary negation. 

In contrast, we do have multiplication and modulus. Remember that multiple operators of equal precedence are evaluated left to right. So, we will start at `37 % 3`.

If you recall, the modulus operator evaluates the remainder.

3 goes into 37 a total of 12 times. But, `12 * 3 = 36`. Since `37 - 36 = 1`, we can determine that `37 % 3 = 1`. There are other ways of finding the remainder, but I just explained 1.

So, now that we've evaluated `37 % 3` to `1`, we can rewrite our expression as
```
11 + 1 * 5
```

Multiplication is evaluated before addition, so we do `1 * 5`, which is just `5`.

Finally, we have `11 + 5`, which is `16.`

**The expression evaluates to `16`.**

### 4. Identify Java primitive types by name

- Which of the following are Java primitive data types? Choose all that apply.

```
a) boolean
b) double
c) String
d) Math
e) class
f) int
g) float
h) Array
i) Random
j) char
```

### Explanation

This problem is honestly more of a memorization thing, which is annoying. There are 8 primitive data types in Java, they are:
- Boolean
- Byte
- Short
- Int
- Long
- Float
- Double
- Char

So, the correct answers are a, b, f, g, j.

You may be slightly confused as to why String is not valid. That is because String is a reference/class based type. Think of it this way - based on our previous knowledge of binary, we know that each of the data types above can be represented purely as binary sequences, with no extra steps. A string though, needs a bit more tweaking. Strings are made up of chars, so, there is a class built into Java that converts an array of chars, into a single String.

### 5. Identify Java primitive types by literal value

- Which of the following Java literals have the data type float? Choose all that apply.

```
a) 5.25
b) 5.25f
c) 5.0
d) '\n'
e) 5f
f) '5'
g) false
h) "true"
i) true
j) 123
k) -5
l) "5.0"
```

### Explanation

If you recall, the only way a value can be denoted as a float is by appending `f` to the end. This is because, otherwise, Java will default any numeric floating point value to a double, or non floating point value to an integer. With this, we can identify the floats.

**b** is a float, as stated by the f at the end

**e** is also a float

Aside from those two, none are float values. They are either Strings, doubles, integers, or chars.

### 6. Identify Java primitive types by expression

IN PROGRESS

### 7. Choose the best Java data type

IN PROGRESS


### 8. Declare a variable of a specified primitive type

IN PROGRESS

### 9. Using string class methods (charAt)

IN PROGRESS

### 10. Using string class methods (compareTo)

IN PROGRESS

### 11. Using string class methods (equals)

IN PROGRESS

### 12. Using string class methods (indexOf)

IN PROGRESS

### 13. Using string class methods (length)

IN PROGRESS

### 14. Using string class methods (substring)

IN PROGRESS

### 15. Trace and evaluate code with multiple methods

IN PROGRESS

