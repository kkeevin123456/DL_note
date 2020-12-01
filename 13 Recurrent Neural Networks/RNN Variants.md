![[RNN (5).jpg]]
* many to many (synced) : input and output have correspondence
* many to many (unsynced) : input and output don't have correspondence

---
![[RNN (6).jpg]]
input is image 通常會接一個 CNN 之後才接進來 RNN
output is a make sense sentence

---
![[RNN (7).jpg]]
給一段文章，output 他是不是負評
Razzie : 金酸梅獎

有 best, wins, award 正面的字，但整句話是在反諷

---
![[RNN (8).jpg]]
可以預測下一個字

---
![[RNN (9).jpg]]
可能在賽末點發球失誤跟比賽前失誤 就不一樣

---
![[RNN (10).jpg]]
有點像是前面一路做過來，在對 representation 加東西，然後在 output 的時候再對 representation 減東西一樣，減完 chat 之後，看看還剩下什麼，然後再減掉 bot

---
![[RNN (11).jpg]]
bidirectional RNNs : 新增一層，由右往左連，就可以看未來的來影響現在的

---
![[RNN (12).jpg]]
離現在越遠的 neuron 就越不重要，但不一定會正確

---
![[RNN (13).jpg]]
用 parse tree 來表示的話，就可以讓下面的 node 更有機會接近上面那個