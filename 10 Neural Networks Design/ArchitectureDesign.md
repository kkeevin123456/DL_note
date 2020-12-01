![Image](ArchitectureDesign1.jpg)
因為今天想將原本用很深的 Neuron network 表達的 function 改成用 比較淺的 Neuron Network 表達的話，需要的 hidden unit 是 deep NN 的 exponential 倍

---
![Image](ArchitectureDesign2.jpg)
優點 : Deep NNs 的 hidden units 個數比較少，會比較好 train

舉例 : 
[[HiddenNeuron#absolute value rectification]]
此例中不管 z 很大或者很小，都是對應到相同的 a ，其實就是在做 folding
當我們用 shallow NN 描述 unfolding 的函數時，會有 exponential 倍的 linear piece

---
![Image](ArchitectureDesign3.jpg)
assumption : 我們採用 deep model 的話，等於是用更多簡單的 function 來表達我們的 function
上述假設成立的情況 : 
1. representation learning 如果是由簡單的 factor 組成，像是辨識人臉，人臉 => 五官組成 => 簡單的線條組成 ，此例 performance 不錯
2. 從程式角度來想，中間可能會有一些 pointer 之類的暫存的 output 像是一些暫存的 hidden units，像是 NLP 語言裡面，結尾可能 depends on 開頭、下一句 depends on 上一句