
## Why Linked Lists?
1. What are the performance limitations of vectors?
2. What are the space limitations of vectors?
3. What capabilities do linked lists provide that vectors do not?
4. What capabilities do vectors provice that linked list do not?
5. Give an example in which you would utilize a linked list over a vector? What about a vector over a linked list?

## Performance of Linked Lists
1. What happens to a vector when it reaches capacitry, as opposed to an array?
1. What fundamental attributes are required in order to create a vector class?
2. What does the constructor of a vector class do? What about the destructor?
3. What is the difference between a vector's capacity and a vector's size?
4. What are the big O's of a vector's push back, insert, and erase functions?

## Implementation of Linked Lists

## Forward List - Standard Template Library
CPP Vector reference: http://www.cplusplus.com/reference/vector/vector/  

1. What is the standard template library?
2. What header needs to be included to utilize vectors?
3. What functions are utilized to add and remove items from the end of the vector?
4. What functions are utilized to check the vectors size and capacity?
5. Write a two vector declarations. One that stores integers and another that stores objects from a class named Students.
6. What does the following program output?
```C++
#include <iostream>
#include <vector>

using namespace std;

int main() {
    vector<int> vect;
    for (int i = 0; i < 5; i++)
        vect.push_back(i);
    for (int i = 0; i < 5; i++)
        cout << vect[i] << " ";
    cout << endl;
    for (int i : vect)
        cout << i << " ";
}
```
7. What does the following program output?
```C++
#include <iostream>
#include <vector>

using namespace std;

int main() {
    vector<int> vect(5);
    for (int i : vect)
        cout << i << " ";
    vect.resize(3);
    vect[1] = 5;
    cout << endl;
    for (int i : vect)
        cout << i << " ";
}
```
8. What does the following program output?
```C++
#include <iostream>
#include <vector>

using namespace std;

int main() {
    vector<int> vect(1);
    cout << "size: " << vect.size() << endl;
    cout << "capacity: " << vect.capacity() << endl << endl;
    vect.push_back(1);
    cout << "size: " << vect.size() << endl;
    cout << "capacity: " << vect.capacity() << endl << endl;
    vect.push_back(1);
    cout << "size: " << vect.size() << endl;
    cout << "capacity: " << vect.capacity() << endl << endl;
    vect.push_back(1);
    vect.push_back(1);
    cout << "size: " << vect.size() << endl;
    cout << "capacity: " << vect.capacity() << endl << endl;
}
```
