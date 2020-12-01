![[RNN (26).jpg]]
* Bounded range in the forward pass 所以比較不會有 exploding gradient 的問題
* dirivative 小於 1 所以也比較不會有 exploding gradient 的問題

但不能避免 vanishing gradient，甚至會在橫向跟縱向都加劇

---
![[RNN (27).jpg]]
1.  IRNN : 如果 $\lambda$ 是 1 就可以避免 exploding / vanishing gradient 了
2.  Krueger 版 IRNN : 在兩個相鄰時間的 a 加一個 norm term ，讓他們不要相差太大

* heuristic : 啟發式

---
![[RNN (28).jpg]]
* 原版的 neuron : 下面是上一層同個時間的 a，左邊是同一層前個時間點的 a 。中間經過一個 sigmiod function 轉換之後得到新的兩個 output a
* 新版的 neuron :  
	 1. 兩個 tanh : 中間的會生成新的 memory cell，經過兩個之後才會生成出新的 a
	 2. 三個 $\sigma$ (看成開關) : 最左邊的 (forget gate) 掌握前一個 memory cell 會不會影像下一個。中間的 (input gate) 控制第一次經過 tanh 轉換的 a 要不要加到下一次裡面。右邊的 (output gate) 要不要 output a 或者只要記得 memory cell 即可

---
![[RNN (29).jpg]]
* 藍色部分永遠都是乘 1 所以並不會 explod 或者 vanish，並且藍色部分的 dirivative 很好算
* 兩個相加才變成新的 gradient 所以可以確保 gradient 不會 vanish 
* U, F, D, W, O 都是 learning 出來的，所以不會存在 long term dependency

---
![[RNN (30).jpg]]
* forget gate for razzie = 0 : 就可以不用管前面紀錄的 mem
* input gate for movie = 0 : 因為這是電影評論，所以 movie 會出現很多次，因此只要看到一次 movie 就好，然後就可以沿用了
* 此外，that 下面是新的子句，所以他可以選擇只記得 memory cell 忘掉前面的 activation ，也就是說，讓下一個 neuron 自己決定他的 gate values 不要被前面的影響