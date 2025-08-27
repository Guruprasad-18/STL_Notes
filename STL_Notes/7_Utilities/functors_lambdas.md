# C++ STL Notes

## Utilities - Functors & Lambdas

**Definition**  
- **Functor (Function Object)**: An object that can be **called like a function** by overloading the `operator()`.  
- **Lambda Function**: An **inline anonymous function** defined using `[](){}` syntax, often used for short operations.  

**When to Use**  
- For **custom comparison** in sorting, sets, maps, or priority queues.  
- To **pass functions** to STL algorithms like `sort`, `for_each`, `count_if`.  
- For **inline operations without creating a separate function**.

**Key Points**  
- Functors can maintain **state** (store variables).  
- Lambdas are **lightweight**, convenient, and often **used inline**.  
- Both can be passed to STL algorithms expecting callable objects.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

// Functor example
struct MultiplyBy {
    int factor;
    MultiplyBy(int f) : factor(f) {}
    int operator()(int x) { return x * factor; }
};

int main() {
    vector<int> v = {1, 2, 3, 4, 5};

    // Using a functor
    MultiplyBy mult2(2); // multiply by 2
    cout << "Using functor: ";
    for (int x : v) cout << mult2(x) << " "; // 2 4 6 8 10
    cout << "\n";

    // Using a lambda function
    cout << "Using lambda: ";
    for_each(v.begin(), v.end(), [](int x){ cout << x*x << " "; }); // 1 4 9 16 25
    cout << "\n";

    // Lambda for custom sort
    vector<int> v2 = {5, 2, 4, 1, 3};
    sort(v2.begin(), v2.end(), [](int a, int b){ return a > b; }); // descending
    cout << "Sorted descending using lambda: ";
    for(int x : v2) cout << x << " "; // 5 4 3 2 1
    cout << "\n";

    return 0;
}
