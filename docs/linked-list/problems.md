
## Why Linked Lists?
1. What are the performance limitations of vectors?
2. What are the space limitations of vectors?
3. What capabilities do linked lists provide that vectors do not?
4. What capabilities do vectors provice that linked list do not?
5. Give an example in which you would utilize a linked list over a vector? What about a vector over a linked list?

## Performance of Linked Lists
1. What would be the Big O of inserting a single node into a linked list?
2. What is the Big O of remove a single node frome a linked list?
3. What is the space complexity of storing nodes in a linked list?
4. What is the time complexity of a linear search of a linked list?
5. Can you perform a traditional binary serach of a linked list? If so, what is the Big O of the search?
6. What is the Big O of printing all elements in a linked list?

## Implementation of Linked Lists
A linked list is built using nodes. The following is the implementation of a node for a Singly Linked List in C++
```C++
#include <iostream>

using namespace std;

template <typename T>
class Node {
    T data;
    Node<T> *next;
    Node() : next(nullptr) {}
};

int main() {
    Node<int> *head = nullptr;
}
```
1. Sketch the linked list for the following code snippet. Assume the Node class has been defined.
```C++
int main() {
    Node<int> *head = new Node<T>();
    head->data = 0;
    head->next = new Node<T>();
    head->next->data = 1;
    head->next->next = new Node<T>();
    head->next->next->data = 2
}
```
2. Does the following code have a memory leak?
```C++
int main() {
    Node<int> *head = new Node<T>();
    head->data = 0;
    Node<int> *newNode = new Node<T>();
    newNode->data = 1
    head->next = newNode;
    newNode->next = new Node<T>();
    newNode->next->data = 2;
    newNode = newNode->next;
}
```

## Forward List - Standard Template Library
CPP Forward List reference: http://www.cplusplus.com/reference/forward_list/forward_list/  

1. What header needs to be included to utilize forward lists?
2. What functions are utilized to add and remove items from the forward list?
3. Declare a forward list and push the integers 1, 2, 3. Print the elements stored in the list. In what order are the elements printed? Why?
5. What does the following program output?
```C++
#include <iostream>
#include <forward_list>

using namespace std;

int main() {
    forward_list<int> list;
    for (int i = 0; i < 10; i++)
        list.push_front(i);
    for (int i = 0; i < 5; i++)
        list.pop_front();
    cout << endl;
    for (int i : list)
        cout << i << " ";
}
```
7. What does the following program output?
```C++
#include <iostream>
#include <forward_list>

using namespace std;

int main() {
    forward_list<int> list;
    for (int i = 10; i > 0; i--)
        list.push_front(i);
    list.pop_front();
    cout << list.front();
}
```
