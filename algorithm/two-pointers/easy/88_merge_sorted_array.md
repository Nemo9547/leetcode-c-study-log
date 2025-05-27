# Merge Sorted Array

- Category : Array
- Level : Easy
- Algorithm : Two Pointers
- Leetcode Link : [LeetCode](https://leetcode.com/problems/Merge-Sorted-Array/description/)

## Note

- 題目要求in-place寫法,nums1有足夠空間容納nums2,所以可以原地合併.
- 用Two Pointers將兩組資料從尾端開始做比較,並把較大的值放到尾端新的index.
- 時間複雜度O(m+n), O(1)

## Code

```c
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {       
        int start1 = m - 1, start2 = n - 1, new_index = nums1.size() - 1;
        while(start1 > -1 && start2 > -1) {
            if(nums1[start1] > nums2[start2]) {
                nums1[new_index] = nums1[start1];
                --start1;
            }
            else {
                nums1[new_index] = nums2[start2];
                --start2;
            }
            --new_index;
        }
        
        //如果是start1 >= 0可以不用理,本來就已經排序好
        while(start2 > -1) {
            nums1[new_index] = nums2[start2];
            --start2;
            --new_index;
        }
    }
};
