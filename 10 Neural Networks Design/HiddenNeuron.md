![Image](HiddenNeuron1.jpg)
如果是用 Sigmoid  hidden unit 的話，會有 Vanishing Gradient Problem

---
用 Sigmoid hidden unit 的壞處
![Image](HiddenNeuron2.jpg)
Sigmoid 函數假設是 logistic，他的微分會變成下面那個山丘狀的函數，他每個值都小於 1 ，所以當我們做 backward 時，一直乘一個小於一的數會導致 $\delta_j$ 接近 0 從而導致 Gradient 很小，所以每步都跨不大

---
用 ReLU 的好處
![Image](HiddenNeuron3.jpg)
在用 backward path 計算 $\delta_j$ 時，因為 $act^{'}(z^{(k)})$ 只會是 1 或 0 所以就不會有 vanishing gradients 類似 filter out 的動作
當 z 是 0 會隨機選，因為 floating points 裡面 0 不見得就是真的 0

---
![Image](HiddenNeuron4.jpg)
因為它可以切成兩段來看，每一段都是直線，所以雖然我們可以調整 $\sigma(.)$ 但是 $ReLU^{''}(.)$ 都是 0
cons : $\delta_j=0$ weight 不會 update

---
![Image](HiddenNeuron5.jpg)
解決方式 : 乘上一個 $\alpha$ 使得 ReLU 不會是0
[Parametric ReLU](https://medium.com/@danqing/a-practical-guide-to-relu-b83ca804f1f7) 自己去 learned $\alpha$
* [Advanced Activation LeakyReLU](https://keras-cn.readthedocs.io/en/latest/layers/advanced_activation_layer/)
##### absolute value rectification

---
![Image](HiddenNeuron6.jpg)
用 Maxout Units 來實現可 learning 的 piecewise linear
因為兩邊的 z 取大的交叉點下面虛線部分會被忽略

---
![Image](HiddenNeuron7.jpg)
catastrophic forgetting : 後面的 example 可能會蓋掉前面的 example
因為輸掉的就變成 0 所以可以避免這個問題

---
![Image](HiddenNeuron8.jpg)
因為需要 learning 的 z 變多了，所以需要更多 data，如果手邊沒有足夠多的 data 就需要做 regularization