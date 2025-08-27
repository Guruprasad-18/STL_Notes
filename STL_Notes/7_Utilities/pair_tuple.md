# C++ STL Notes

## Utilities - Pair & Tuple

**Definition**  
- **Pair**: A simple container storing **two values** (possibly of different types).  
- **Tuple**: A generalization of pair that can store **multiple values of different types**.  

**When to Use**  
- To **group multiple values** together.  
- Useful in **maps**, returning multiple values from a function, or storing heterogeneous data.  

**Key Points**  
- Access elements using `.first` and `.second` for `pair`.  
- Access tuple elements using `get<index>(tuple)` or structured bindings (`auto [a,b,c]`).  
- Can be **nested** for complex data.  

**Common Functions**  
- `make_pair(a, b)` → creates a pair  
- `tie(a, b, c)` → unpack a tuple  
- `get<i>(tuple)` → access ith element  
- `tuple_size<T>::value` → get number of elements  

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Pair example
    pair<int, string> p1 = make_pair(1, "Apple");
    cout << "Pair: " << p1.first << ", " << p1.second << "\n"; // 1, Apple

    // Vector of pairs
    vector<pair<int, string>> vp = {{2,"Banana"}, {3,"Cherry"}};
    cout << "Vector of pairs:\n";
    for(auto &p : vp) cout << p.first << " -> " << p.second << "\n";

    // Tuple example
    tuple<int, string, double> t1 = make_tuple(10, "Orange", 3.14);
    cout << "Tuple: " << get<0>(t1) << ", " << get<1>(t1) << ", " << get<2>(t1) << "\n";

    // Structured bindings (C++17)
    auto [a, b, c] = t1;
    cout << "Structured bindings: " << a << ", " << b << ", " << c << "\n";

    // Tie for unpacking
    int x; string y; double z;
    tie(x, y, z) = t1;
    cout << "Using tie: " << x << ", " << y << ", " << z << "\n";

    return 0;
}
