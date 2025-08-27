# C++ STL Notes

## Unordered Map

**Definition**  
`std::unordered_map` is an **associative container** that stores **key-value pairs** with **unique keys**, but unlike `map`, it does **not store keys in any order**.  
It is implemented using a **hash table**, so lookups are generally faster: O(1) average.

**When to Use**  
- When you need **fast access to key-value pairs**.  
- When key order does **not matter**.  

**Key Points**  
- Keys are unique; duplicates not allowed.  
- Average O(1) time for search, insert, and delete.  
- Cannot use iterators for sorted traversal (unsorted).  

**Common Functions**  
`insert()`, `erase()`, `find()`, `count()`, `size()`, `empty()`, `operator[]`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating an unordered_map
    unordered_map<int, string> umap;

    // Inserting elements
    umap[1] = "Apple";             // Using operator[]
    umap.insert({2, "Banana"});    // Using insert()
    umap.insert(make_pair(3, "Cherry"));

    // Accessing elements
    cout << "Key 2 maps to: " << umap[2] << "\n"; // Banana
    cout << "Key 3 maps to: " << umap.at(3) << "\n"; // Cherry

    // Iterating through unordered_map (order not guaranteed)
    cout << "Unordered Map elements:\n";
    for (auto it : umap) {
        cout << it.first << " -> " << it.second << "\n";
    }

    // Checking if key exists
    if (umap.find(4) == umap.end()) cout << "Key 4 not found\n";

    // Removing elements
    umap.erase(2); // Removes key 2

    // Size and emptiness
    cout << "Unordered Map size: " << umap.size() << "\n";
    cout << "Is unordered_map empty? " << (umap.empty() ? "Yes" : "No") << "\n";

    return 0;
}
