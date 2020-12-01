![[RNN (39).jpg]]
* 紅色是 prediction
* 藍色是 hidden neuron
* 黑色是 input
* 綠色是 attention (partial input)
* $d^{(t-1)}$ 有點像是 query enter 跟 memory 相乘後的到一個 vector 然後再做 softmax 之後得到 $b^{(t)}$
* $e^{(t-1)}$ 會根據 $b^{(t)}$ 去更新 memory ，$\alpha$ 控制要保留多少程度的上一動 memory
*  下一個時間點的 attention 是根據這個 memory 經過 $b^{(t)}$ 得到的

---
![[RNN (40).jpg]]
這個測試 input sequence 跟 output sequence 是一樣的，所以他如果有 learn 到這個現象，那長度變成 120 也不是甚麼問題

---
![[RNN (41).jpg]]
例子: 給不同的 image 使得他可以轉正 (可能要先水平的轉，然後再垂直的轉)
* 每個 neuron 有兩個 input 其中一個是 calling stack，另一個是圖片
* 三個 output 
	1. end: 停止了
	2. key: corresponding to external memory，去查這個表，查到的 function 會變成下個時間的 input function
* 有些在 external memory 裡面的 subroutine 是 predefined 好的，但有些是 **NPI 自己加的**
