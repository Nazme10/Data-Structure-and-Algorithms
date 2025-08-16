
# 🌈 Selection Sort Algorithm - Complete Documentation

## 📌 Introduction
**Selection Sort** is a simple, intuitive, and comparison-based sorting algorithm in **Data Structures and Algorithms (DSA)**.  
It works by **repeatedly selecting the minimum element** from the **unsorted portion** of the array and placing it in its correct position in the **sorted portion**.

🔑 Key Points:
- Easy to understand and implement ✨  
- Not efficient for large datasets 🚫  
- Frequently asked in **interviews** and **placement tests** 🎯  

---

## ⚙️ Working Principle
Selection Sort divides the array into two subarrays:
1. **Sorted subarray** → initially empty  
2. **Unsorted subarray** → initially the whole array  

👉 On each iteration:
- Find the **smallest element** in the unsorted subarray.  
- Swap it with the **first unsorted element**.  
- Expand the sorted subarray by one element.  

---

## 🔄 Steps (Algorithm)
1. Start with the first element as the minimum.  
2. Traverse the unsorted part to find the **smallest element**.  
3. Swap it with the first unsorted element.  
4. Move the boundary forward.  
5. Repeat until the entire array is sorted.  

---

## 📝 Example Walkthrough

Consider the array:  
`[64, 25, 12, 22, 11]`

### Pass 1:
- Minimum element = `11`  
- Swap with first element → `[11, 25, 12, 22, 64]`  

### Pass 2:
- Minimum from remaining = `12`  
- Swap with `25` → `[11, 12, 25, 22, 64]`  

### Pass 3:
- Minimum from remaining = `22`  
- Swap with `25` → `[11, 12, 22, 25, 64]`  

### Pass 4:
- Remaining array is already sorted.  

✅ Final Sorted Array = `[11, 12, 22, 25, 64]`  

---

## 💡 Pseudocode

```text
procedure selectionSort(A)
    n = length(A)
    for i = 0 to n-1 do
        minIndex = i
        for j = i+1 to n-1 do
            if A[j] < A[minIndex] then
                minIndex = j
            end if
        end for
        swap(A[minIndex], A[i])
    end for
end procedure
```

---

## 🖥️ Implementations

### Python 🐍
```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr

arr = [64, 25, 12, 22, 11]
print("Sorted Array:", selection_sort(arr))
```

### C++ 💻
```cpp
#include <iostream>
using namespace std;

void selectionSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        int minIndex = i;
        for (int j = i+1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        swap(arr[minIndex], arr[i]);
    }
}

int main() {
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr)/sizeof(arr[0]);
    selectionSort(arr, n);
    cout << "Sorted Array: ";
    for (int i=0; i<n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

---

## 🚀 Optimizations
- **Swap only when necessary**: Unlike Bubble Sort, Selection Sort minimizes swaps.  
- **Track sorted boundaries**: Reduces unnecessary iterations.  
- **Not adaptive**: Even if the array is sorted, Selection Sort still performs all passes.  

---

## ⏱️ Time Complexity Analysis

### Best Case (Already Sorted Array)
- Still finds the minimum each time → **O(n²)**  
- ❌ Not adaptive  

### Worst Case (Reverse Sorted Array)
- Still checks all comparisons → **O(n²)**  

### Average Case (Random Order Array)
- On average, ~n²/2 comparisons → **O(n²)**  

### Space Complexity
- In-place sorting → **O(1)**  

### Stability
- ❌ **Not stable** (swapping may change relative order of equal elements).  

---

## 📊 Complexity Table

| Algorithm        | Best Case | Worst Case | Average Case | Space | Stable |
|------------------|-----------|------------|--------------|-------|--------|
| Selection Sort   | O(n²)     | O(n²)      | O(n²)        | O(1)  | ❌ No |
| Bubble Sort      | O(n)      | O(n²)      | O(n²)        | O(1)  | ✅ Yes |
| Insertion Sort   | O(n)      | O(n²)      | O(n²)        | O(1)  | ✅ Yes |
| Merge Sort       | O(n log n)| O(n log n) | O(n log n)   | O(n)  | ✅ Yes |
| Quick Sort       | O(n log n)| O(n²)      | O(n log n)   | O(log n)| ❌ No |

---

## 🎯 When to Use Selection Sort?
- Small datasets  
- When minimizing **swaps** is more important than minimizing **comparisons**  
- Teaching and interviews for concept building  

---

## ⚠️ Disadvantages
- Poor efficiency on large datasets  
- Always **O(n²)** regardless of input  
- Not stable  

---

## 💡 Key Takeaways for Interviews
- Easy to implement but inefficient 🚀  
- Always **O(n²)** time complexity ⏱️  
- **Not stable**, but **in-place** sorting 🌟  
- Fewer swaps compared to Bubble Sort 🔄  
- Good for **learning basic sorting concepts** 📚  

---

## 🏁 Conclusion
Selection Sort is a **fundamental sorting algorithm** that helps beginners understand sorting mechanics.  
While not suitable for large datasets, it is an important topic for **DSA interviews and placements**.  
Its simplicity, deterministic performance, and fewer swaps make it a good stepping stone toward learning more advanced algorithms like **Merge Sort** and **Quick Sort**.  

---

✨ **Pro Tip for Interviews**: Be ready to compare **Selection Sort vs Bubble Sort vs Insertion Sort**, explain **stability**, and analyze **time complexities** in detail.
