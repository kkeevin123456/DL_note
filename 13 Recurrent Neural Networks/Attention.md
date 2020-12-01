![[RNN (34).jpg]]
因為 a 的 size 有限，所以我們可能會面臨選擇，到底要花多一點心思在 girl 還是 bear 如果主要 focus 在 girl 則 bear 的表現可能會不好

---
![[RNN (35).jpg]]
* input recurrence : 簡化 a 的工作，讓他變成是只要 support 現在這個 prediction 跟下面那個 representation a 即可 (e.g. $a^{(t-1)}$ 只要 support prediction 'a' 還有下一個 representation $a^{(t)}$ )
* 寫一個 model 去讓每個 a pay attention on explicity pattern

---
![[RNN (36).jpg]]
* 用 CNN 的最後一層 output layer output 出的結果來當成 attention 的東西，因為 CNN 可以 extract "location independent feature"  然後形成一個灰階的圖，放進來
* e.g. 要放 0.9 的 attention 在人臉，0.1 的 attention 在籃球
* 把這個 attention vector 跟 image inner product 起來，可以得到一個類似 focus 的 image 
* 所以 X 的 size 可以 reduce，減少 weight

---
![[RNN (37).jpg]]
* a 和 x 去得到一個 match score 然後在代一個 softmax function (做 normalization 且 高的更高，低得更低) 
* 求 match score i.e. z 的方式，簡單一點可以用內積，複雜一點可以代一個小小的 neuron network 
* p, q, r 都是 share 的，所以只要 learn 一組即可

---
![[RNN (38).jpg]]
* 白色的部分是 pay attention 的部分，所以 a little girl 是小女生那邊比較亮 etc，錯也可以知道錯在哪，像是 bed 跟 sofa
* 把 vector b 乘上那個圖