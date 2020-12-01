![[CNN4.jpg]]
將 2D convolution 變成 3D convolution 的方式
* 2D filter 可以沿著 W, H, channel 的方向掃描	  (X)
* 3D filter 來掃，只是 channel 的維度一次看全部 (O) 因為人類一次是看 RGB 不會分開看 *(仍然稱為 2D convolution 因為可以動的維度是 2D)*

---
![[CNN5.jpg]]
用 C 個 filter 來掃，會得到 C 個 activation map (每個都是 2D 的 matrix) ， 將這些 matrix 沿著 channel 疊起來，當成下一層 channel 的厚度

	下一層 dectect 一個 pattern 就如同要 see through 上一層 detect 的那些 pattern

---
![[CNN6.jpg]]

	detect 上一層同一個位置的 pattern 就可以 detect 下一層同個位置的 pattern
	
像是上一層 detect 眼睛嘴巴鼻子，下一層就可以 dectect 人臉

---
![[CNN7.jpg]]
* receptive field : 在 image 裡面會 activate 這個 neuron 的那些 pixels


		深層看得 image 範圍比較大

---
![[CNN8.jpg]]
