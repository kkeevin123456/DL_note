![[ul (9).jpg]]
* CBOW: input "the cat sat" 這三個字，經過相同的 weight 之後，存入 hidden layer，之後再 predict 出 "on"
* Skip Gram: 跟上面相反 input "on"
* Latent representation: 某個字 encode 後的 h (hidden layer) 的值

sematic: 語義的

	因為 latent representation 會被保留下來，所以我們可以對此作運算，像是我們想知道 (男生 -> 女生) = (國王 -> ??) ，則我們可以用 (男生的 latent representation) - (女生的 latent representation) + (國王的 latent representation) 剛好會跟 queen 的 latent representation 蠻接近的

原本需要人去給他 label 像是 on 跟 above 是同義字，但她現在自己就可以根據 latent representation 學到，這兩個其實意思很像

---
![[ul (10).jpg]]
* 原因是因為，既然我們原本的 vector 可以代表 word 的 sematic，那還會 predict 不好的原因就可能是沒有考慮到 word 之間的順序跟結構，所以多一個 段落，句子的結構來一起決定，就可能會更好

---
![[ul (11).jpg]]
* 這個 RNN 是不斷去看上面跟左邊的 pixel，去 predict 下一個 pixel

---
![[ul (12).jpg]]
* 可以去預測接下來的 frame