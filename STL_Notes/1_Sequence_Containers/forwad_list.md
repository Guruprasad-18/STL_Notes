# C++ STL Notes

## Forward List

**Definition**  
`std::forward_list` is a **singly linked list** container in STL.  
It allows efficient insertion and deletion at any position but **only supports forward traversal**.

**When to Use**  
- When memory efficiency is important (uses less memory than `list`).  
- When you need fast insertions/deletions but only in **forward direction**.  
- Suitable for large datasets where bidirectional traversal is not required.

**Key Points**  
- Singly linked list — each node has a pointer to the next node only.  
- No random access (`[]` not supported).  
- Supports only **Forward Iterator**.  
- More memory efficient than `list`.  

**Common Functions**  
`push_front()`, `pop_front()`, `insert_after()`, `erase_after()`, `remove()`, `sort()`, `reverse()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating and initializing forward_list
    forward_list<int> fl = {1, 2, 3};

    // Inserting at front
    fl.push_front(0);  // fl = [0, 1, 2, 3]

    // Iterating through forward_list
    cout << "Forward List elements: ";
    for (int x : fl) cout << x << " "; // 0 1 2 3
    cout << "\n";

    // Removing first element
    fl.pop_front(); // fl = [1, 2, 3]

    // Inserting after a position
    auto it = fl.begin();
    fl.insert_after(it, 10); // fl = [1, 10, 2, 3]

    // Erasing after a position
    it = fl.begin();
    fl.erase_after(it); // removes 10 → fl = [1, 2, 3]

    // Removing by value
    fl.remove(2); // fl = [1, 3]

    // Sorting forward_list
    fl.push_front(5);
    fl.push_front(0);
    fl.sort(); // fl = [0, 1, 3, 5]

    // Reversing forward_list
    fl.reverse(); // fl = [5, 3, 1, 0]

    // Display final forward_list
    cout << "Final Forward List: ";
    for (int x : fl) cout << x << " "; // 5 3 1 0
    cout << "\n";

    return 0;
}
