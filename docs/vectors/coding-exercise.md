!!! note
    If you have not configured you repository yet, please refer to [this guide](https://moredatastructures.com/set-up/). You have to set it up in order to test your solutions.

## Retrieving The New Problem Set

Please run

```
./update
```

To ensure you have the latest problem set. You should be able to see `2-fixed-vector` in your repository.

## The Code

This week's exercise will focus on vectors. Specifically, you will be implementing your very own fixed vector class. Fixed vectors are similar to standard vectors, except for the fact that fixed vectors do not dynamically grow/shrink.

The `2-fixed-vector` codebase consists of a partially complete fixed vector class. You will be filling in the empty functions in `include/fixed_vector.h` in order complete this exercise.

!!! warning
    In your repository, please only modify the highlighted regions in `include/fixed_vector.h` indicated below


``` C++ tab="include/fixed_vector.h" hl_lines="33 34 35 44 45 46 55 56 57 66 67 68 77 78 79"

#ifndef FIXED_VECTOR_H
#define FIXED_VECTOR_H

#include <stdexcept>
using namespace std;

template <typename T>
class FixedVector {
private:
    size_t capacity,
           size;
    T *arr;

public:
    FixedVector();
    FixedVector(size_t cap);
    FixedVector(const FixedVector &rhs);
    ~FixedVector();

    void push_back(const T &elem);
    void pop_back();
    T at(const size_t index) const;

    size_t get_capacity();
    size_t get_size();
    T &operator[] (size_t index);
};

template <typename T>
FixedVector<T>::FixedVector(const FixedVector &rhs) {
    // Implement the copy constructor.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}

template <typename T>
void FixedVector<T>::push_back(const T &elem) {
    // Insert an element at the next available index of the array.
    // Utilize stdexcept to handle edge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}

template <typename T>
void FixedVector<T>::pop_back() {
    // Remove element from the back of the vector.
    // Utilize stdexcept to handle edge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}

template <typename T>
T FixedVector<T>::at(const size_t index) const {
    // Retrieve the element at the specified index.
    // Utilize stdexcept to handle edge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return arr[0];


    // ====================================================
}

template <typename T>
T &FixedVector<T>::operator[](const size_t index) {
    // Retrieve the element at the specified index.
    // Utilize stdexcept to handle edge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return arr[0];


    // ====================================================
}

template <typename T>
FixedVector<T>::FixedVector() {
    capacity = 100;
    size = 0;
    arr = new T[capacity];
}

template <typename T>
FixedVector<T>::FixedVector(size_t cap) {
    capacity = cap;
    size = 0;
    arr = new T[capacity];
}

template <typename T>
FixedVector<T>::~FixedVector() {
    delete [] arr;
}

template <typename T>
size_t FixedVector<T>::get_capacity() {
    return capacity;
}

template <typename T>
size_t FixedVector<T>::get_size() {
    return size;
}

#endif

```

## Testing

After you have modified your code, test it! You can test it by running

```
./run 2-fixed-vector
```

At the root of your repository.


If you've successfully implemented all of the functions, your output should look like this:
```
❯ ./run 2-fixed-vector

================================================================================================================

                                         COMPILING 2-fixed-vector TESTS

ar: creating archive libgtest.a
a - gtest-all.o
ar: creating archive libgtest_main.a
a - gtest-all.o
a - gtest_main.o

================================================================================================================

                                          RUNNING 2-fixed-vector TESTS

unit_test_2
Running main() from /Users/oscar/Documents/projects/si-spring-2019/googletest/src/gtest_main.cc
[==========] Running 5 tests from 1 test case.
[----------] Global test environment set-up.
[----------] 5 tests from Fixed_Vector
[ RUN      ] Fixed_Vector.Copy_Constructor
[       OK ] Fixed_Vector.Copy_Constructor (0 ms)
[ RUN      ] Fixed_Vector.Push_Back
[       OK ] Fixed_Vector.Push_Back (0 ms)
[ RUN      ] Fixed_Vector.Pop_Back
[       OK ] Fixed_Vector.Pop_Back (0 ms)
[ RUN      ] Fixed_Vector.At
[       OK ] Fixed_Vector.At (0 ms)
[ RUN      ] Fixed_Vector.Operator_Overloading
[       OK ] Fixed_Vector.Operator_Overloading (0 ms)
[----------] 5 tests from Fixed_Vector (0 ms total)

[----------] Global test environment tear-down
[==========] 5 tests from 1 test case ran. (0 ms total)
[  PASSED  ] 5 tests.

================================================================================================================

                                           CLEANING 2-fixed-vector UP

================================================================================================================
```

