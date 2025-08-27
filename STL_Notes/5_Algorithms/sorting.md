# C++ STL Notes

## Algorithms - Sorting

**Definition**  
STL provides ready-made **sorting algorithms** to sort elements in containers.  
Sorting can be done in **ascending, descending, or custom order** using comparators.

**When to Use**  
- When you need elements **in order**.  
- For **competitive programming**, or **preparing containers for binary search**.  

**Common Functions**  

| Function | Description | Requirements |
|----------|------------|--------------|
| `sort(begin, end)` | Sorts elements in ascending order | Random access iterator (vector, deque, array) |
| `sort(begin, end, cmp)` | Sorts using custom comparator | Random access iterator |
| `stable_sort(begin, end)` | Sorts elements while maintaining relative order of equal elements | Random access iterator |
| `partial_sort(begin, middle, end)` | Sorts only the first part up to `middle` | Random access iterator |
| `nth_element(begin, nth, end)` | Places nth element in correct sorted position | Random access iterator |

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v = {5, 1, 4, 2, 3};

    // Sorting in ascending order
    sort(v.begin(), v.end());
    cout << "Ascending: ";
    for(int x : v) cout << x << " "; // 1 2 3 4 5
    cout << "\n";

    // Sorting in descending order
    sort(v.begin(), v.end(), greater<int>());
    cout << "Descending: ";
    for(int x : v) cout << x << " "; // 5 4 3 2 1
    cout << "\n";

    // Stable sort with custom comparator (even first)
    vector<int> v2 = {5, 2, 4, 2, 3};
    stable_sort(v2.begin(), v2.end(), [](int a, int b){ return a%2 < b%2; });
    cout << "Stable sort (even first): ";
    for(int x : v2) cout << x << " "; // 2 2 4 5 3
    cout << "\n";

    // Partial sort (first 3 elements sorted)
    vector<int> v3 = {9, 7, 5, 3, 1};
    partial_sort(v3.begin(), v3.begin()+3, v3.end());
    cout << "Partial sort (first 3): ";
    for(int x : v3) cout << x << " "; // 1 3 5 9 7
    cout << "\n";

    // nth_element (3rd smallest element in correct position)
    vector<int> v4 = {9, 7, 5, 3, 1};
    nth_element(v4.begin(), v4.begin()+2, v4.end());
    cout << "nth_element (3rd smallest): ";
    for(int x : v4) cout << x << " "; // 1 3 5 9 7 (5 is in correct 3rd position)
    cout << "\n";

    return 0;
}
