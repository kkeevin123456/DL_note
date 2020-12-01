![[CNN20.jpg]]
取代全部都是 fully convolution 的方式，應該要去針對一些 locatily pattern 做，所以才會 con, pool 交錯

---
![[CNN21.jpg]]
imagenet : 某 big data

---
![[CNN22.jpg]]
x 軸是 size
y 軸是 accuracy

---
![[CNN23.jpg]]
突破 : ReLU, Dropout, GPU 的先行使用者

---
![[CNN24.jpg]]
突破 : 藉由 filter size 小，但是疊多層 (e.g. 3\*3 疊三層) 取代 filter size 大，因為 k 比較小，所以 learn 的 weight 可以不用那麼多

---
![[CNN25.jpg]]
暴力法去試不同大小的 k
1\*1 convolution

---
![[CNN26.jpg]]
* 原本的做法需要用每個 cubes 去掃 2D 的圖，所以 1 個 cube 去掃需要 W\*H\*(3\*3\*256)，共有 256 個 cubes
* 改良後，前面用 1\*1 的 filters 後面也用 1\*1 的 filters 去包他，可以減少 multiplies operation
* 而且 performance 不會變糟，有時候還會變好，因為 1\*1 的 convolution 是把上一層的 W\*H area 裡面每個 channel see through 看透之後 conbine，才繼續看他跟附近的點的關聯

---
![[CNN27.jpg]]
可以連一個 shortcut 跳過中間兩層，也可以跳過一個 bottleneck layer

原因 : 如果有捷徑，所以 CNN 有新的選擇，如果新加的那層 performance 不好，那就可以走捷徑，可以 skip 掉一些 layers

---
![[CNN28.jpg]]
1 層的變化量不多，所以不見得會 learning 到好的 residual pattern

發現 : 就算他很深 (150幾層) 他實際上還是只有執行 20~30 層而已就夠好了

---
![[CNN29.jpg]]
中間有 dense block 所以像橘色 可以看到前面四層的 patterns (像是看人臉的時候，瞳孔可能不在前一個 pattern ，因為他比較小，所以他在紫色那層，但橘色那層需要這個 patterns)