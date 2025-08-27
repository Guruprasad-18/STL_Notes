# C++ STL Notes

## Unordered Multimap

**Definition**  
`std::unordered_multimap` is an **associative container** that stores **key-value pairs** and **allows duplicate keys**.  
It is implemented using a **hash table**, so elements are **not ordered**, and average access time is O(1).

**When to Use**  
- When you need **multiple values per key**.  
- When **key order does not matter**.  
- When you want **fast insertion, lookup, and deletion**.

**Key Points**  
- Duplicate keys are allowed.  
- Unordered (no sorting).  
- Average O(1) time for insertion, search, and deletion.  
- Supports iterators for traversal, but order is undefined.

**Common Functions**  
`insert()`, `erase()`, `find()`, `count()`, `equal_range()`, `size()`, `empty()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating an unordered_multimap
    unordered_multimap<int, string> umm;

    // Inserting elements (duplicate keys allowed)
    umm.insert({1, "Apple"});
    umm.insert({2, "Banana"});
    umm.insert({1, "Apricot"});
    umm.insert({3, "Cherry"});
    umm.insert({2, "Blueberry"});

    // Iterating through unordered_multimap
    cout << "Unordered Multimap elements:\n";
    for (auto it : umm) {
        cout << it.first << " -> " << it.second << "\n";
    }

    // Accessing elements with key 1
    cout << "Values with key 1: ";
    auto range = umm.equal_range(1);
    for (auto it = range.first; it != range.second; ++it) {
        cout << it->second << " ";
    }
    cout << "\n";

    // Removing elements with key 2
    umm.erase(2); // removes all elements with key 2

    // Size and emptiness
    cout << "Unordered Multimap size: " << umm.size() << "\n";
    cout << "Is unordered_multimap empty? " << (umm.empty() ? "Yes" : "No") << "\n";

    return 0;
}
