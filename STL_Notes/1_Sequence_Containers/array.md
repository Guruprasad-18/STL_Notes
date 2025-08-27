# C++ STL Notes

## Array

**Definition**  
`std::array` is a fixed-size sequence container available in C++11 and above. Unlike a normal array, it comes with built-in member functions (like `size()`, `fill()`, `at()`, etc.) while still storing data in contiguous memory.

**When to Use**  
- When size is known at compile time.  
- When you need the safety and utility functions of STL but without dynamic resizing.  

**Key Points**  
- Fixed size (cannot grow/shrink).  
- Contiguous memory storage.  
- Faster than `vector` when size is constant.  
- Supports STL algorithms and range-based loops.  

**Common Functions**  
`size()`, `at()`, `front()`, `back()`, `fill()`, `swap()`.

---

### Example Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Creating and initializing an array
    array<int, 5> arr = {1, 2, 3, 4, 5};

    // Accessing elements
    cout << "First element: " << arr.front() << "\n";   // 1
    cout << "Last element: " << arr.back() << "\n";     // 5
    cout << "Element at index 2: " << arr[2] << "\n";   // 3
    cout << "Element at index 3 (safe): " << arr.at(3) << "\n"; // 4

    // Modifying elements
    arr[1] = 10;   // arr = [1, 10, 3, 4, 5]

    // Iterating through array
    cout << "Array elements: ";
    for (int x : arr) cout << x << " ";  // Output: 1 10 3 4 5
    cout << "\n";

    // Filling array with a value
    arr.fill(7);   // arr = [7, 7, 7, 7, 7]

    // Swapping with another array
    array<int, 5> arr2 = {9, 8, 6, 4, 2};
    arr.swap(arr2);  // arr = [9, 8, 6, 4, 2], arr2 = [7, 7, 7, 7, 7]

    // Size of array
    cout << "Size: " << arr.size() << "\n";

    return 0;
}
