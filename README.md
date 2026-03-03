# 🔍 Binary Search (Recursive) - Java

## 📌 Problem
Given a sorted array of integers `nums` and a target value `target`, return the index of the target if it exists.  
If the target does not exist, return `-1`.

---

## 🚀 Approach

Binary Search works on **sorted arrays**.

Steps:
1. Find the middle element.
2. If middle element equals target → return index.
3. If target is greater → search right half.
4. If target is smaller → search left half.
5. If `low > high` → element not found.

This implementation uses **recursion**.

---

## 💻 Code

```java
class Solution {
    
    public int binarySearch(int[] arr, int target, int lo, int hi) {
        if (lo > hi) return -1;
        
        int mid = lo + (hi - lo) / 2;
        
        if (arr[mid] == target)
            return mid;
        else if (arr[mid] < target)
            return binarySearch(arr, target, mid + 1, hi);
        else
            return binarySearch(arr, target, lo, mid - 1);
    }
    
    public int search(int[] nums, int target) {
        return binarySearch(nums, target, 0, nums.length - 1);
    }
}
