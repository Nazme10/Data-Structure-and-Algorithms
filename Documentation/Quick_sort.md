
# ⚡ Quick Sort Algorithm - Complete Documentation

## 📌 Introduction
**Quick Sort** is one of the most efficient and widely used **sorting algorithms** in **Data Structures and Algorithms (DSA)**.  
It follows the **Divide and Conquer** strategy and works by selecting a **pivot element**, partitioning the array around the pivot, and recursively sorting the subarrays.

🔑 Key Highlights:
- Extremely **fast** for large datasets 🚀  
- **In-place** sorting (requires little extra memory) 📦  
- Widely asked in **interviews** and **placements** 🎯  
- Foundation for understanding advanced algorithms  

---

## ⚙️ Working Principle (Divide & Conquer)
The Quick Sort algorithm works in three main steps:

1. **Divide**: Choose a **pivot** element from the array.  
2. **Partition**: Rearrange elements so that:  
   - All elements **smaller than pivot** → left side  
   - All elements **greater than pivot** → right side  
3. **Conquer**: Recursively apply Quick Sort on the left and right subarrays.  

👉 The process continues until subarrays have size 1 (which are inherently sorted).  

---

## 🔄 Example Walkthrough

Array: `[10, 80, 30, 90, 40, 50, 70]`  
Pivot = `70`  

- Partition Step:  
  `[10, 30, 40, 50] 70 [80, 90]`  

Now recursively sort left `[10, 30, 40, 50]` and right `[80, 90]`  

- Final Sorted Array: `[10, 30, 40, 50, 70, 80, 90]` ✅  

---

## 💡 Pseudocode

```text
procedure quickSort(A, low, high)
    if low < high then
        pivotIndex = partition(A, low, high)
        quickSort(A, low, pivotIndex - 1)
        quickSort(A, pivotIndex + 1, high)
    end if
end procedure

procedure partition(A, low, high)
    pivot = A[high]
    i = low - 1
    for j = low to high-1 do
        if A[j] <= pivot then
            i = i + 1
            swap(A[i], A[j])
        end if
    end for
    swap(A[i+1], A[high])
    return i+1
end procedure
```

---

## 🖥️ Implementation

### Python 🐍
```python
def partition(arr, low, high):
    pivot = arr[high]
    i = low - 1
    for j in range(low, high):
        if arr[j] <= pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
    arr[i+1], arr[high] = arr[high], arr[i+1]
    return i+1

def quick_sort(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quick_sort(arr, low, pi-1)
        quick_sort(arr, pi+1, high)

arr = [10, 80, 30, 90, 40, 50, 70]
quick_sort(arr, 0, len(arr)-1)
print("Sorted Array:", arr)
```

### C++ 💻
```cpp
#include <iostream>
using namespace std;

int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = (low - 1);
    for (int j = low; j < high; j++) {
        if (arr[j] <= pivot) {
            i++;
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i+1], arr[high]);
    return (i + 1);
}

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    int arr[] = {10, 80, 30, 90, 40, 50, 70};
    int n = sizeof(arr) / sizeof(arr[0]);
    quickSort(arr, 0, n - 1);
    cout << "Sorted Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

---

## 🎯 Variants of Quick Sort
1. **Lomuto Partition Scheme** → Simple, uses last element as pivot.  
2. **Hoare Partition Scheme** → More efficient, uses two pointers.  
3. **Randomized Quick Sort** → Random pivot reduces worst-case probability.  
4. **Three-Way Quick Sort** → Handles duplicates efficiently.  

---

## ⏱️ Time Complexity Analysis

### Best Case (Balanced Partition)
- Each time pivot divides array into equal halves.  
- Recurrence: T(n) = 2T(n/2) + O(n) → **O(n log n)**  

### Worst Case (Unbalanced Partition)
- Happens when pivot is always smallest/largest element (e.g., sorted/reverse sorted array).  
- Recurrence: T(n) = T(n-1) + O(n) → **O(n²)**  

### Average Case (Random Order)
- On average, partitions are reasonably balanced.  
- Expected time = **O(n log n)**  

### Space Complexity
- Recursive stack depth = O(log n) (best case)  
- O(n) (worst case if recursion is skewed)  

### Stability
- ❌ Quick Sort is **not stable** (relative order of equal elements may change).  

---

## 📊 Complexity Table

| Algorithm      | Best Case   | Worst Case | Average Case | Space | Stable |
|----------------|------------|------------|--------------|-------|--------|
| Quick Sort     | O(n log n) | O(n²)      | O(n log n)   | O(log n) | ❌ No |
| Merge Sort     | O(n log n) | O(n log n) | O(n log n)   | O(n)   | ✅ Yes |
| Heap Sort      | O(n log n) | O(n log n) | O(n log n)   | O(1)   | ❌ No |
| Selection Sort | O(n²)      | O(n²)      | O(n²)        | O(1)   | ❌ No |
| Insertion Sort | O(n)       | O(n²)      | O(n²)        | O(1)   | ✅ Yes |

---

## 🎓 When to Use Quick Sort?
- Large datasets 🚀  
- Situations where **average performance** is more important than worst case  
- When **in-place sorting** is required  
- When recursion is not a problem  

---

## ⚠️ Disadvantages
- Worst case is **O(n²)** if pivot selection is poor  
- Not stable  
- Recursion overhead for very large datasets  

---

## 💡 Key Takeaways for Interviews
- Quick Sort is **fastest in practice** (average O(n log n))  
- Based on **Divide and Conquer** principle  
- Be ready to **explain partitioning logic** (Lomuto vs Hoare)  
- Understand **best, average, worst case complexities** in depth  
- Compare with Merge Sort and Heap Sort during interviews  

---

## 🏁 Conclusion
Quick Sort is a **powerful and efficient sorting algorithm** widely used in practice and interviews.  
Although its worst case is **O(n²)**, with randomized pivoting or three-way partitioning, it achieves **O(n log n)** almost always.  

👉 **Interview Tip**: Be prepared to write Quick Sort code quickly, explain partitioning, and compare it with Merge Sort.  

---

✨ **Pro Tip**: If asked in placements, always highlight **Quick Sort vs Merge Sort** differences and discuss pivot strategies to avoid worst-case performance.
