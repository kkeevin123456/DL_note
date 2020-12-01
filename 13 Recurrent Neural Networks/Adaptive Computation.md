adaptive: 適應性
![[RNN (42).jpg]]
有些時候可能 prediction 比較難，要 process 比較多次

---
![[RNN (43).jpg]]
這幾個 step 會根據 $\sigma$ (halting neuron) 來決定要不要加在一起，上面會有一個 budget = 1 去控制 $\sigma$ 總和，用完後面的 step 就都不會加進來了

---
![[RNN (44).jpg]]
ponder: 思考
用越少的 step 越好


---
![[RNN (45).jpg]]


----
![[RNN (46).jpg]]
在句子跟句子間，ponder time 越多

---
![[RNN (47).jpg]]


---
![[RNN (48).jpg]]
會先學習一些簡單的 pattern 之後再慢慢去學比較難的 (像是比較長的單字)

----
![[RNN (49).jpg]]
很重要的一點是要學習代名詞
比如 it 是代表甚麼之類的