# Linear Search vs Binary Search in Data Structures and Algorithms (DSA)



## 1. Linear Search

### **Definition:**
**Linear Search**, also known as **Sequential Search**, checks each element of the list one by one until the desired element is found or the list ends.

### **Algorithm:**
1. Start from the first element of the array.
2. Compare the current element with the target value.
3. If it matches, return the index.
4. If no match is found till the end, return -1 (not found).

### **Example:**
```python
arr = [3, 5, 2, 9, 7]
key = 9
for i in range(len(arr)):
    if arr[i] == key:
        print(f"Element found at index {i}")
        break
```

### **Characteristics:**
- **Time Complexity:** `O(n)` (worst case)
- **Space Complexity:** `O(1)`
- **Data Requirement:** Works on **both sorted and unsorted arrays**
- **Implementation:** Very simple
- **Efficiency:** Inefficient for large datasets
- **Use Cases:** Small datasets, unsorted data, memory not a constraint

**💡 Key Info:** Linear Search is **simple but slow** for large datasets. Best when dataset is unsorted or small.

---

## 2. Binary Search

### **Definition:**
**Binary Search** works on **sorted arrays**. It repeatedly divides the search interval in half and eliminates the half that cannot contain the target.

### **Algorithm:**
1. Initialize `low = 0` and `high = n-1`.
2. While `low <= high`:
   - Compute `mid = (low + high) // 2`
   - If `arr[mid] == key`, return `mid`
   - If `arr[mid] < key`, set `low = mid + 1`
   - If `arr[mid] > key`, set `high = mid - 1`
3. If `low > high`, element is not found.

### **Example:**
```python
arr = [2, 3, 5, 7, 9]
key = 7
low, high = 0, len(arr)-1
while low <= high:
    mid = (low + high) // 2
    if arr[mid] == key:
        print(f"Element found at index {mid}")
        break
    elif arr[mid] < key:
        low = mid + 1
    else:
        high = mid - 1
```

### **Characteristics:**
- **Time Complexity:** `O(log n)`
- **Space Complexity:** `O(1)` iterative / `O(log n)` recursive
- **Data Requirement:** Only works on **sorted arrays**
- **Implementation:** Slightly more complex
- **Efficiency:** Very efficient for large datasets
- **Use Cases:** Large datasets, sorted data, high-performance requirement

**💡 Key Info:** Binary Search is **fast and efficient**, but requires the dataset to be sorted.

---

## 3. Comparison Table
| Feature | Linear Search | Binary Search |
|---------|---------------|---------------|
| **Time Complexity (Worst Case)** | O(n) | O(log n) |
| **Best Case** | O(1) | O(1) |
| **Space Complexity** | O(1) | O(1) iterative / O(log n) recursive |
| **Data Requirement** | Any array | Sorted array |
| **Implementation** | Simple | Moderate |
| **Efficiency** | Low for large data | High for large data |
| **Use Cases** | Small/unsorted data | Large/sorted data |

---

## 4. Visual Representation

**Linear Search:**
```
Index: 0 1 2 3 4
Array: 3 5 2 9 7
Key: 9
Search Path: -> -> -> -> Found
```

**Binary Search:**
```
Array: [2, 3, 5, 7, 9]
low=0, high=4
mid=2 -> 5 < 7 -> low=3
mid=3 -> 7 == 7 -> Found
```

---

## 5. Interview Questions & Answers

**Q1: When would you prefer Linear Search over Binary Search?**
**A:** When the dataset is **unsorted** or **small**. Linear Search does not require sorting.

**Q2: Can Binary Search work on an unsorted array?**
**A:** No, Binary Search requires the array to be **sorted**.

**Q3: What is the time complexity of Linear Search and Binary Search?**
**A:** Linear Search: O(n), Binary Search: O(log n)

**Q4: Which search algorithm is more efficient for large datasets?**
**A:** Binary Search, because it reduces the search space by half each iteration.

**Q5: Can Binary Search be implemented recursively?**
**A:** Yes, Binary Search can be implemented both iteratively and recursively.

---

## 6. Key Takeaways
- **Linear Search:** Simple, works on any array, inefficient for large datasets.
- **Binary Search:** Fast, requires sorted arrays, highly efficient for large datasets.
- **Choice:** Depends on **data size, sortedness, and performance requirements**.

---



**✨ Highlighted Points:** Linear = Simple & Unsorted; Binary = Fast & Sorted; Complexity = O(n) vs O(log n); Interview Q&A included.

