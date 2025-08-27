# C++ STL Notes

## Algorithms - Searching

**Definition**  
STL provides ready-made **searching algorithms** to find elements in containers.  
They work with iterators and can operate on any container supporting the required iterator type.

**When to Use**  
- When you need to **find elements** in a container efficiently.  
- For **binary search, linear search, or checking existence** of elements.

**Common Functions**  

| Function | Description | Requirements |
|----------|------------|--------------|
| `find(begin, end, value)` | Returns iterator to first occurrence of value, or `end` if not found | Any container with forward iterator |
| `binary_search(begin, end, value)` | Returns `true` if value exists (requires sorted container) | Random access iterator (vector, deque, array) |
| `count(begin, end, value)` | Returns number of occurrences of value | Any container with forward iterator |
| `find_if(begin, end, predicate)` | Returns iterator to first element satisfying predicate | Any container with forward iterator |

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v = {1, 3, 5, 7, 9, 3, 5};

    // Linear search using find
    auto it = find(v.begin(), v.end(), 5);
    if (it != v.end())
        cout << "Found 5 at index: " << distance(v.begin(), it) << "\n";
    else
        cout << "5 not found\n";

    // Counting occurrences of 3
    int cnt = count(v.begin(), v.end(), 3);
    cout << "3 appears " << cnt << " times\n";

    // Using binary_search (requires sorted container)
    sort(v.begin(), v.end()); // 1 3 3 5 5 7 9
    if (binary_search(v.begin(), v.end(), 7))
        cout << "7 is present\n";
    else
        cout << "7 not found\n";

    // Using find_if with a lambda predicate
    auto it2 = find_if(v.begin(), v.end(), [](int x){ return x > 5; });
    if (it2 != v.end())
        cout << "First element > 5: " << *it2 << "\n";

    return 0;
}
