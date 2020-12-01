### 梯度下降法(gradient descent)
[梯度下降法(gradient descent)](https://medium.com/@chih.sheng.huang821/%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E5%9F%BA%E7%A4%8E%E6%95%B8%E5%AD%B8-%E4%BA%8C-%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E6%B3%95-gradient-descent-406e1fd001f)是最佳化理論裡面的一個一階找最佳解的一種方法，主要是希望用梯度下降法找到函數(剛剛舉例的式子)的局部最小值，因為梯度的方向是走向局部最大的方向，所以在梯度下降法中是往梯度的反方向走。

這邊我們先大概說一下梯度， 要算一個函數f(x)的梯度有一個前提，就是這個函數要是任意可微分函數，這也是深度學習為什麼都要找可微分函數出來當激活函數(activation function)。

一維度的純量x的梯度，通常用f'(x)表示。
多維度的向量x的梯度，通常用∇f(x)表示。

	白話一點，一維度的純量x的梯度就是算f(x)對x的微分，多維度的向量x的梯度就是算f(x)對x所有元素的偏微分

### 隨機梯度下降法(Stochastic gradient descent, SGD)

[隨機梯度下降法(Stochastic gradient descent, SGD)](https://medium.com/@chih.sheng.huang821/%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E5%9F%BA%E7%A4%8E%E6%95%B8%E5%AD%B8-%E4%B8%89-%E6%A2%AF%E5%BA%A6%E6%9C%80%E4%BD%B3%E8%A7%A3%E7%9B%B8%E9%97%9C%E7%AE%97%E6%B3%95-gradient-descent-optimization-algorithms-b61ed1478bd7)就是一次跑一個樣本或是小批次(mini-batch)樣本然後算出一次梯度或是小批次梯度的平均後就更新一次，那這個樣本或是小批次的樣本是隨機抽取的，所以才會稱為**隨機**梯度下降法。
