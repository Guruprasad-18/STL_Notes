# C++ STL Notes

## Queue

**Definition**  
`std::queue` is a container adapter that implements a **FIFO (First In First Out)** data structure.  
Elements are inserted at the **back** and removed from the **front**.

**When to Use**  
- When you need to process elements in the order they were added.  
- For problems like task scheduling, BFS in graphs, or buffering data.

**Key Points**  
- FIFO behavior (first in, first out).  
- Cannot iterate directly like vector or list.  
- Insertion: `push()`, Removal: `pop()`, Access front/back: `front()`, `back()`.  

**Common Functions**  
`push()`, `pop()`, `front()`, `back()`, `empty()`, `size()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating a queue
    queue<int> q;

    // Adding elements
    q.push(10);  // q = [10]
    q.push(20);  // q = [10, 20]
    q.push(30);  // q = [10, 20, 30]

    // Accessing elements
    cout << "Front element: " << q.front() << "\n"; // 10
    cout << "Back element: " << q.back() << "\n";   // 30

    // Removing element
    q.pop(); // removes 10 → q = [20, 30]
    cout << "After pop, front element: " << q.front() << "\n"; // 20

    // Checking size and emptiness
    cout << "Queue size: " << q.size() << "\n";        // 2
    cout << "Is queue empty? " << (q.empty() ? "Yes" : "No") << "\n"; // No

    // Removing all elements
    while (!q.empty()) {
        cout << q.front() << " ";
        q.pop();
    }
    cout << "\n";

    return 0;
}
