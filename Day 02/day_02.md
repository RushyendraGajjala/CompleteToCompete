# Day 02

# Stack

- A stack is a linear data structure that follows the Last-In, First-Out (LIFO) principle meaning the last element you add is the first one to be removed.
- It supports core operations like push (add an element) and pop (remove the top element), along with helpful utility functions such as top (view the top element), size (check number of elements), empty (verify if the stack has no elements), and swap (exchange contents with another stack).

## Real-life Analogy

Imagine a pile of plates in your kitchen:

- **Push** → You wash a plate and put it on top.
- **Pop** → You take the top plate to use.
- **Empty** → Check if there are no plates left.
- **Top** → Just peek at the top plate without taking it.
- **Size** → Count how many plates are stacked.
- **Swap** → Exchange your whole pile with another one.

## Basic Operations

```cpp
#include <bits/stdc++.h> // or you can include both <iostream> & <stack>
using namespace std;

int main() {
    stack<int> stk;
    
    // Push elements into the stack
    stk.push(10); // {10}
    stk.push(20); // {20, 10}
    stk.push(30); // {30, 20, 10}
    
    // Emplace works like push but can be slightly more efficient
    stk.emplace(40); // {40, 30, 20, 10}
    stk.emplace(50); // top -> {50, 40, 30, 20, 10} -> bottom
    
    // Show the element at the top
    cout << "Top element: " << stk.top() << endl; // 50
    
    // Remove the top element
    stk.pop();  // Now top is 40
    
    // Check if the stack is empty
    if (stk.empty()) {
        cout << "Stack is empty." << endl;
    } else {
        cout << "Stack is not empty." << endl;
    }
    
    // Show current size
    cout << "Size after pop: " << stk.size() << endl; // 4
    
    // Swapping with another stack
    stack<int> anotherStk;
    anotherStk.push(99); // {99}
    anotherStk.push(88); // top -> {88, 99} -> bottom
    
    stk.swap(anotherStk);
    
    // Show top elements after swap
    cout << "stk top: " << stk.top() 
         << " | anotherStk top: " << anotherStk.top() << endl;
         
    return 0;
}
```

# Queue

In C++ STL (Standard Template Library), a queue is a container that follows the First-In-First-Out (FIFO) principle meaning the element that is inserted first will be the first one to be removed.

## Real - Life Example

Think of a supermarket checkout line — the first customer to arrive is served first, and each new customer joins at the end of the line. This is exactly how a queue works in programming.

### Basic Operations

```cpp
#include <iostream>
#include <queue> // or can include <bits/stdc++.h>
using namespace std;

int main() {
    queue<int> q;

    // Adding elements (push at the back)
    q.push(10); // {10}
    q.push(20); // {10, 20}
    q.push(30); // front -> {10, 20, 30} <- back

    // Accessing front and back elements
    cout << "Front: " << q.front() << endl; // 10
    cout << "Back: " << q.back() << endl;   // 30

    // Removing the front element
    q.pop(); // removes 10
    cout << "Front after pop: " << q.front() << endl; // 20

    return 0;
}
```

# **Stack vs Queue - Time Complexity**

| **Operation** | **Stack** | **Queue** |
| --- | --- | --- |
| push() | O(1) | O(1) |
| pop() | O(1) | O(1) |
| top() | O(1) | - |
| front() | - | O(1) |
| back() | - | O(1) |

# Priority Queue

In C++ STL, a priority queue is a container that stores elements in order of priority, ensuring that the element with the highest priority is always at the top. By default, it behaves like a max heap, meaning the largest element is given the highest priority.

Unlike simple linear data structures, a priority queue is typically implemented as a binary heap, allowing fast insertion and removal while maintaining the priority order.

### Max Priority Queue

```cpp
#include <iostream>
#include <queue> 
using namespace std;

int main() {
    priority_queue<int> pq; // Creating a max heap priority queue
    
    // Push elements into the priority queue
    pq.push(30); // pq = {30}
    pq.push(10); // pq = {30,10}
    pq.push(50); // pq = {50, 30, 10}
    pq.push(20); // pq = {50, 30, 20, 10}
    
    // Print the top element (element with the highest priority) without removing it
    cout << "Top element: " << pq.top() << endl; // 50
    
    // Pop the top element
    pq.pop();
    
    // Get the size of the priority queue
    cout << "Size of the priority queue: " << pq.size() << endl; // 3
    
    // Check if the priority queue is empty
    if (pq.empty()) {
        cout << "The priority queue is empty." << endl;
    } else {
        cout << "The priority queue is not empty." << endl; // Not empty
    }
    
    // Create a second priority queue
    priority_queue<int> pq2;
    
    // Swap the content of the first priority queue with the second one
    pq.swap(pq2);
    cout << "After swapping, the first priority queue size: " << pq.size() << endl; // 0
    cout << "After swapping, the second priority queue size: " << pq2.size() << endl; // 3
    return 0;
}
```

### Min Priority Queue

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    // Creating a min heap priority queue
    priority_queue<int, vector<int>, greater<int>> min_prq;
    
    // Push elements into the min heap priority queue
    min_prq.push(30); // {30}
    min_prq.push(10); // {10, 30}
    min_prq.push(50); // {10, 30, 50}
    min_prq.push(20); // {10, 20, 30, 50}
    min_prq.push(5);  // {5, 10, 20, 30, 50}
    
    // Print the top element (element with the lowest priority) without removing it
    cout << "Top element: " << min_prq.top() << endl; // 5
    
    // Pop the top element
    min_prq.pop();
    
    // Get the size of the min heap priority queue
    cout << "Size of the priority queue: " << min_prq.size() << endl; // 4
    
    // Check if the min heap priority queue is empty
    if (min_prq.empty()) {
        cout << "The priority queue is empty." << endl;
    } else {
        cout << "The priority queue is not empty." << endl; // Not Empty
    }
    
    // Create a second min heap priority queue
    priority_queue<int, vector<int>, greater<int>> min_prq2;
    
    // Swap the content of the first min heap priority queue with the second one
    min_prq.swap(min_prq2);
    cout << "After swapping, the first priority queue size: " << min_prq.size() << endl; // 0
    cout << "After swapping, the second priority queue size: " << min_prq2.size() << endl; // 4
    return 0;
}
```

## Priority Queue Time Complexity

 

| **Operation** | **Max Heap Priority Queue** | **Min Heap Priority Queue** |
| --- | --- | --- |
| push() | O(log n) | O(log n) |
| pop() | O(log n) | O(log n) |
| top() | O(1) | O(1) |
| size() | O(1) | O(1) |
| empty() | O(1) | O(1) |
| swap() | O(1) | O(1) |
