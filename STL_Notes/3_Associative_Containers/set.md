# C++ STL Notes

## Set

**Definition**  
`std::set` is an **associative container** that stores **unique elements** in **sorted order**.  
It is typically implemented as a **balanced binary search tree**.

**When to Use**  
- When you need **unique sorted elements**.  
- When order matters and duplicates are not allowed.  

**Key Points**  
- Elements are always sorted automatically.  
- Duplicate elements are **not allowed**.  
- Supports iterators and standard algorithms.  
- Searching, insertion, and deletion: O(log n).

**Common Functions**  
`insert()`, `erase()`, `find()`, `count()`, `size()`, `empty()`, `lower_bound()`, `upper_bound()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating a set
    set<int> s;

    // Inserting elements
    s.insert(5);
    s.insert(1);
    s.insert(3);
    s.insert(5); // duplicate ignored
    s.insert(2);

    // Iterating through set
    cout << "Set elements (sorted & unique): ";
    for (int x : s) cout << x << " "; // 1 2 3 5
    cout << "\n";

    // Checking if element exists
    if (s.find(3) != s.end()) cout << "3 is present\n";

    // Counting occurrences
    cout << "Count of 5: " << s.count(5) << "\n"; // 1

    // Removing element
    s.erase(2); // remove element 2
    cout << "After removing 2: ";
    for (int x : s) cout << x << " "; // 1 3 5
    cout << "\n";

    // Using lower_bound and upper_bound
    auto it = s.lower_bound(3); // points to 3
    auto it2 = s.upper_bound(3); // points to 5
    cout << "Lower bound of 3: " << *it << "\n";
    cout << "Upper bound of 3: " << *it2 << "\n";

    // Size and emptiness
    cout << "Size: " << s.size() << "\n";
    cout << "Is set empty? " << (s.empty() ? "Yes" : "No") << "\n";

    return 0;
}
