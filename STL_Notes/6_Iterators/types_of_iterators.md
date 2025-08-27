# C++ STL Notes

## Iterators - Types of Iterators

**Definition**  
STL provides different **types of iterators** depending on how elements in a container can be accessed.  
Each iterator type supports a specific set of operations.

**When to Use**  
- Choose the iterator type based on **container type** and **required operations**.  
- Required for **STL algorithms**, traversal, or element manipulation.

**Iterator Types**  

| Iterator Type | Description | Example Containers | Operations Supported |
|---------------|------------|------------------|-------------------|
| Input Iterator | Can **read elements once** in a single pass | `istream_iterator` | `*it`, `++it` |
| Output Iterator | Can **write elements once** in a single pass | `ostream_iterator` | `*it = value`, `++it` |
| Forward Iterator | Can traverse **forward multiple times** | `forward_list` | `*it`, `++it` |
| Bidirectional Iterator | Can traverse **forward & backward** | `list`, `set`, `map` | `*it`, `++it`, `--it` |
| Random Access Iterator | Can access **any element directly** | `vector`, `deque`, `array` | `*it`, `++it`, `--it`, `it + n`, `it - n`, `it[n]` |

**Key Points**  
- **Input/Output iterators** are used for single-pass streams.  
- **Forward/Bidirectional iterators** allow multi-pass traversal.  
- **Random Access iterators** allow the most operations (like array indexing).  
- Most STL algorithms require the **appropriate iterator type**.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v = {10, 20, 30, 40, 50};
    list<int> lst = {1, 2, 3, 4, 5};

    // Random Access Iterator (vector)
    cout << "Vector elements using random access iterator: ";
    for (vector<int>::iterator it = v.begin(); it != v.end(); ++it)
        cout << *it << " ";
    cout << "\n";

    // Bidirectional Iterator (list)
    cout << "List elements using bidirectional iterator: ";
    for (list<int>::iterator it = lst.begin(); it != lst.end(); ++it)
        cout << *it << " ";
    cout << "\n";

    // Reverse traversal using reverse iterator
    cout << "Vector reversed: ";
    for (vector<int>::reverse_iterator rit = v.rbegin(); rit != v.rend(); ++rit)
        cout << *rit << " ";
    cout << "\n";

    return 0;
}
