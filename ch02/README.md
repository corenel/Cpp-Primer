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
(a)
    ```
     int input_value;
     std::cin >> input_value;
    ```

(b): In C++11, you'll get an error "Warning: implict conversion from 'double' into 'int' changes value from '3.14' to '3'".
     ```
     double i{3.14};
     ```

(c): If you declared "wage" before=, that's right. If not, you'll get an error saying "Use of undeclared idedntifier 'wage'".
     ```
      double wage;
      duoble salary = wage = 9999.99;
     ```

(d): That's right, but you'll get a truncated value of "i".
