# C++ STL Notes

## Iterators - Iterator Basics

**Definition**  
An **iterator** is an object that points to an element in a container and allows **traversal and access** to elements.  
Iterators in STL act like **pointers** and work with all standard containers.

**When to Use**  
- To **traverse containers** without using indices (especially for lists, sets, maps).  
- When using **STL algorithms** that require iterator ranges.  

**Key Points**  
- Work like pointers: `*it` to access element, `it++` to move forward.  
- Can be passed to STL algorithms like `sort()`, `find()`, `reverse()`.  
- Iterator types depend on container (input, output, forward, bidirectional, random access).

**Common Functions**  
- `begin()` → returns iterator to the first element  
- `end()` → returns iterator past the last element  
- `rbegin()` → returns reverse iterator to last element  
- `rend()` → returns reverse iterator past first element  

**Iterator Types**  

| Type | Description | Containers |
|------|------------|------------|
| Input Iterator | Read elements once | istream_iterator |
| Output Iterator | Write elements once | ostream_iterator |
| Forward Iterator | Traverse forward multiple times | forward_list |
| Bidirectional Iterator | Traverse forward & backward | list, set, map |
| Random Access Iterator | Direct jump to any element | vector, deque, array |

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v = {10, 20, 30, 40, 50};

    // Using iterator to traverse vector
    cout << "Vector elements: ";
    for (vector<int>::iterator it = v.begin(); it != v.end(); ++it) {
        cout << *it << " "; // dereference iterator
    }
    cout << "\n";

    // Using auto keyword for iterator
    cout << "Using auto: ";
    for (auto it = v.begin(); it != v.end(); ++it) {
        cout << *it << " ";
    }
    cout << "\n";

    // Reverse iterator
    cout << "Reversed: ";
    for (auto rit = v.rbegin(); rit != v.rend(); ++rit) {
        cout << *rit << " ";
    }
    cout << "\n";

    return 0;
}
