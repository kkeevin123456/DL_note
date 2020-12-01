![[CNN34.jpg]]
$a_2^{(1)}$ 只會去 detect 一小個範圍的 neuron
* 右圖裡面為甚麼說這樣是一個 group 呢 ? 因為兩條紅色其實是 tied 再一起的一個 weight ，所以看起來有六條，實際上只有三條
* 可以看做是 $a_2^{(1)}$  $a_3^{(1)}$ 用掃過去的方式來 detect 相同的 pattern  
* zero-padding : 在 input 的 boundary 上面跟下面加 0 這樣 $a_0^{(1)}$ 的 #(weight) 就會跟其他人一樣，但因為 0 乘任何 weight 都是 0 所以通常不畫出來 

---
![[CNN35.jpg]]
* 上面公式的意思是要去 detect k個 neurons 再加上一個 bias
* 不同 activation per group 是指在那個 group 所在的位置上面有沒有 detect 到那個 pattern

---
# 延伸到 2D
![[CNN1.jpg]]
* filter : 看 k 個 neurons 的 weights
* kernel 是一個 K$*$K 的 filter

(D 維的 input) * (K 個 wight 掃過去) 還是 D 維的 output

---
# Why Called Convolution
![[CNN2.jpg]]
由於可能有誤差，所以我們可以多 query 幾次之後，把他們加總起來，這個式子在數學上稱為 y(t) 是 x() 和 w() 的 convolution

![[CNN3.jpg]]
二維的話，考慮他們做 u, v 的變動
* commutative : 換向
x 跟 w 可以互換