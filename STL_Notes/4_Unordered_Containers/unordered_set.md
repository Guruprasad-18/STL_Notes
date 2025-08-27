# C++ STL Notes

## Unordered Set

**Definition**  
`std::unordered_set` is an **associative container** that stores **unique elements** in **no particular order**.  
It is implemented using a **hash table**, so average access, insertion, and deletion are O(1).

**When to Use**  
- When you need **unique elements** and **fast lookup**.  
- When the order of elements **does not matter**.  

**Key Points**  
- Elements are unique; duplicates are ignored.  
- Unordered — no automatic sorting.  
- Average O(1) operations.  
- Supports iterators for traversal, but order is undefined.

**Common Functions**  
`insert()`, `erase()`, `find()`, `count()`, `size()`, `empty()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating an unordered_set
    unordered_set<int> us;

    // Inserting elements
    us.insert(5);
    us.insert(1);
    us.insert(3);
    us.insert(5); // duplicate ignored
    us.insert(2);

    // Iterating through unordered_set
    cout << "Unordered Set elements: ";
    for (int x : us) cout << x << " "; // order not guaranteed
    cout << "\n";

    // Checking if an element exists
    if (us.find(3) != us.end()) cout << "3 is present\n";

    // Counting occurrences
    cout << "Count of 5: " << us.count(5) << "\n"; // 1

    // Removing an element
    us.erase(2); // remove element 2
    cout << "After removing 2: ";
    for (int x : us) cout << x << " ";
    cout << "\n";

    // Size and emptiness
    cout << "Size: " << us.size() << "\n";
    cout << "Is unordered_set empty? " << (us.empty() ? "Yes" : "No") << "\n";

    return 0;
}
