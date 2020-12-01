### Training an NN
![Image](training1.jpg)
### Example : Binary Classification
![Image](training2.jpg)
因為是 Bernoulli 分佈所以 $$-logP(\mathcal{y}^{(i)}|\mathcal{x}^{(i)};\Theta) = -log[(a^{(L)})^{y^{(i)}}(1-a^{(L)})^{1-y^{(i)}}]$$
又 $a^{(L)} = \sigma (z^{(L)})$ 所以
$$-log[(a^{(L)})^{y^{(i)}}(1-a^{(L)})^{1-y^{(i)}}] = -log[\sigma (z^{(L)})^{y^{(i)}}(1-\sigma (z^{(L)}))^{1-y^{(i)}}]$$
* 當 $y^{(i)}$ = 1 時 $\sigma (z^{(L)})$ 要最大
* 當 $y^{(i)}$ = 0 時 $\sigma (z^{(L)})$ 要最小

所以可以畫簡成 $$-log[\sigma ((2y^{(i)}-1)z^{(L)})]$$

![[Optimization Algorithm]]
![[Back Propagation]]
