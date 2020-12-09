![[ul (23).jpg]]
* 自己隨便生成一個 c 之後帶入 decoder，也是可以得到不同的 output
* 缺點: 
	1. decode 出來的圖片會**模糊**
	2. 他只是把 data 做 linear conbination 比較沒有創新

---
![[ul (24).jpg]]
* 會模糊的原因: loss function 不好，因為 pixel 多一點少一點 loss 都一樣
* solution: 把 loss function 變成一個 CNN

---
![[ul (25).jpg]]
* $g$ : 不用 encoder 了，直接帶一個 c 然後 decoder -> generator
* Discriminator $f$ : 去偵測 $g$ output 出來的是不是真的
* label: $g$ 生出來的標 False，其他標 True

---
![[ul (26).jpg]]
* $\Theta_g$ : g 生出的 weight
* $\Theta_f$ : f 生出的 weight
* $\rho$ : n 是帶現實的 data，m 是指 g 生出來的

找到一個 generator，他生成的東西是 learn 不起來的


---
![[ul (27).jpg]]
* 一次走幾步之後，把 weight 固定起來，換 learn 另一個
* 因為希望他有一點點 train 而不是 well train，不然會變成整天雞蛋裡挑骨頭，所以 f 一次只能走 k 步 (k 要小一點)

---
![[ul (28).jpg]]
brandon wu: 很難 train