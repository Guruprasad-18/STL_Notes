# C++ STL Notes

## Map

**Definition**  
`std::map` is an **associative container** that stores elements in **key-value pairs** with **unique keys**.  
It is implemented as a **balanced binary search tree**, so keys are stored in **sorted order**.

**When to Use**  
- When you need **fast lookup, insertion, and deletion by key**.  
- When keys must be **unique**.  

**Key Points**  
- Elements are stored as pairs: `pair<const Key, Value>`.  
- Keys are unique; duplicate keys are not allowed.  
- Supports iterators and STL algorithms.  
- Commonly implemented as a **Red-Black tree**: O(log n) operations.

**Common Functions**  
`insert()`, `erase()`, `find()`, `count()`, `size()`, `empty()`, `operator[]`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating a map
    map<int, string> mp;

    // Inserting elements
    mp[1] = "Apple";             // Using operator[]
    mp.insert({2, "Banana"});    // Using insert()
    mp.insert(make_pair(3, "Cherry"));

    // Accessing elements
    cout << "Key 2 maps to: " << mp[2] << "\n"; // Banana
    cout << "Key 3 maps to: " << mp.at(3) << "\n"; // Cherry

    // Iterating through map
    cout << "Map elements:\n";
    for (auto it : mp) {
        cout << it.first << " -> " << it.second << "\n";
    }

    // Checking if key exists
    if (mp.find(4) == mp.end()) cout << "Key 4 not found\n";

    // Removing elements
    mp.erase(2); // Removes key 2

    // Size and emptiness
    cout << "Map size: " << mp.size() << "\n";
    cout << "Is map empty? " << (mp.empty() ? "Yes" : "No") << "\n";

    return 0;
}
