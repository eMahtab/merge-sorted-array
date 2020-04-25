# Merge Sorted Array
## https://leetcode.com/problems/merge-sorted-array

Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

**Note:**
1. The number of elements initialized in nums1 and nums2 are m and n respectively.
2. You may assume that nums1 has enough space (size that is greater or equal to m + n) to hold additional elements from nums2.

Example:

Input:
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6],       n = 3

Output: [1,2,2,3,5,6]

# Implementation :
```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int c1 = 0, c2 = 0;
        int index = 0;
        int[] clone = nums1.clone();
        
        while(c1 < m && c2 < n) {
            if(nums2[c2] <= clone[c1]) {
                nums1[index++] = nums2[c2++];
            } else {
                nums1[index++] = clone[c1++];
            }
        }
        
        while(c2 < n) {
            nums1[index++] = nums2[c2++];
        }
        
        while(c1 < m) {
            nums1[index++] = clone[c1++];
        }
            
    }
}
```
