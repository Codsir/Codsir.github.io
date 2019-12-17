## Article Read: Algorithms for Non-negative Matrix Factorization

### Introduction And Background

​	矩阵分解(**Non-negative Matrix Factorization**, 简称**NMF**)是无监督学习的一种算法，利用线性代数的矩阵运算将矩阵**V**分解为**W**和**H**, 分解后的矩阵更容易研究，这个问题是不可解析解的吗，所以一般采用近似算法[^1]；NMF在很多领域都有应用，如计算机视觉(computer vision), 文本分类(document clustering), 语言建模(language modeling), 语音处理(speech processing)等[^2]. 

![](/imgs/NMF.png)

### Main Idea

​	这篇文章分析了非负矩阵分解(NMF)的两种迭代算法，第一种算法可最小化最小均方误差，第二种算法最小化相互熵，也就是_Kullback-Leibler divergence_; 在分别引入一个辅助函数后作者证明了两种算法的收敛性，辅助函数类似于证明**EM**(Expectation Maximization)算法的收敛性时引入的辅助函数。 两种算法可以理解为对角化的变维梯度下降法，而变维参数通过优化选择以保证算法收敛性。

​	文章主要是两个算法的提出和证明，而在证明过程中并没有使用太多的矩阵表示和运算，而我发现有些地方可以用矩阵表示以简化证明过程；文章比较简洁，我对文章直接略过的地方进行了补充。这篇文章是矩阵分解方面经典的文章。

### Here It Is







### Implement

- [Chih-Jen Lin](http://www.csie.ntu.edu.tw/~cjlin/nmf/)
- [MATLAB-nnmf](http://cn.mathworks.com/help/stats/nnmf.html)

### The Article

[Lee D D, Seung H S.  Algorithms for non-negative matrix factorization[C]//Advances in neural information processing systems. 2001: 556-562.](http://web.cs.ucla.edu/~yzsun/classes/2014Spring_CS7280/Papers/Clustering/NNF_lee01algorithms.pdf)

### References

[^1]: [ Wikipedia: Non-negative Matrix Factorization](https://en.wikipedia.org/wiki/Non-negative_matrix_factorization)
[^2]: [Sra S, Dhillon I S. Generalized nonnegative matrix approximations with Bregman divergences[C]//Advances in neural information processing systems. 2006: 283-290. ](http://papers.nips.cc/paper/2757-generalized-nonnegative-matrix-approximations-with-bregman-divergences.pdf)



