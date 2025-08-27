# C++ STL Notes

## Algorithms - Utility Algorithms

**Definition**  
STL provides **utility algorithms** for common operations like reversing, swapping, finding min/max, summing ranges, and generating sequences.  

**When to Use**  
- To **manipulate containers quickly** without writing loops manually.  
- For **competitive programming** or cleaner code in projects.  

**Common Functions**  

| Function | Description | Requirements |
|----------|------------|--------------|
| `reverse(begin, end)` | Reverses the order of elements | Any bidirectional iterator |
| `max_element(begin, end)` | Returns iterator to the maximum element | Any forward iterator |
| `min_element(begin, end)` | Returns iterator to the minimum element | Any forward iterator |
| `swap(a, b)` | Swaps two elements | Any type |
| `accumulate(begin, end, init)` | Returns sum of elements starting with `init` | Any forward iterator (`<numeric>` header) |
| `iota(begin, end, start)` | Fills container with sequentially increasing values starting from `start` | Random access iterator |

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;
#include <numeric> // for accumulate, iota

int main() {
    vector<int> v = {5, 2, 9, 1, 7};

    // Reverse
    reverse(v.begin(), v.end());
    cout << "Reversed: ";
    for(int x : v) cout << x << " "; // 7 1 9 2 5
    cout << "\n";

    // Find max and min
    cout << "Max element: " << *max_element(v.begin(), v.end()) << "\n"; // 9
    cout << "Min element: " << *min_element(v.begin(), v.end()) << "\n"; // 1

    // Swap two elements
    swap(v[0], v[1]);
    cout << "After swap first two: ";
    for(int x : v) cout << x << " "; // 1 7 9 2 5
    cout << "\n";

    // Accumulate (sum)
    int sum = accumulate(v.begin(), v.end(), 0);
    cout << "Sum of elements: " << sum << "\n"; // 24

    // Fill container with sequential values using iota
    vector<int> seq(5);
    iota(seq.begin(), seq.end(), 10); // fills 10,11,12,13,14
    cout << "Sequential values: ";
    for(int x : seq) cout << x << " ";
    cout << "\n";

    return 0;
}
