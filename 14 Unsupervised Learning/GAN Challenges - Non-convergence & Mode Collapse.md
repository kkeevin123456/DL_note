![[ul (29).jpg]]
* 要求馬鞍的 saddle point (中間那個點) 所以才會有一邊是 max 一邊是 min，**很容易滑掉**

---
![[ul (30).jpg]]
* 不管在哪裡 cut 都只能展現一部份的 data points
* k 太小的話，解 min max 等於 解 max min，會變成全部都攻擊同一個特點，只要 f 沒辦法分辨即可

----
![[ul (31).jpg]]
* minibatch discrimination: 看看帶一段 batch 進去，如果裡面 generate 出來的都是一樣的東西，代表他可能是專攻某個點了
* unrolled gan: 不只是要攻這個版本的 discriminator 還要攻擊上一個版本，上上一個版本之類的