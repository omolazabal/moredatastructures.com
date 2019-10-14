
!!! note
    If you have not configured you repository yet, please refer to [this guide](https://moredatastructures.com/set-up/). You have to set it up in order to test your solutions.

## Retrieving The New Problem Set

Please run

```
./update
```

To ensure you have the latest problem set. You should be able to see `5-stack`.

## The Code

This week's exercise will focus on lists. Specifically, you will be implementing stack operations within `5-stack`.

The `5-stack` codebase consists of a series of function that manipulate a stack that is passed in.

!!! warning
    In your repository, please only modify the highlighted regions in `include/stack.h` indicated below


``` C++ tab="include/stack.h" hl_lines="15 16 17 25 26 27 35 36 37 45 46 47"
#ifndef STACKS
#define STACKS

#include <stack>
#include <algorithm>
using namespace std;


// For the following tasks manipulate the passed in stack.

template <typename T>
void push_elements(stack<T> &s, T arr[], size_t size) {
    // Insert the values from the array into the stack
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}

template <typename T>
T sum(stack<T> &s) {
    // Sum up all of the elements in the stack
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return 0;


    // ====================================================
}

template <typename T>
void clear(stack<T> &s) {
    // Remove all elements from the stack
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}

template <typename T>
void reverse(stack<T> &s) {
    // Reverse the elements of the stack
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}

#endif

```

## Testing

After you have modified your code, test it! You can test it by running

```
./run 5-stack
```

At the root of your repository.


If you've successfully implemented all of the functions, your output should look like this:
```
❯ ./run 5-stack

============================================================================================

                                  COMPILING 5-stack TESTS

ar: creating archive libgtest.a
a - gtest-all.o
ar: creating archive libgtest_main.a
a - gtest-all.o
a - gtest_main.o

============================================================================================

                                   RUNNING 5-stack TESTS

unit_test_5
Running main() from /Users/oscar/Documents/projects/si-spring-2019/googletest/src/gtest_main.cc
[==========] Running 4 tests from 1 test case.
[----------] Global test environment set-up.
[----------] 4 tests from
[ RUN      ] .Push_Elements
[       OK ] .Push_Elements (0 ms)
[ RUN      ] .Reverse
[       OK ] .Reverse (0 ms)
[ RUN      ] .Sum
[       OK ] .Sum (0 ms)
[ RUN      ] .Clear
[       OK ] .Clear (0 ms)
[----------] 4 tests from  (1 ms total)

[----------] Global test environment tear-down
[==========] 4 tests from 1 test case ran. (1 ms total)
[  PASSED  ] 4 tests.

============================================================================================

                                    CLEANING 5-stack UP

============================================================================================

```

