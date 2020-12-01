FCNs : 全部都是 convolutional network，最後那邊其實就是去 detect 1000 個 object，所以可以直接對應到 class 裡面，class 存的就是，在這個圖片裡面看到這個 object 的機率 

Note: 特別適合 single object 比如在圖片裡面找貓

但如果要 predict 是不是沙灘，可能有很多東西 (背景，前景) 要處理，就不太適合 FCNs