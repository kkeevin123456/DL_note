![Image](NeuronDesign5.jpg)
Maximum likelihood principle : $$arg \max_{\Theta} log P(\mathbb{X}|\Theta)$$

想要去 minimizing output $\hat p$ s.t. 使他跟上面的 P 有最小的 [cross entropy](Shannon.pdf)

* [機器/深度學習: 基礎介紹-損失函數](https://medium.com/@chih.sheng.huang821/%E6%A9%9F%E5%99%A8-%E6%B7%B1%E5%BA%A6%E5%AD%B8%E7%BF%92-%E5%9F%BA%E7%A4%8E%E4%BB%8B%E7%B4%B9-%E6%90%8D%E5%A4%B1%E5%87%BD%E6%95%B8-loss-function-2dcac5ebb6cb)
* [lost function document](https://ml-cheatsheet.readthedocs.io/en/latest/loss_functions.html)

---
![Image](NeuronDesign4.jpg)
從白努力分布 (像擲銅板) 來看
從上圖可以得知，如果 $\delta^{(L)}$ 要接近 0 只有兩種情況
1. $y^{(n)} = 1$ and $z^{(L)}$ is large positive
2. $y^{(n)} = 0$ and $z^{(L)}$ is small negative

---
![Image](NeuronDesign3.jpg)
從 Categorical 分布 (像擲骰子) 來看
要 output $\rho$ 這個 vector (骰子的機率分布) 所以可以拿他當成最後一層的 a 
只需要前面 k-1 維即可，因為 k 維可以透過前面生成出來
Note : 當 k=2 就會 degenerate 到前面 Bernoulli case

---
![Image](NeuronDesign2.jpg)
如果今天 y 就是我要的那個 class j ，對 j 偏微 可以得到 $\hat{\rho_j}-1$ 又 $\hat{\rho_j}$ 最大是1，所以只有當 $\hat{\rho_j}$ 是我們要的性質 $\delta$ 才會接近 0
另外，對於其他 class 而言，$\hat{\rho_j}$ 是越小越好

---
![Image](NeuronDesign1.jpg)
Neuron network 不一定要 output distribution 也可以 output mean，我們可以用 linear 的方式來表達