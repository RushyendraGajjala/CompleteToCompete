# Day 01

# Introduction

The C++ STL (Standard Template Library) offers a powerful set of containers, algorithms, and data structures that simplify tasks like data handling, searching, and sorting makes code more efficient and reusable.

## Fundamental Components of the STL

### **Containers**

The STL provides a variety of containers such as `vector`, `list`, `map`, `set`, and `stack`, each designed to store and manage data efficiently.

### **Algorithms**

STL includes a broad range of built-in algorithms like `sort`, `find`, and `count`, which operate directly on containers to perform common tasks with ease.

### **Iterators**

Iterators act as generalized pointers, allowing sequential access to elements within containers. STL provides different iterator types tailored to specific container behaviors.

### **Function Objects (Functors)**

Functors are objects that can be used in place of regular functions. They can be passed as arguments to algorithms, enabling customized and reusable behavior.

## **Arrays**

Arrays are organized data structures capable of storing a specific quantity of elements, all of the same data type, in adjacent memory slots.

They act as containers for managing and retrieving items based on their position or index.

### **Contiguous Memory Allocation**

Arrays consist of elements of the same data type, like integers or characters, etc and are stored in a single block of adjacent memory locations.

### Array Declaration

```cpp
#include <iostream>
using namespace std;

int main(){
    int arr[5];
    return 0;
}
```

# Array v Vector

| **Aspect** | **Arrays** | **Vectors** |
| --- | --- | --- |
| **Size Flexibility** | Fixed size; must be defined at the time of declaration | Dynamic size; can grow or shrink as needed |
| **Initialization** | Initialized with a fixed set of elements | Can be initialized with a flexible and dynamic set of elements |
| **Function Support** | Limited built-in functionality | Rich set of built-in functions for manipulation and access |

## Pair in C++

- A **pair** in C++ is a simple container that holds exactly **two values**, which can be of **different types**. You can access these values using `.first` and `.second`.
- It’s commonly used when you want to keep two related values together — for example, a name and age, or a key and value in a map.
- Pairs are defined in the `<utility>` header, but you can also use them by including `<bits/stdc++.h>`.

### Syntax

```cpp
pair<DataType1, DataType2> variableName;   // Declaring a pair

variableName.first = value1;               // Setting the first value
variableName.second = value2;              // Setting the second value
```

### Example

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating pairs with different data types
    pair<int, double> numberPi = {42, 3.14159};         // Integer and double
    pair<int, char> indexChar = {0, 'a'};               // Integer and character
    pair<int, string> idMessage = {21, "Hello World"};  // Integer and string

    // Printing the values inside each pair
    cout << "numberPi -> First: " << numberPi.first << ", Second: " << numberPi.second << endl;
    cout << "indexChar -> First: " << indexChar.first << ", Second: " << indexChar.second << endl;
    cout << "idMessage -> First: " << idMessage.first << ", Second: " << idMessage.second << endl;

    // Nested pair (a pair inside another pair)
    pair<int, pair<int, int>> nested = {0, {10, 20}};
    cout << "nested -> First: " << nested.first
         << ", Inner First: " << nested.second.first
         << ", Inner Second: " << nested.second.second << endl;

    // Array of pairs (like a list of paired values)
    pair<int, string> dataList[] = {
        {1, "One"},
        {2, "Two"},
        {3, "Three"}
    };

    // Accessing the second item in the array
    cout << "dataList[1] -> First: " << dataList[1].first
         << ", Second: " << dataList[1].second << endl;

    return 0;
}

```

## Vector

- A `vector` in C++ is a dynamic array that can **automatically resize** itself when elements are added or removed. It stores elements in **contiguous memory**, allowing fast access using indexing.
- To use vectors, include the `<vector>` header (or `<bits/stdc++.h>` for competitive programming).

### Declaration

```cpp
#include <iostream>
#include <vector>  // Standard header for using vectors
// You can also use: #include <bits/stdc++.h> for all-in-one access (mostly used in competitive programming)
using namespace std;

int main() {
    // 1. Declare an empty vector of integers
    vector<int> v;

    // 2. Create a vector of size 5, all elements initialized to 20
    vector<int> v1(5, 20);

    // 3. Create a vector of size 5, default-initialized to 0
    vector<int> v2(5);

    // 4. Copy an existing vector (v1) into a new vector (v3)
    vector<int> v3(v1);

    return 0;
}
```

### **Push Back or Emplace Back**

- Adds elements to the end of the vector

```cpp
#include <iostream>
#include <vector> // For using vector container
// Alternatively: #include <bits/stdc++.h> (mostly used in competitive programming)
using namespace std;

int main() {
    // Creating an empty vector of integers
    vector<int> v;

    // Adding elements to the vector
    v.push_back(10);      // Adds 10 at the end
    v.emplace_back(20);   // Adds 20 at the end (faster than push_back)

    // Accessing elements using index
    cout << v[0] << " " << v[1] << endl;  // Output: 10 20

    return 0;
}
```

## Vector of Pairs

```cpp
#include <iostream>
#include <vector> // For using the vector container
// Alternatively: #include <bits/stdc++.h> (used in competitive programming)
using namespace std;

int main() {
    // Creating a vector that stores pairs of integers
    vector<pair<int, int>> pairs;

    // Adding a pair using push_back
    pairs.push_back({10, 20}); // Adds the pair (10, 20) to the vector

    // Adding a pair using emplace_back
    pairs.emplace_back(30, 40); // Adds the pair (30, 40) more efficiently

    // Accessing and printing the pairs
    cout << pairs[0].first << " " << pairs[0].second << endl; // Output: 10 20
    cout << pairs[1].first << " " << pairs[1].second << endl; // Output: 30 40

    return 0;
}
#include <iostream>
#include <vector> // For using the vector container
// Alternatively: #include <bits/stdc++.h> (used in competitive programming)
using namespace std;

int main() {
    // Creating a vector that stores pairs of integers
    vector<pair<int, int>> pairs;

    // Adding a pair using push_back
    pairs.push_back({10, 20}); // Adds the pair (10, 20) to the vector

    // Adding a pair using emplace_back
    pairs.emplace_back(30, 40); // Adds the pair (30, 40) more efficiently

    // Accessing and printing the pairs
    cout << pairs[0].first << " " << pairs[0].second << endl; // Output: 10 20
    cout << pairs[1].first << " " << pairs[1].second << endl; // Output: 30 40

    return 0;
}
```

- `vector<pair<int, int>>` means you're storing a list of pairs where each pair has two integers.
- `push_back` and `emplace_back` both add elements, but `emplace_back` is a bit faster and avoids some unnecessary copying.
- You access the elements of each pair using `.first` and `.second`

## Iterators

- Iterators are objects used to traverse containers like vectors.

```cpp
#include <iostream>
#include <vector> // For using vector container
// You can also use: #include <bits/stdc++.h>
using namespace std;

int main() {
    // Create and initialize a vector with values
    vector<int> v = {10, 20, 30, 40, 50};

    // --------- 1. Using Iterators (Forward) ---------
    // 'begin()' gives iterator to the first element
    vector<int>::iterator it = v.begin();

    // 'end()' gives iterator just past the last element, so we move one step back
    vector<int>::iterator it1 = v.end();
    it1--; // Now it1 points to the last element

    cout << "First element using begin(): " << *it << endl;   // Output: 10
    cout << "Last element using end()-1: " << *it1 << endl;   // Output: 50

    // --------- 2. Using Reverse Iterators ---------
    // 'rbegin()' points to last element, 'rend()' is past the first element
    vector<int>::reverse_iterator rIt = v.rbegin();
    vector<int>::reverse_iterator rEndIt = v.rend();
    rEndIt--; // Move one step back to point to the first element

    cout << "First element in reverse: " << *rIt << endl;      // Output: 50
    cout << "Last element in reverse: " << *rEndIt << endl;    // Output: 10

    // --------- 3. Using back() ---------
    // back() directly gives the last element of the vector
    int lastElement = v.back();
    cout << "Last element using back(): " << lastElement << endl; // Output: 50

    return 0;
}
```

## Printing Vectors

```cpp
#include <iostream>
#include <vector> // or use #include <bits/stdc++.h>
using namespace std;

int main() {
    // Let’s start with a simple vector of integers
    vector<int> v = {10, 20, 30, 40, 50};

    // 1. The classic way using an iterator
    cout << "1. Using a basic for loop with iterator:" << endl;
    for (vector<int>::iterator it = v.begin(); it != v.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

    // 2. Same as above, but a bit cleaner with auto
    cout << "2. Using auto with iterator (less typing, same job):" << endl;
    for (auto it = v.begin(); it != v.end(); it++) {
        cout << *it << " ";
    }
    cout << endl;

    // 3. A more modern way range-based for loop
    cout << "3. Using range-based for loop (simple and clean):" << endl;
    for (int val : v) {
        cout << val << " ";
    }
    cout << endl;

    // 4. Even simpler range-based loop with auto
    cout << "4. Range-based loop with auto (short and sweet):" << endl;
    for (auto val : v) {
        cout << val << " ";
    }
    cout << endl;

    return 0;
}
```

- **Using a For Loop with Iterator:** We can manually declare an iterator and move through the vector step by step. It's the traditional way, gives full control, but involves more typing.
- **Using Auto with Iterator:** Instead of specifying the full type of the iterator, we let the compiler figure it out using `auto`. It keeps the code clean and readable.
- **Using Range-Based For Loop:** This is a modern and simpler approach — we directly loop through each element of the vector, no need to worry about iterators.
- **Using Auto with Range-Based For Loop:** Here, we combine the range-based loop with `auto` so the compiler figures out the type of each element automatically. It's the shortest and most beginner-friendly way.
- **Note**: The auto keyword is used to let the compiler automatically detect the data type of a variable. It's especially helpful with complex types like iterators or long template types.

### Deletion Functions

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v = {10, 20, 30, 40, 50};

    // Let's remove the 3rd element (which is 30, at index 2)
    v.erase(v.begin() + 2);  // Now v = {10, 20, 40, 50}

    // Now, remove a range of elements from index 1 to index 2 (excluding index 3)
    // That means elements 20 and 40 will be removed
    v.erase(v.begin() + 1, v.begin() + 3); // Now v = {10, 50}

    // Let's print the final contents of the vector
    for (int element : v) {
        cout << element << " ";
    }
    cout << endl;

    return 0;
}
```

## **size(), pop_back(), swap, clear() and empty()**

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v = {10, 20, 30, 40, 50};

    // Let's check how many elements are in the vector
    cout << "Vector size: " << v.size() << endl;  // Output: 5

    // Now we'll remove the last element (which is 50)
    v.pop_back();  // v becomes: {10, 20, 30, 40}

    // Let's create another vector and swap its contents with v
    vector<int> v1 = {100, 200, 300};
    v.swap(v1);  
    // Now: 
    // v = {100, 200, 300}
    // v1 = {10, 20, 30, 40}

    // Let's clear all elements from v1
    v1.clear();  // Now v1 is completely empty

    // We'll check if v1 is empty
    cout << "Is v1 empty? " << v1.empty() << endl;  // Output: 1 (true)

    // Finally, print the elements in vector v
    cout << "v: ";
    for (int element : v) {
        cout << element << " ";
    }
    cout << endl;  // Output: 100 200 300

    return 0;
}

```
