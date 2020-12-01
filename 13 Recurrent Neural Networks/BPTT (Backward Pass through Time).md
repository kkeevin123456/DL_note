![[RNN (14).jpg]]
在代 a 的時候，已經考慮了之前的 x ，所以還是有 recursive 的感覺

---
![[RNN (15).jpg]]
對於 W 方向的偏微跟之前的一樣

---
![[RNN (16).jpg]]
從最一開始的時間往後看的 through time

---
![[RNN (17).jpg]]
a 會影響
1. 深一層的 z
2. 下個時間同一層的 z

根據 chain rule 可以寫成上式

---
![[RNN (18).jpg]]
在 evaluate 時，有點像是從
1. 深往淺走
2. 未來往過去走

---
![[RNN (19).jpg]]
forward pass 只要一條就可以得到 $\delta^{(L,1)}$,  $\delta^{(L,2)}$, $\delta^{(L,3)}$ 