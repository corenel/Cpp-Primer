# Exercise 2.3
> What output will the following code produce?
```
unsigned u = 10, u2 = 42;
std::cout << u2 - u << std::endl;
std::cout << u - u2 << std::endl;
int i = 10, i2 = 42;
std::cout << i2 - i << std::endl;
std::cout << i - i2 << std::endl;
std::cout << i - u << std::endl;
std::cout << u - i << std::endl;
```

Output is shown below:
```
32
4294967264
32
-32
0
0
```

# Exercise 2.5
> Determine the type of each of the following literals. Explain the differences among the literals in each of the four examples:
```
* (a) 'a', L'a', "a", L"a"
* (b) 10, 10u, 10L, 10uL, 012, 0xC
* (c) 3.14, 3.14f, 3.14L
* (d) 10, 10u, 10., 10e-2
```

* (a): character literal, wide character literal, string literal, string wide character literal.
* (b): decimal, unsigned decimal, long decimal, unsigned long decimal, octal, hexadecimal.
* (c): double, float, long double.
* (d): decimal, unsigned decimal, double, double.

# Exercise 2.6
> What, if any, are the differences between the following definitions:
```
int month = 9, day = 7;
int month = 09, day = 07;
```

In the first line, `month` and `day` are decimal.

In the second line, `month` is invalid because there's no '9' in octal. And `day` is octal.

# Exercise 2.7
> What values do these literals represent? What type does each have?
```
* (a) "Who goes with F\145rgus?\012"
* (b) 3.14e1L
* (c) 1024f
* (d) 3.14L
```

* (a) is `string`, which represents **"Who goes with Fergus?" and a new line**.
* (b) is of `long double` type, which represents **31.4**.
* (c) is of `float` type, which represents **1024.**.
* (d) is of `long double` type, which represents **3.14**

# Exercise 2.9
>Explain the following definitions. For those that are illegal,
explain what’s wrong and how to correct it.
- (a) std::cin >> int input_value;
- (b) int i = { 3.14  };
- (c) double salary = wage = 9999.99;
- (d) int i = 3.14;

(a)
    ```cpp
     int input_value;
     std::cin >> input_value;
    ```

(b): In C++11, you'll get an error "Warning: implict conversion from 'double' into 'int' changes value from '3.14' to '3'".
     ```cpp
     double i{3.14};
     ```

(c): If you declared "wage" before=, that's right. If not, you'll get an error saying "Use of undeclared idedntifier 'wage'".
     ```cpp
      double wage;
      duoble salary = wage = 9999.99;
     ```

(d): That's right, but you'll get a truncated value of "i".

# Exercise 2.10
>What are the initial values, if any, of each of the following variables?
```cpp
std::string global_str;
int global_int;
int main()
{
    int local_int;
    std::string local_str;

}
```

* `global_str` is a global string, so its value is an empty string;
* `global_int` is a global int, so its value is 0;
* `local_int` is a local int, so its value is undefined;
* `local_string` is a local string, but the string class define its initial value as an empty string.

# Exercise 2.11
> Explain whether each of the following is a declaration or a
definition:
- (a) extern int ix = 1024;
- (b) int iy;
- (c) extern int iz;

* (a): definition.
* (b): definition.
* (c): declaration.

# Exercise 2.12
>Which, if any, of the following names are invalid?
- (a) int double = 3.14;
- (b) int _;
- (c) int catch-22;
- (d) int 1_or_2 = 1;
- (e) double Double = 3.14;

(a), (c) and (d) are invalid.

# Exercise 2.13
>What is the value of j in the following program?
```cpp
int i = 42;
int main()
{
     int i = 100;
    int j = i;

}
```

j = 100

# Exercise 2.14
>Is the following program legal? If so, what values are printed?
```cpp
    int i = 100, sum = 0;
    for (int i = 0; i != 10; ++i)
        sum += i;
    std::cout << i << " " << sum << std::endl;
```

100 45

# Exercise 2.15
>Which of the following definitions, if any, are invalid? Why?
- (a) int ival = 1.01;
- (b) int &rval1 = 1.01;
- (c) int &rval2 = ival;
- (d) int &rval3;

* (b): `1.01` is not an object, so it can't be referenced.
* (d): 'rval3' must be initialized.

# Exercise 2,16
>Which, if any, of the following assignments are invalid? If they are valid, explain what they do.

    int i = 0, &r1 = i; double d = 0, &r2 = d;
- (a) r2 = 3.14159;
- (b) r2 = r1;
- (c) i = r2;
- (d) r1 = d;

* (a) is valid. let d equals 3.14159
* (b) is valid. let d equals i;
* (c) is valid. let i equals d, but value will be truncated;
* (d) is valid. let i equals d, but value wiil be truncated.

# Exercise 2.17
>What does the following code print?
```cpp
int i, &ri = i;
i = 5; ri = 10;
std::cout << i << " " << ri << std::endl;
```

10 10


# Exercise 2.18
>Write code to change the value of a pointer. Write code to
change the value to which the pointer points.

```cpp
 int v1 = 0, v2 = 1;
 int *p1 = &v1, *p2 = &v2;

 p1 = p2;
 *p1 = v1;
```

# Exercise 2.19
>Explain the key differences between pointers and references.

see in book.

# Exercise 2.20
>What does the following program do?
```cpp
int i = 42;
int *p1 = &i; *p1 = *p1 * *p1;
```

1. Let p1 points to i;
2. Let i = i * i;

# Exercise 2.21
>Explain each of the following definitions. Indicate whether any are illegal and, if so, why.

    int i = 0;

- (a) double* dp = &i;
- (b) int *ip = i;
- (c) int *p = &i;

* (a): Illegal. A double pointer can't point to an int object.
* (b): Illegal. The value of a pointe must be the address of an object.
* (c): Legal.

# Exercise 2.22
Assuming p is a pointer to int, explain the following code:

```cpp
if (p) // ...
if (*p) // ...
```
1. Whether p is a nullptr?
2. Whether the int value that p points is zero?


# Exercise 2.23
>Given a pointer p, can you determine whether p points to a valid object? If so, how? If not, why not?

No, we can't. Because no more information needed to determine if the point is valid.


##Exercise 2.24
>Why is the initialization of p legal but that of lp illegal?

```cpp
int i = 42;
void *p = &i;
long *lp = &i;
```

`void*` is a special type that can point to any objects, so 'p' can point to 'i'.

But 'lp' is of 'long*' type, hence it can;t point to an int object.
