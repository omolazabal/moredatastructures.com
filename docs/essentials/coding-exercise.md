
!!! note
    If you have not configured you repository yet, please refer to [this guide](https://moredatastructures.com/set-up/). You have to set it up in order to test your solutions.

## Retrieving The New Problem Set

Please run

```
python3 run.py --update
```

To ensure you have the latest problem set. You should be able to see `1-dynamic-memory` in your repository.

## The Code

This week's exercise will focus on dynamic memory, as it is a fundametal aspect of data structures in C++. Specifically, you will be allocating, handling, and freeing memory in C++. This pattern of allocating, handling, and freeing memory is essential when creating data structures (as you will see later in the course).

The `1-dynamic-memory` codebase consists of a program that allows one to enroll students into a course. You will be filling in the empty functions in `src/course.cpp` in order complete this exercise.

!!! warning
    In your repository, please only modify the highlighted regions in `src/course.cpp`

``` C++ tab="include/course.h"

#ifndef COURSE_H
#define COURSE_H

#include "student.h"

using namespace std;

class Course {
private:
    size_t num_students,
           max_students;
    int professor_cwid,
        class_num;
    Student *students;

public:
    Course();
    Course(size_t max);
    ~Course();

    Student get_student(size_t index) const;
    void enroll_student(const Student &student);

    // Mutators
    void set_class_number(int num);
    void set_professor_cwid(int id);

    // Accessors
    int get_class_number() const;
    size_t get_max_students() const;
    size_t get_num_students() const;
    int get_professor_cwid() const;
};

#endif
```

``` C++ tab="include/student.h"

#ifndef STUDENT_H
#define STUDENT_H

#include "string"

using namespace std;

class Student {
private:
    int cwid;
    string student_fname,
        student_lname;

public:
    // Contructors
    Student();
    Student(string fname, string lname, int id);

    // Mutators
    void set_cwid(int id);
    void set_fname(string fname);
    void set_lname(string lname);

    // Accessors
    int get_cwid () const;
    string get_fname () const;
    string get_lname () const;

    friend bool operator==(const Student &lhs, const Student &rhs);
};

#endif
```

``` C++ tab="src/course.cpp" hl_lines="11 12 13 21 22 23 30 31 32 40 41 42 50 51 52"

#include "course.h"
#include "student.h"
#include <stdexcept>

using namespace std;

Course::Course() {
    // Initialize member variables.
    // By default, course will hold a max of 25 students.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}

Course::Course(size_t max) {
    // Very similar to default constructor, but parameter specifies max
    // number of students.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}

Course::~Course() {
    // Utilized to free allocated memory.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}

Student Course::get_student(size_t index) const {
    // Fetch student at specified index.
    // Utilize stdexcept to handle edge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========
    return Student();


    // ====================================================
}

void Course::enroll_student(const Student &student) {
    // Insert a new student
    // Utilize stdexcept to handle endge cases.
    // ========= ONLY MODIFY BETWEEN THE LINES  ===========



    // ====================================================
}


void Course::set_class_number(int num) {
    class_num = num;
}

void Course::set_professor_cwid(int id) {
    professor_cwid = id;
}

int Course::get_class_number() const {
    return class_num;
}

size_t Course::get_max_students() const {
    return max_students;
}

size_t Course::get_num_students() const {
    return num_students;
}

int Course::get_professor_cwid() const {
    return professor_cwid;
}

```

``` C++ tab="src/student.cpp"

#include "student.h"

Student::Student() : cwid(-1) {}

Student::Student(string fname, string lname, int id) :
    cwid(id), student_fname(fname), student_lname(lname) {}

void Student::set_cwid(int id) {
    cwid = id;
}

void Student::set_fname(string fname) {
    student_fname = fname;
}

void Student::set_lname(string lname) {
    student_lname = lname;
}

int Student::get_cwid() const {
    return cwid;
}

string Student::get_fname() const {
    return student_fname;
}

string Student::get_lname() const {
    return student_lname;

}

bool operator==(const Student &lhs, const Student &rhs) {
    return (lhs.cwid == rhs.cwid &&
            lhs.student_fname == rhs.student_fname &&
            lhs.student_lname == rhs.student_lname);
}

```

## Testing

After you have modified your code, test it! You can test it by running

```
python3 run.py --test 1-dynamic-memory
```

At the root of your repository.


If you've successfully implemented all of the functions, your output should look like this:
```
❯ python3 run.py --test 1-dynamic-memory
a - gtest-all.o
a - gtest-all.o
a - gtest_main.o


unit_test_1
Running main() from /Users/oscar/Documents/projects/si-spring-2019/googletest/src/gtest_main.cc
[==========] Running 3 tests from 1 test case.
[----------] Global test environment set-up.
[----------] 3 tests from Dynamic_Memory
[ RUN      ] Dynamic_Memory.Constructor
[       OK ] Dynamic_Memory.Constructor (0 ms)
[ RUN      ] Dynamic_Memory.Enroll_Student
[       OK ] Dynamic_Memory.Enroll_Student (0 ms)
[ RUN      ] Dynamic_Memory.Get_Student
[       OK ] Dynamic_Memory.Get_Student (0 ms)
[----------] 3 tests from Dynamic_Memory (0 ms total)

[----------] Global test environment tear-down
[==========] 3 tests from 1 test case ran. (0 ms total)
[  PASSED  ] 3 tests.
```

