
## C++ Types
1. What is a C++ type?
2. List as many C++ types as you can.
3. Are pointers and references a C++ type?

## Pointers
1. What does a pointer hold?
2. Write a line of code that declares a pointer to a double.

## References
1. What is a reference?
2. Write a line of code that initializes a reference to a float variable named `x`.

## Referencing and dereferencing
1. What does the reference operator do?
2. What does the dereference operator do?
3. Write a line of code that initializes a pointer to the address of an integer variable named `y`
4. The following program performs pointer arithmetic. In general terms, what should the following program output?
```C++
#include <iostream>

using namespace std;

int main() {
    int var = 5;
    int* ptr = &var;
    cout << var << endl;
    cout << &var << endl;
    cout << ptr << endl;
    cout << *ptr << endl;
    cout << &ptr << endl;
}
```
5. The following program performs reference arithmetic. In general terms, what should the following program output?
```C++
#include <iostream>

using namespace std;

int main() {
    int var = 5;
    int& ref = var;
    cout << var << endl;
    cout << &var << endl;
    cout << ref << endl;
    cout << &ref << endl;
}
```

## Stack
1. What is the stack used for?
2. What are the limitations of the stack?
3. Fill out the following table with respect to the program from question `4 in Referencing and Dereferencing` and question `5 in Referencinng and Dereferencing`

Question 4

| Variable name(s) | Value | Address |
| ------------- | ------------- | ---------- |
| | | |

Question 5

| Variable name(s) | Value | Address |
| ------------- | ------------- | ---------- |
| | | |

## Heap
1. What is heap used for?
2. What benefits does the heap have?
3. What are the downsides to using the heap?
4. What does it mean to dynamically allocate?
5. What data type does the `new` keyword return?
6. Why do pointers need to be used with dynamic memory?
7. Write a line of code to deallocate the memory referenced by the pointer `ptr`.
8. Fill out the stack and heap tables below with respect to following program.
```C++
#include <iostream>

using namespace std;

int main() {
    int *iptr = nullptr;
    iptr = new int(5);
    double *dptr;
    double dvar = 5.8;
    dptr = &dvar;
}

```

Stack

| Variable name(s) | Value | Address |
| ------------- | ------------- | ---------- |
| | | |
| | | |
| | | |

Heap

| Value | Address |
| ------------- | ---------- |
| | |


## Passing by Value vs Passing by Reference

![](https://csuf-acm.github.io/epp-review/img/value-reference.gif)

1. What does it mean to pass by reference?
2. What does it mean to pass by value?
3. What are the advantages of passing by reference?
4. What are the advantages of passing by value?
3. Consider the following functions:

```C++
void swap_a(int a, int b) {
    int temp = a;
    a = b;
    b = temp;
}

void swap_b(int &a, int &b) {
    int temp = a;
    a = b;
    b = temp;
} 
```
What does the following program output? Does it pass by value or by reference?

```C++
#include <iostream>

using namespace std;
int main() {
    int x(2), y(3);
    cout << x << " " << y << endl;
    swap_a(x, y);
    cout << x << " " << y << endl;
}
```

What does the following program output? Does it pass by value or by reference?
```C++
#include <iostream>

using namespace std;
int main() {
    int x(2), y(3);
    cout << x << " " << y << endl;
    swap_b(x, y);
    cout << x << " " << y << endl;
}
```

## Classes and Objects
1. What are the differences between classes and objects?
2. What are constructors and destructors?
3. What is public and private?
4. Design a class with the following details:
    - class for cars
    - private attributes: brand, lisencse plate
    - public methods: set brand, set license plate, get brand, get license plate
5. Create two objects from the class above. The first having the brand Ford and license plate number 1234567. The second having the brand name BMW and license plate 7654321.
