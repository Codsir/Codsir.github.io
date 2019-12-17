## Singular-value decomposition

### Background

### Method

​	矩阵的奇异值分解(SVD): 设矩阵$\bf{A}_{n\times{m}}$，令

$(\bf{A}^T\bf{A})v_i=\lambda_iv_i, $

$u_i = \frac{1}{\sigma_i}\bf{A}v_i, $

$\sigma_i=\sqrt{\lambda_i},  i=1,2,\cdots, p$.

其中$p$为矩阵$\bf{A^TA}$的秩，则有$\bf{A}=\bf{U}\bf{\Sigma}\bf{V}$.

_**proof**_: 

​	$\bf{U}\bf{\Sigma}\bf{V}$

= $\bf{(u_1, u_2, \cdots, u_p)\pmatrix{\sigma_1 & 0 & \cdots & 0\\ 0&\sigma_2& \cdots& 0\\ \vdots& \vdots& \cdots&\vdots \\ 0&0&\cdots&\sigma_p }\pmatrix{v_1^T\\v_2^T\\\vdots \\v_p^T}}$

= $\sum_{i=1}^{p}{\sigma_i\bf{u_iv_i^T}}$

=$\sum_{i=1}^{p}{\frac{1}{\sigma_i}\bf{Av_i}\sigma_i\bf{v_k^T}}$

=$\bf{A}$

 