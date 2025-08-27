# C++ STL Notes

## Deque

**Definition**  
`std::deque` (Double Ended Queue) is a sequence container that allows insertion and deletion from both ends efficiently. It provides dynamic resizing and random access like a vector.

**When to Use**  
- When you need to insert/remove elements from both front and back frequently.  
- When middle insertions are rare (as they are slower).  

**Key Points**  
- Supports random access (like vector).  
- Insertion/deletion at both ends is O(1).  
- Slightly slower than `vector` for purely sequential access due to segmented storage.  

**Common Functions**  
`push_back()`, `push_front()`, `pop_back()`, `pop_front()`, `front()`, `back()`, `size()`, `clear()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating and initializing deque
    deque<int> dq = {1, 2, 3};

    // Inserting at the back
    dq.push_back(4);  // dq = [1, 2, 3, 4]

    // Inserting at the front
    dq.push_front(0); // dq = [0, 1, 2, 3, 4]

    // Accessing elements
    cout << "First element: " << dq.front() << "\n"; // 0
    cout << "Last element: " << dq.back() << "\n";   // 4
    cout << "Element at index 2: " << dq[2] << "\n"; // 2

    // Removing from back
    dq.pop_back();   // dq = [0, 1, 2, 3]

    // Removing from front
    dq.pop_front();  // dq = [1, 2, 3]

    // Iterating through deque
    cout << "Deque elements: ";
    for (int x : dq) cout << x << " ";  // Output: 1 2 3
    cout << "\n";

    // Size of deque
    cout << "Size: " << dq.size() << "\n";

    // Clearing deque
    dq.clear(); // dq becomes empty

    return 0;
}
