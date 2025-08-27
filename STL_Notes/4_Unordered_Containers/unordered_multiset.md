# C++ STL Notes

## Unordered Multiset

**Definition**  
`std::unordered_multiset` is an **associative container** that stores **elements** with **duplicate values allowed**.  
It is implemented using a **hash table**, so elements are **not sorted**, and average access time is O(1).

**When to Use**  
- When you need a collection of **unsorted elements with duplicates**.  
- When you need **fast insertion, lookup, and deletion**.  

**Key Points**  
- Duplicate elements are allowed.  
- Elements are **unordered** (no sorting).  
- Average O(1) time for insertion, search, and deletion.  
- Supports iterators for traversal, but order is undefined.

**Common Functions**  
`insert()`, `erase()`, `find()`, `count()`, `size()`, `empty()`, `equal_range()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating an unordered_multiset
    unordered_multiset<int> ums;

    // Inserting elements (duplicates allowed)
    ums.insert(5);
    ums.insert(1);
    ums.insert(3);
    ums.insert(5); // duplicate allowed
    ums.insert(2);

    // Iterating through unordered_multiset
    cout << "Unordered Multiset elements: ";
    for (int x : ums) cout << x << " "; // order not guaranteed
    cout << "\n";

    // Counting occurrences of an element
    cout << "Count of 5: " << ums.count(5) << "\n"; // 2

    // Finding an element
    auto it = ums.find(3);
    if (it != ums.end()) cout << "Element 3 found\n";

    // Removing elements
    ums.erase(5); // removes all occurrences of 5
    cout << "After removing 5s: ";
    for (int x : ums) cout << x << " ";
    cout << "\n";

    // Size and emptiness
    cout << "Size: " << ums.size() << "\n";
    cout << "Is unordered_multiset empty? " << (ums.empty() ? "Yes" : "No") << "\n";

    return 0;
}
