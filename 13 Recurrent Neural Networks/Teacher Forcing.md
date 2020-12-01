![[RNN (31).jpg]]
很難 parallelism
因為 
1. a 跟 a 在 forward pass 的時候有 dependency
2. $\delta$ 跟 $\delta$  在 backward pass 的時候有 dependency

---
![[RNN (32).jpg]]
* 在 training time 時，因為前面的 label 是給定的 (也就是最上面那個 neuron) 所以就可以憑行化計算
* 但是在 test time 還是要 sequencial 的執行

---
![[RNN (33).jpg]]
vanilla RNN 比較能 simulate Turing machines 因為他的 U 會比 Output-recurrent RNN 的 U (可能只是一個 1 維的矩陣) 來的大，所以更能幫助 $a^{(1,t)}$ 更好的去 summarize $x^{(t-1)}$