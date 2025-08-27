# C++ STL Notes

## Priority Queue

**Definition**  
`std::priority_queue` is a container adapter that provides **constant-time access to the largest (by default) element**.  
It is typically implemented as a max-heap. You can also create a min-heap using a comparator.

**When to Use**  
- When you need to repeatedly access the **largest/smallest element**.  
- For problems like scheduling, Dijkstra's algorithm, or any greedy algorithm.

**Key Points**  
- By default, it is a **max-heap**.  
- Does **not support iteration** like vector or deque.  
- Insertion: O(log n), Access max/min: O(1), Removal: O(log n).  
- Can be customized to a min-heap using `greater<int>`.

**Common Functions**  
`push()`, `pop()`, `top()`, `empty()`, `size()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Max-heap (default)
    priority_queue<int> pq;
    pq.push(10);
    pq.push(5);
    pq.push(20);

    cout << "Max element: " << pq.top() << "\n"; // 20

    pq.pop(); // removes 20
    cout << "After pop, max element: " << pq.top() << "\n"; // 10

    // Min-heap
    priority_queue<int, vector<int>, greater<int>> minpq;
    minpq.push(10);
    minpq.push(5);
    minpq.push(20);

    cout << "Min element: " << minpq.top() << "\n"; // 5
    minpq.pop();
    cout << "After pop, min element: " << minpq.top() << "\n"; // 10

    // Iterating is not directly supported; elements accessed via top/pop
    cout << "Removing all elements from max-heap: ";
    while (!pq.empty()) {
        cout << pq.top() << " ";
        pq.pop();
    }
    cout << "\n";

    return 0;
}
