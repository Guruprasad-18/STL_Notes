# C++ STL Notes

## Multiset

**Definition**  
`std::multiset` is an **associative container** that stores elements in **sorted order** and **allows duplicate elements**.  
It is typically implemented as a **balanced binary search tree**.

**When to Use**  
- When you need a **collection of sorted elements**.  
- When duplicate elements are allowed and order matters.  

**Key Points**  
- Elements are always sorted.  
- Duplicate elements are allowed.  
- No direct access by index (`[]` not supported).  
- Supports iterators and standard algorithms.

**Common Functions**  
`insert()`, `erase()`, `find()`, `count()`, `size()`, `empty()`, `equal_range()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating a multiset
    multiset<int> ms;

    // Inserting elements
    ms.insert(5);
    ms.insert(1);
    ms.insert(3);
    ms.insert(5); // duplicate allowed
    ms.insert(2);

    // Iterating through multiset
    cout << "Multiset elements (sorted): ";
    for (int x : ms) cout << x << " "; // 1 2 3 5 5
    cout << "\n";

    // Counting occurrences of an element
    cout << "Count of 5: " << ms.count(5) << "\n"; // 2

    // Finding elements
    auto it = ms.find(3);
    if (it != ms.end()) cout << "Element 3 found\n";

    // Removing elements
    ms.erase(5); // removes all 5s
    cout << "After removing 5s: ";
    for (int x : ms) cout << x << " "; // 1 2 3
    cout << "\n";

    // Size and emptiness
    cout << "Size: " << ms.size() << "\n";
    cout << "Is multiset empty? " << (ms.empty() ? "Yes" : "No") << "\n";

    return 0;
}
