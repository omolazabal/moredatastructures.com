
## Concepts
1. What does time complexity mean?
2. What is upper bound? Lower bound?
3. What is the difference between O(1) and O(N)?
4. Why is it important to consider worst-case when developing an algorithm?

## Big O Exercises

Give the Big O of the following snippets of code

<h3>Example 1</h3>

```C++
int min = INT_MIN;
int max = INT_MAX;
for (int i = 0; i < n; i++) {
    if (arr[i] > max) max = arr[i];
}
for (int i = 0; i < n; i++) {
    if (arr[i] < min) min = arr[i];
}
```

<h3>Example 2</h3>

```C++
int min = INT_MIN;
int max = INT_MAX;
for (int i = 0; i < n; i++) {
    if (arr[i] < min) min = arr[i];
    if (arr[i] > max) max = arr[i];
}
```

<h3>Example 3</h3>

```C++
void foo(int arr[], int size) {
    int sum = 0;
    int product = 1;
    for (int i = 0; i < size, i++)
        sum += arr[i];
    for (int i = 0; i < size; i++)
        product *= arr[i];
    cout << sum << ", " << product;
}
```

<h3>Example 4</h3>

```C++
void printPairs(int arr[], int size) {
    for (int i = 0; i < size, i++)
        for (int j = 0; j < size; j++)
            cout << arr[i] << " " << arr[j];
}
```

<h3>Example 5</h3>

```C++
void printUnorderedPairs(int arr[], int size) {
    for (int i = 0; i < size, i++)
        for (int j = i + 1; j < size; j++)
            cout << arr[i] << " " << arr[j];
}
```

