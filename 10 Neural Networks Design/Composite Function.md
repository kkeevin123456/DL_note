a<sup>(k)</sup> =  act<sup>(k)</sup> ( W<sup>(k)T</sup> a<sup>(k-1)</sup>  + b<sup>(k)</sup> )
* act<sup>(i)</sup>( <sup>.</sup> ) : **R** -> **R** is an *[[activation function]]* applied elementwisely
* 先對</sup> a<sup>(k-1)</sup> 做一個線性轉換後，再用 nonlinear 的 act 針對 W<sup>(k)T</sup> a<sup>(k-1)</sup>  + b<sup>(k)</sup> 這個 vector 裡面所有元素做轉換

Shorthand : a<sup>(k)</sup> =  act<sup>(k)</sup> ( W<sup>(k)T</sup> a<sup>(k-1)</sup>  )
* 第一層 a<sub>0</sub><sup>(k-1)</sup> = 1 並且 bias term b<sup>(k)</sup> 融合進 W<sup>(k)</sup> 裡面