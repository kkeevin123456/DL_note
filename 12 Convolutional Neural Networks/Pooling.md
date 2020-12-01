![[CNN9.jpg]]
兩種方式來做 max pooling
* 在 filter 裡面挑最大值
* 用 stride 的方式，通常 k*k 的 filter，stride 也是 k

max : pattern 的存在性
Average : 亮度或者對比 (要看那區 pixel 平均的情況)

---
![[CNN10.jpg]]
在 forward 的時候，去記錄當時最大值我們是拿哪一格，unpooling 的時候，將值填回去即可

---
![[CNN11.jpg]]
* invariant : 下面那張圖的 input 向右邊 shift 但是 pooling layer 還有兩格一樣，代表 pooling 後對於 input 的 translation 不那麼 sensitive

---
![[CNN12.jpg]]
因為 CNN 有 invariant 的特性，所以他會覺得下面兩張都是人臉

---
![[CNN13.jpg]]
detect 的方式變成是看某個區域有沒有某些 pattern 如果有就認為她是人臉

像物體如果有多個面向，會轉動，前面沒有尾翼，兩個翅膀，他可能就說是飛機，但轉動之後可能就會多尾翼

---
![[CNN14.jpg]]
1. input 是 256*256 而且有三個 channels
2. 
     * 每個 filter 有 4\*4\*3 個 weight，總共有 16 個 filters => 4\*4\*3\*16 個 weights
	 * 共有 16 個 filters 所以下一層會變成 16 個 channels，寬跟高還是 256\*256 =>  256\*256\*16 個 units
3.  
     * 沒有 weight 因為他直接挑出 max 就好
	 * 寬跟高都縮小 4 倍，所以是 64\*64\*16 個 units
4.  
     * 16 個 channels 所以每個 filter 有 4\*4\*16 個 weight，總共有 32 個 filters => 4\*4\*16\*32 個 weights
	 * 共有 32 個 filters 所以下一層會變成 32 個 channels，寬跟高還是 64\*64 =>  64\*64\*32 個 units


			flatten 會把他拉成長長的，所以就失去了 location info. 不需要有 weight
			Fully connected 假設有 10 個 units 則他就需要 8192\*10 個 weights 