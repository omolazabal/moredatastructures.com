
!!! note
    If you have not configured you repository yet, please refer to [this guide](https://moredatastructures.com/set-up/). You have to set it up in order to test your solutions.

## Retrieving The New Problem Set

Please run

```
./update
```

To ensure you have the latest problem set. You should be able to see `3-singly-linked-list` and `4-std-list` in your repository.

## Singly Linked List

### The Code

This week's exercise will focus on lists. Specifically, you will be implementing singly linked list functions within `3-singly-linked-list`.

The `3-singly-linked-list` codebase consists of a partially complete singly linked list class. You will be filling in the empty functions in `include/singly_linked_list.h` in order complete this exercise.

!!! warning
    In your repository, please only modify the highlighted regions in `include/singly_linked_list.h` indicated below


``` C++ tab="include/singly_linked_list.h" hl_lines="44 45 46 55 56 57 66 67 68 77 78 79"

#ifndef SINGLY_LINKED_LIST_H
#define SINGLY_LINKED_LIST_H

#include <stdexcept>
using namespace std;

template <typename T>
struct Node {
    T data;
    Node<T> *next;
    Node() = delete;  // No default constructor
    Node(const T &element) : data(element), next( nullptr ) {}
};

template <typename T>
class SinglyLinkedList {
private:
    Node<T>* head;
    Node<T>* tail;

public:
    SinglyLinkedList();
    ~SinglyLinkedList();

    bool empty();
    void prepend(const T&);
    void append(const T&);
    void pop_front();

    T& front();
    T& back();

    void clear();
    size_t size();
    T& at(size_t);
    void swap_head_tail();
};

template <typename T>
void SinglyLinkedList<T>::clear() {
    // Delete every node in the linked list.
    // Utilize stdexcept to handle edge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return;


    // ====================================================
}

template <typename T>
size_t SinglyLinkedList<T>::size() {
    // Return the number of nodes in the linked list.
    // Utilize stdexcept to handle edge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return 0;


    // ====================================================
}

template <typename T>
T& SinglyLinkedList<T>::at(size_t i) {
    // Return the data stored in the ith node
    // Utilize stdexcept to handle edge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return front();


    // ====================================================
}

template <typename T>
void SinglyLinkedList<T>::swap_head_tail() {
    // Swap the head and tail nodes in the linked list.
    // Utilize stdexcept to handle edge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return;


    // ====================================================
}


template <typename T>
SinglyLinkedList<T>::SinglyLinkedList() : head(nullptr), tail(nullptr) {}

template <typename T>
SinglyLinkedList<T>::~SinglyLinkedList() {
    clear();
}

template <typename T>
bool SinglyLinkedList<T>::empty() {
    return head == nullptr;
}

template <typename T>
void SinglyLinkedList<T>::append(const T& newData) {
    Node<T> *newNode = new Node<T>(newData);   // create new node
    if (head == nullptr) {  // List empty
        head = newNode;
        tail = newNode;
    }
    else{
        tail->next = newNode;
        tail = newNode;
    }
}

template <typename T>
void SinglyLinkedList<T>::prepend(const T& newData) {
    Node<T> *newNode = new Node<T>(newData);   // create new node
    if (head == nullptr) {  // list empty
        head = newNode;
        tail = newNode;
    }
    else {
        newNode->next = head;
        head = newNode;
    }
}

template <typename T>
void SinglyLinkedList<T>::pop_front() {
    if (empty())
        throw length_error("empty list");
    Node<T> *temp = head;
    head = head->next;
    delete temp;
    if (head == nullptr)
        tail = nullptr;
}

template <typename T>
T& SinglyLinkedList<T>::front() {
    if(empty())
        throw std::length_error( "empty list" );
    return head->data;
}

template <typename T>
T& SinglyLinkedList<T>::back() {
    if(empty())
        throw std::length_error( "empty list" );
    return tail->data;
}

#endif
```

### Testing

After you have modified your code, test it! You can test it by running

```
./run 3-singly-linked-list
```

At the root of your repository.


If you've successfully implemented all of the functions, your output should look like this:
```
❯ ./run 3-singly-linked-list

==============================================================================================

                             COMPILING 3-singly-linked-list TESTS

ar: creating archive libgtest.a
a - gtest-all.o
ar: creating archive libgtest_main.a
a - gtest-all.o
a - gtest_main.o

==============================================================================================

                              RUNNING 3-singly-linked-list TESTS

unit_test_3
Running main() from /Users/oscar/Documents/projects/si-spring-2019/googletest/src/gtest_main.cc
[==========] Running 4 tests from 1 test case.
[----------] Global test environment set-up.
[----------] 4 tests from Singly_Linked_List
[ RUN      ] Singly_Linked_List.Clear
[       OK ] Singly_Linked_List.Clear (0 ms)
[ RUN      ] Singly_Linked_List.Size
[       OK ] Singly_Linked_List.Size (0 ms)
[ RUN      ] Singly_Linked_List.At
[       OK ] Singly_Linked_List.At (0 ms)
[ RUN      ] Singly_Linked_List.Swap_Head_And_Tail_Nodes
[       OK ] Singly_Linked_List.Swap_Head_And_Tail_Nodes (0 ms)
[----------] 4 tests from Singly_Linked_List (0 ms total)

[----------] Global test environment tear-down
[==========] 4 tests from 1 test case ran. (0 ms total)
[  PASSED  ] 4 tests.

==============================================================================================

                               CLEANING 3-singly-linked-list UP

==============================================================================================
```


## STD List

### The Code

In addition to the singly linked list implementation, we will also be leveraging the STL's implementation of a singly linked list. It is called a forward list. You will be performing operations on a forward list.

The `4-std-list` codebase consists of a incomplete functions that manipulate the forward list `main_list`. You will be filling in the empty functions in `include/lists.h` in order complete this exercise.

!!! warning
    In your repository, please only modify the highlighted regions in `include/lists.h` indicated below


``` C++ tab="include/lists.h" hl_lines="33 34 35 47 48 49 60 61 62 70 71 72 81 82 83 91 92 93 106 107 108 117 118 119 127 128 129"
#ifndef LISTS
#define LISTS

#include <list>
#include <algorithm>
using namespace std;

template <typename T> 
class ListQuestions {
private:
   list<T> main_list;
public:
   ListQuestions(list<T>);
   list<T>& get_list();

   void push_front_elements();
   void pop_front_elements();
   void delete_element();
   typename list<T>::iterator get_element(const T &);
   T sum();
   void swap_elements();
   void insert_elements(const T &);
   void sort();
   void clear_elements();
};

// For the following tasks manipulate main_list.

template <typename T>
void ListQuestions<T>::push_front_elements() {
    // Insert 3 elements at the front of the list
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return;


    // ====================================================
}

template <typename T>
void ListQuestions<T>::delete_element() {
    // Delete the third element from the front of the list
    // Example:
    // BEFORE: [ 1  2  4  6  1  4  . . . ]
    //                 ^
    // AFTER:  [ 1  2  6  1  4  . . . ]
    typename list<T>::iterator it = main_list.begin();
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return;


    // ====================================================
}

template <typename T>
typename list<T>::iterator ListQuestions<T>::get_element(const T &elem) {
    // Retreive an element from the list. Retrieve the element using an iterator.
    // Hint: utilize std::algorithm
    typename list<T>::iterator it = main_list.begin();
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return it;


    // ====================================================
}

template <typename T>
void ListQuestions<T>::pop_front_elements() {
    // Remove 3 elements at the front of the list
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return;


    // ====================================================
}

template <typename T>
T ListQuestions<T>::sum() {
    // Find the sum of all of the elements of the list. Utilize iterators.
    typename list<T>::iterator it = main_list.begin();
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return *it;


    // ====================================================
}

template <typename T>
void ListQuestions<T>::swap_elements() {
    // Swap the first and the last element in the list. Utilize iterators.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return;


    // ====================================================
}

template <typename T>
void ListQuestions<T>::insert_elements(const T &elem) {
    // Insert an element at the 3rd position in the list.
    // Example:
    // BEFORE: [ 1  2  4  6  1  4  . . . ]
    //                 ^
    // AFTER:  [ 1  2  n  4  6  1  4  . . . ]
    typename list<T>::iterator it = main_list.begin();
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return;


    // ====================================================
}

template <typename T>
void ListQuestions<T>::sort() {
    // Sort the elements in the list in ascending order.
    // Hint: Use std::algorithm
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return;


    // ====================================================
}

template <typename T>
void ListQuestions<T>::clear_elements() {
    // Remove every element from the list.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return;


    // ====================================================
}


template <typename T>
ListQuestions<T>::ListQuestions(list<T> copy_list) {
    for (T i : copy_list)
        main_list.push_back(i);
}

template <typename T>
list<T>& ListQuestions<T>::get_list() {
    return main_list;
}

#endif
```

### Testing

After you have modified your code, test it! You can test it by running

```
./run 4-std-list
```

At the root of your repository.


If you've successfully implemented all of the functions, your output should look like this:
```
❯ ./run 4-std-list

============================================================================================

                                 COMPILING 4-std-list TESTS

ar: creating archive libgtest.a
a - gtest-all.o
ar: creating archive libgtest_main.a
a - gtest-all.o
a - gtest_main.o

============================================================================================

                                  RUNNING 4-std-list TESTS

unit_test_4
Running main() from /Users/oscar/Documents/projects/si-spring-2019/googletest/src/gtest_main.cc
[==========] Running 9 tests from 1 test case.
[----------] Global test environment set-up.
[----------] 9 tests from
[ RUN      ] .Push_Front
[       OK ] .Push_Front (0 ms)
[ RUN      ] .Delete_Element
[       OK ] .Delete_Element (0 ms)
[ RUN      ] .Get_Element
[       OK ] .Get_Element (0 ms)
[ RUN      ] .Pop_Front
[       OK ] .Pop_Front (0 ms)
[ RUN      ] .Sum
[       OK ] .Sum (0 ms)
[ RUN      ] .Swap
[       OK ] .Swap (0 ms)
[ RUN      ] .Insert_Elements
[       OK ] .Insert_Elements (0 ms)
[ RUN      ] .Sort
[       OK ] .Sort (0 ms)
[ RUN      ] .Clear
[       OK ] .Clear (0 ms)
[----------] 9 tests from  (0 ms total)

[----------] Global test environment tear-down
[==========] 9 tests from 1 test case ran. (1 ms total)
[  PASSED  ] 9 tests.

============================================================================================

                                   CLEANING 4-std-list UP

============================================================================================
```

