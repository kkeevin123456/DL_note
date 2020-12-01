![[RNN (20).jpg]]
通常 t 會比深度還要深
* 兩個 a 或 兩個 $\delta$ 有 Long-Term Dependency 是指 i 跟 j  差很多

Long-Term dependency 會造成 optimization 上的某些問題 (e.g. Exploding/Vanishing)/

---
![[RNN (21).jpg]]
只要 $j-i$ is large 那 $\lambda$ 要嘛很大要嘛很小，沒有中間值

---
![[RNN (22).jpg]]
因為 $\lambda$ 要嘛很大要嘛很小，所以或產生懸崖，當 learning 跟 gradient 都很大的時候 (在崖壁上面) 就會導致跨出很大步往回走，然後又再慢慢走回來，浪費時間

---
![[RNN (23).jpg]]
Nesterov Momentum : 如果發現下一步會踏到懸崖，就讓他減速

---
![[RNN (24).jpg]]
Gradient Clipping : 把 gradient 設一個上限 (max)，只要他超過那個數字，就把他設成 max 的值就好

---
![[RNN (25).jpg]]
爬上懸崖後要注意的事情
* 上面的特性跟下面可能不一樣
* 所以用 $\lambda$ 來控制要記得前面多少次的 gradient，藉由 reduce  $\lambda$ 來減少下面造成的影響