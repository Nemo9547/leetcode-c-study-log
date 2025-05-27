# Gas Station

- 題目連結：[LeetCode](https://leetcode.com/problems/Gas-Station/description/)
- 難度：Medium（官方標 Medium，但部分人認為接近 Hard）
- 類別：Greedy
- 是否熟悉：✅ 是

## 解法筆記

Greedy 方法經典題。

- 雖然難度是 Medium，但沒想到好的寫法也很容易卡關或有 bug。
- 以前大學程式課有出過，重點在於用兩個變數去分別累加兩個狀態：

1. `prefix_sum`：累加「中途不夠油」失敗時的缺口
2. `curr_sum`：累加「能走下去」時的剩餘油量，並記錄 `start_index`

如果 `curr_sum + prefix_sum >= 0`，則可以從 `start_index` 出發；否則無解。
