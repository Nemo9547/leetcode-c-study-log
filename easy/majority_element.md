# Majority Element

- 題目連結：[LeetCode](https://leetcode.com/problems/Majority-Element/description/)
- 難度：Easy
- 類別：Math
- 是否熟悉：✅ 是

## 解法筆記

眾數法則：當選者的票數必定超過半數才可使用。

- 選擇第一個拿到的票先當候選人
- 如果之後開票投給同個人則票數 +1，不同人則 -1
- 若票數 < 0，則更換候選人並把票數改為 1
- 最後開完票看候選人是誰就是答案
