# C++ STL Notes

## Stack

**Definition**  
`std::stack` is a container adapter that implements a **LIFO (Last In First Out)** data structure.  
Elements are inserted and removed from the **top** only.

**When to Use**  
- When you need to process elements in reverse order of insertion.  
- For problems like expression evaluation, backtracking, undo functionality.

**Key Points**  
- LIFO behavior (last in, first out).  
- Cannot iterate directly like vector or list.  
- Insertion: `push()`, Removal: `pop()`, Access top: `top()`.  

**Common Functions**  
`push()`, `pop()`, `top()`, `empty()`, `size()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating a stack
    stack<int> st;

    // Adding elements
    st.push(10);  // stack = [10]
    st.push(20);  // stack = [10, 20]
    st.push(30);  // stack = [10, 20, 30]

    // Accessing top element
    cout << "Top element: " << st.top() << "\n"; // 30

    // Removing element
    st.pop(); // removes 30 → stack = [10, 20]
    cout << "After pop, top element: " << st.top() << "\n"; // 20

    // Checking size and emptiness
    cout << "Stack size: " << st.size() << "\n";        // 2
    cout << "Is stack empty? " << (st.empty() ? "Yes" : "No") << "\n"; // No

    // Removing all elements
    while (!st.empty()) {
        cout << st.top() << " ";
        st.pop();
    }
    cout << "\n";

    return 0;
}
