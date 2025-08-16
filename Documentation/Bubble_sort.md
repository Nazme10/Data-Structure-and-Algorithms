
# Bubble Sort Algorithm - Detailed Documentation

## Introduction
Bubble Sort is one of the simplest sorting algorithms in Data Structures and Algorithms (DSA). 
It repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. 
The pass through the list is repeated until the list becomes sorted.

Despite being simple and easy to understand, Bubble Sort is **not efficient** for large datasets. 
However, it is commonly asked in coding interviews and placements to test the candidate’s understanding of sorting techniques and complexity analysis.

---

## Working Principle
Bubble Sort works by **repeatedly swapping adjacent elements** if they are in the wrong order.  
This way, larger elements "bubble up" towards the end of the list after every iteration.

### Steps:
1. Start from the first element of the array.
2. Compare the current element with the next element.
3. If the current element is greater than the next element, swap them.
4. Continue this process for each adjacent pair in the array (one full pass).
5. After each pass, the largest element is placed at the end of the unsorted section.
6. Repeat the process for the remaining unsorted portion until no swaps are needed.

---

## Example Walkthrough

Consider the array:  
`[5, 3, 8, 4, 2]`

### Pass 1:
- Compare 5 and 3 → Swap → `[3, 5, 8, 4, 2]`
- Compare 5 and 8 → No swap → `[3, 5, 8, 4, 2]`
- Compare 8 and 4 → Swap → `[3, 5, 4, 8, 2]`
- Compare 8 and 2 → Swap → `[3, 5, 4, 2, 8]`

(Largest element `8` is now at the end)

### Pass 2:
- Compare 3 and 5 → No swap → `[3, 5, 4, 2, 8]`
- Compare 5 and 4 → Swap → `[3, 4, 5, 2, 8]`
- Compare 5 and 2 → Swap → `[3, 4, 2, 5, 8]`

(Largest element `5` is at the 2nd last position)

### Pass 3:
- Compare 3 and 4 → No swap → `[3, 4, 2, 5, 8]`
- Compare 4 and 2 → Swap → `[3, 2, 4, 5, 8]`

### Pass 4:
- Compare 3 and 2 → Swap → `[2, 3, 4, 5, 8]`

Now the array is sorted.

---

## Pseudocode

```text
procedure bubbleSort(A)
    n = length(A)
    repeat
        swapped = false
        for i = 1 to n-1 do
            if A[i] > A[i+1] then
                swap(A[i], A[i+1])
                swapped = true
            end if
        end for
    until not swapped
end procedure
```

---

## Implementation

### Python
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        swapped = False
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        if not swapped:
            break
    return arr

# Example
arr = [5, 3, 8, 4, 2]
print("Sorted Array:", bubble_sort(arr))
```

### C++
```cpp
#include <iostream>
using namespace std;

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        bool swapped = false;
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                swap(arr[j], arr[j+1]);
                swapped = true;
            }
        }
        if (!swapped)
            break;
    }
}

int main() {
    int arr[] = {5, 3, 8, 4, 2};
    int n = sizeof(arr)/sizeof(arr[0]);
    bubbleSort(arr, n);
    cout << "Sorted Array: ";
    for (int i=0; i<n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

---

## Optimizations
1. **Early Stopping**: If no swaps are performed during a pass, the array is already sorted (break out of loop).
2. **Reduced Iterations**: After each pass, the largest element is in its correct position, so reduce inner loop iterations.
3. **Bidirectional Bubble Sort (Cocktail Shaker Sort)**: Instead of only moving largest elements to the end, also move the smallest elements to the beginning.

---

## Time Complexity Analysis

### Best Case (Already Sorted Array)
- Only one pass needed (no swaps).
- **Time Complexity: O(n)**

### Worst Case (Reverse Sorted Array)
- Every element needs to be compared and swapped in each pass.
- Number of comparisons = \[ (n-1) + (n-2) + ... + 1 \] = n(n-1)/2
- **Time Complexity: O(n²)**

### Average Case (Random Array)
- On average, about half the elements are swapped in each pass.
- **Time Complexity: O(n²)**

### Space Complexity
- Bubble Sort is **in-place**.
- **Space Complexity: O(1)**

### Stability
- Bubble Sort is a **stable sorting algorithm**, meaning equal elements retain their relative order.

---

## Comparison with Other Sorting Algorithms

| Algorithm      | Best Case | Worst Case | Average Case | Space | Stability |
|----------------|-----------|------------|--------------|-------|-----------|
| Bubble Sort    | O(n)      | O(n²)      | O(n²)        | O(1)  | Stable    |
| Insertion Sort | O(n)      | O(n²)      | O(n²)        | O(1)  | Stable    |
| Selection Sort | O(n²)     | O(n²)      | O(n²)        | O(1)  | Not Stable|
| Merge Sort     | O(n log n)| O(n log n) | O(n log n)   | O(n)  | Stable    |
| Quick Sort     | O(n log n)| O(n²)      | O(n log n)   | O(log n)| Not Stable |

---

## When to Use Bubble Sort
- When the input size is **very small**.
- When the array is **almost sorted** (best case O(n)).
- For teaching **basic concepts** of sorting in interviews or academics.

---

## Disadvantages
- Extremely inefficient for large datasets.
- Higher number of comparisons and swaps compared to other algorithms.
- Rarely used in real-world applications.

---

## Key Takeaways for Interviews
- Bubble Sort is **easy to implement** but not efficient.
- Know **best, average, worst-case complexities**.
- Understand **stability** and **space complexity**.
- Be ready to **optimize with early stopping**.
- Often asked in interviews to check understanding of **basic sorting principles**.

---

## Conclusion
Bubble Sort is a beginner-friendly sorting algorithm that helps in understanding the basics of sorting. 
While inefficient for large datasets, its simplicity makes it an important concept in DSA and interview preparation.

