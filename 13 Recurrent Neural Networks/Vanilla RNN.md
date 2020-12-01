![[RNN (1).jpg]]
* successive : 連續
* Phonemes : 音位
* utterance : 發音

通常拿到 sequence data 會表達成一個 tensor
t 表示時間

---
![[RNN (2).jpg]]
直的看成是以前的 Neural Network  

---
![[RNN (3).jpg]]
$U^{(k)} 跟 W^{(k)}$ 都是同一個，不會隨著時間改變，只會在個別的 NN 裡面改變

---
![[RNN (4).jpg]]
左右兩張圖是相同的，其實 RNN 裡面需要一個 memory ，要存上一個 $a^{(1, t-1)}$