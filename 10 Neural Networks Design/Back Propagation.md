![[backpropagation4.jpg]]
由於 SGD 需要進行大量偏微分計算，所以採用 Back Propagation 方式 & GPU，從後面計算回來，可以有效提升計算速度
---
![[backpropagation5.jpg]]
求最後目標的第二個 terms
當 k=1 時 $z_j^{(1)}$ 等於 $x_i^{(n)}$ 乘上 weight 的和
當 k>1 時 $z_j^{(k)}$ 等於 $a_i^{(k-1)}$ 乘上 weight 的和
---
![[backpropagation3.jpg]]
求最後目標的第一個 terms，需要從後面求回來
例子 : softplus 偏微完會變成 logistic 
---
![[backpropagation2.jpg]]
算式第二行
* a 會影響下一層所有的 z 所以套 chain rule 結果如圖

算式第三行
* 帶定義即可

算式第四行
* 藍色對 $a_j$ 偏微得到

---
![[backpropagation1.jpg]]
要算 $\delta_j^{(k)}$ 可以從後面的 $\delta_j^{(k+)}$ 得到，所以我們可以用有點類似 neuron network 的方式來做

---
![[backpropalgorithm1.jpg]]
![[backpropalgorithm2.jpg]]
想要用 GPU 加速的話，要嘛把寬度設大，要嘛把 batch size 設大，深度不會影響，因為不是平行的