# C++ STL Notes

## Vector

**Definition**  
A vector is a dynamic array in C++ STL that can change its size automatically when elements are inserted or deleted. It stores elements in contiguous memory locations and allows fast random access.

**When to Use**  
- When array size is unknown at compile time.  
- When you need fast access and frequent insertions/removals at the end.  

**Key Points**  
- Contiguous memory storage (like arrays).  
- Fast random access: O(1).  
- Insert/remove at end: O(1) amortized.  
- Insert/remove in middle: O(n).  

**Common Functions**  
`push_back()`, `pop_back()`, `insert()`, `erase()`, `clear()`, `size()`, `capacity()`, `reserve()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating and initializing a vector
    vector<int> v = {1, 2, 3};      // v = [1, 2, 3]

    // Adding elements
    v.push_back(4);                 // v = [1, 2, 3, 4]
    v.emplace_back(5);              // v = [1, 2, 3, 4, 5]

    // Accessing elements
    cout << "First element: " << v.front() << "\n";   // 1
    cout << "Last element: " << v.back() << "\n";     // 5
    cout << "Element at index 2: " << v[2] << "\n";   // 3

    // Inserting element
    v.insert(v.begin() + 2, 10);    // Insert 10 at index 2 → [1, 2, 10, 3, 4, 5]

    // Removing last element
    v.pop_back();                   // Removes 5 → [1, 2, 10, 3, 4]

    // Removing element at index 1
    v.erase(v.begin() + 1);         // Removes 2 → [1, 10, 3, 4]

    // Iterating
    cout << "Vector elements: ";
    for (int x : v) cout << x << " ";   // Output: 1 10 3 4
    cout << "\n";

    // Size & capacity
    cout << "Size: " << v.size() << "\n";
    cout << "Capacity: " << v.capacity() << "\n";

    // Clearing vector
    v.clear();                      // Now v is empty
    cout << "Is vector empty? " << (v.empty() ? "Yes" : "No") << "\n";

    return 0;
}
