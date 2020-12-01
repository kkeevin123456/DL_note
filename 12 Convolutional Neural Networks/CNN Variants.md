![[CNN15.jpg]]
padding : 填充，有填充的話就是外面多一層虛擬的
stride : 掃的時候一次跳幾格
dilation : 擴張，pixel 跳幾格

---
![[CNN16.jpg]]
不同的 activation map 可以接到同一個 pooling 裡面，不同 filter 可能 detect 不同的旋轉角度，因為只要某一個角度被其中一個 filter 抓到，就可以 detect

---
![[CNN17.jpg]]
將 channel group 起來，像這邊分成兩組，一組 map 到一組，所以新的 channel 就只會看到一半的，可以減少 pattern

---
![[CNN18.jpg]]
左邊 : filter size 固定，但出來的 activation size 不固定
中間 : pooling filter size 不固定，但出來的 activation size 固定
右邊 [[FCNs]] : 不一定要 reshape 可以重頭到尾都是 convolutional network，e.g. 先做 1000 個 filter ，detect 完後再做 pooling，會有 1000 個 object ()

---
![[CNN19.jpg]]
Terminology : 術語
左邊在一些文獻中比較常用