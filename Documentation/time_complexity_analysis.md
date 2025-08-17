
# 🔍 Sorting Algorithm Analysis: Bubble Sort vs Selection Sort vs Quick Sort



---

## 📌 1. Bubble Sort
Bubble Sort is the simplest sorting algorithm, often taught as an introduction to sorting.  
It repeatedly **swaps adjacent elements** if they are in the wrong order.

### ⚙️ Working Principle:
- Compare each adjacent pair.
- Swap if out of order.
- Repeat until the array is sorted.

### ⏳ Time Complexity:
- **Best Case (Sorted Array):** O(n) → Optimized version checks if swaps occurred.  
- **Average Case:** O(n²)  
- **Worst Case (Reverse Sorted):** O(n²)  
- **Space Complexity:** O(1) (in-place)  

✅ **Pros:** Easy to implement.  
❌ **Cons:** Very slow for large datasets.

---

## 📌 2. Selection Sort
Selection Sort improves slightly by reducing swaps.  
It repeatedly **selects the smallest element** and places it at the correct position.

### ⚙️ Working Principle:
- Find the **minimum element** in the unsorted part.  
- Swap with the first unsorted element.  
- Repeat until the entire array is sorted.

### ⏳ Time Complexity:
- **Best Case:** O(n²)  
- **Average Case:** O(n²)  
- **Worst Case:** O(n²)  
- **Space Complexity:** O(1) (in-place)  

✅ **Pros:** Performs fewer swaps than Bubble Sort.  
❌ **Cons:** Still quadratic; not efficient for large data.

---

## 📌 3. Quick Sort
Quick Sort is a **divide-and-conquer** algorithm and one of the fastest comparison-based sorts.

### ⚙️ Working Principle:
- Choose a **pivot element**.  
- Partition array into two halves:  
  - Elements **less than pivot**.  
  - Elements **greater than pivot**.  
- Recursively apply Quick Sort on partitions.

### ⏳ Time Complexity:
- **Best Case:** O(n log n) (balanced partition)  
- **Average Case:** O(n log n)  
- **Worst Case:** O(n²) (when pivot is always smallest/largest, e.g., sorted array without optimization)  
- **Space Complexity:** O(log n) (due to recursion stack)  

✅ **Pros:** Very fast in practice; widely used in libraries.  
❌ **Cons:** Worst-case O(n²), but can be avoided using **randomized pivot**.

---

## ⚖️ 4. Comparison Table

| Algorithm      | Best Case | Average Case | Worst Case | Space Complexity | Stability |
|----------------|-----------|--------------|-------------|------------------|-----------|
| 🔵 Bubble Sort | O(n)      | O(n²)        | O(n²)       | O(1)             | ✅ Stable |
| 🟢 Selection Sort | O(n²)  | O(n²)        | O(n²)       | O(1)             | ❌ Not Stable |
| 🔴 Quick Sort  | O(n log n)| O(n log n)   | O(n²)       | O(log n)         | ❌ Not Stable (but can be modified) |

---

## 🧑‍💻 5. Interview Tips
- **Bubble Sort**: Rarely used, but asked for basics.  
- **Selection Sort**: Important to compare with Bubble Sort.  
- **Quick Sort**: Common in interviews; understand **partition logic** & **time complexity derivation**.

---

## 🎯 6. Key Takeaways
- For **learning basics**, Bubble & Selection Sort are useful.  
- For **real-world use**, Quick Sort (or Merge Sort) is preferred.  
- **Optimization:** Always choose a **random or median pivot** in Quick Sort to avoid worst-case.

---

✨ **In summary:**  
- Bubble Sort → Simple but slow.  
- Selection Sort → Slightly better but still slow.  
- Quick Sort → Fastest in practice, widely used.

---

📌 *Prepared for DSA Interview & Placement Preparation*
