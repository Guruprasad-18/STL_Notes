# C++ STL Notes

## Multimap

**Definition**  
`std::multimap` is an **associative container** that stores elements in **key-value pairs**, but **allows duplicate keys**.  
It is implemented as a **balanced binary search tree**, so keys are stored in **sorted order**.

**When to Use**  
- When you need **multiple values for the same key**.  
- When order of keys matters and duplicates are allowed.  

**Key Points**  
- Duplicate keys are allowed.  
- Elements are stored as pairs: `pair<const Key, Value>`.  
- Supports iterators and STL algorithms.  
- Searching by key returns **all matching elements**.  

**Common Functions**  
`insert()`, `erase()`, `find()`, `count()`, `equal_range()`, `size()`, `empty()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating a multimap
    multimap<int, string> mp;

    // Inserting elements (duplicate keys allowed)
    mp.insert({1, "Apple"});
    mp.insert({2, "Banana"});
    mp.insert({1, "Apricot"});
    mp.insert({3, "Cherry"});
    mp.insert({2, "Blueberry"});

    // Iterating through multimap
    cout << "Multimap elements:\n";
    for (auto it : mp) {
        cout << it.first << " -> " << it.second << "\n";
    }

    // Accessing elements with key 1
    cout << "Values with key 1: ";
    auto range = mp.equal_range(1);
    for (auto it = range.first; it != range.second; it++) {
        cout << it->second << " ";
    }
    cout << "\n";

    // Removing elements with key 2
    mp.erase(2); // removes all elements with key 2

    // Size and emptiness
    cout << "Multimap size: " << mp.size() << "\n";
    cout << "Is multimap empty? " << (mp.empty() ? "Yes" : "No") << "\n";

    return 0;
}
