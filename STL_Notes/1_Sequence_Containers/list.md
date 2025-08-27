# C++ STL Notes

## List

**Definition**  
`std::list` is a **doubly linked list** container in STL.  
It allows efficient insertion and deletion at both ends and at any position, but it does not provide random access like `vector` or `deque`.

**When to Use**  
- When frequent insertions/deletions are needed anywhere in the sequence.  
- When you don’t need direct access by index.  

**Key Points**  
- Doubly linked list — each node has pointers to previous and next node.  
- No random access (`[]` not supported).  
- Forward and backward traversal supported.  
- Insertion/deletion at known position: O(1), searching: O(n).  

**Common Functions**  
`push_back()`, `push_front()`, `pop_back()`, `pop_front()`, `insert()`, `erase()`, `remove()`, `sort()`, `reverse()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating and initializing list
    list<int> li = {1, 2, 3};

    // Inserting at back
    li.push_back(4);   // li = [1, 2, 3, 4]

    // Inserting at front
    li.push_front(0);  // li = [0, 1, 2, 3, 4]

    // Iterating through list
    cout << "List elements: ";
    for (int x : li) cout << x << " "; // 0 1 2 3 4
    cout << "\n";

    // Removing last element
    li.pop_back();  // li = [0, 1, 2, 3]

    // Removing first element
    li.pop_front(); // li = [1, 2, 3]

    // Inserting at specific position
    auto it = li.begin();
    advance(it, 1);  // move iterator to index 1
    li.insert(it, 10); // li = [1, 10, 2, 3]

    // Erasing specific position
    it = li.begin();
    advance(it, 2);  // move to element '2'
    li.erase(it);    // li = [1, 10, 3]

    // Removing by value
    li.remove(10); // li = [1, 3]

    // Sorting list
    li.push_back(5);
    li.push_back(0);
    li.sort(); // li = [0, 1, 3, 5]

    // Reversing list
    li.reverse(); // li = [5, 3, 1, 0]

    // Display final list
    cout << "Final list: ";
    for (int x : li) cout << x << " "; // 5 3 1 0
    cout << "\n";

    return 0;
}
