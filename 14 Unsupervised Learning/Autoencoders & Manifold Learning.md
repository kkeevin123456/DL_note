![[ul (13).jpg]]
* 藍色: encoder
* 紅色: decoder

---
![[ul (14).jpg]]
* 不用做 uppooling 了，也就是不用去存原本的位置，因為兩邊不是對稱的，可以改成做 upsampling 也就是圖形變大後空出來的那格 左邊乘 0.5，右邊乘 0.5 加起來。
* 因為 weight 要重新 learn，所以可以把 deconvolution 改成 convolution


---
![[ul (15).jpg]]


---
![[ul (16).jpg]]
![[ul (17).jpg]]


---
![[ul (18).jpg]]
* c 代表的是 manifold 上的一個座標，只會記得 x 有變化的地方

---
![[ul (19).jpg]]


---
![[ul (20).jpg]]


---
![[ul (21).jpg]]
* 給了一個 c 如何找出 manifold 上面的 tangent vector: 對他做 SVD 得到前幾大的 eigenvector 就是 tangent vector

---
![[ul (22).jpg]]