# ISLR

### introduction

In Chapter 3,we discuss ==linear regression==（线性回归）, which can be used to predict wage from this data set. Ideally, we should predict wage in a way that accounts for the ==non-linear==(非线性) relationship between wage and age. 

The Wage data involves predicting a *continuous* or *quantitative* output value. This is often referred to as a ==*regression* problem==(回归问题). However, in certain cases we may instead wish to predict a non-numerical value—that is, a *categorical*(分类的) or *qualitative*(定性的) output. This is known as a ==*classification* problem==(分类问题). 

 *quadratic discriminant analysis model* to the subset of the Smarket data(二次判别分析模型的市场数据子集)

 visualize the data.(数据可视化)

The left-hand panel of Figure 1.4 addresses this problem by representing each of the 64 cell lines using just two numbers, *Z*1 and *Z*2. These are the first two *principal components* of the data, which summarize the 6*,*830 expression measurements for each cell line down to two numbers or *dimensions*. While it is likely that this ==dimension reduction== has resulted in some loss of information, it is now possible to ==visually examine the data for evidence of clustering==. Deciding on the number of ==clusters== is often a difficult problem. 

图1.4的左侧面板通过仅用两个数字Z1和Z2来表示64个细胞系中的每个细胞系，从而解决了这个问题。这是数据的前两个主要组成部分，它将每个细胞系的6,830个表达测量值总结为两个数字或维度。虽然这种==降维==很可能导致了一些信息的丢失，但现在可以==可视化地检查数据以获得聚类的证据==。决定==集群==的数量通常是一个棘手的问题。

*Many statistical learning methods are relevant and useful in a wide* range of academic and non-academic disciplines, beyond just the statistical sciences. We believe that many contemporary statistical learning procedures should, and will, become as widely available and used as is currently the case for classical methods such as linear regression. **As a result, rather than attempting to consider every possible approach (an impossible task), we have concentrated on presenting the methods that we believe are most widely applicable.**

许多统计学习方法在广泛的学术和非学术学科中都是相关和有用的。我们认为，许多当代统计学习程序应该而且将像目前线性回归等经典方法一样广泛可用和使用。因此，**我们并没有试图考虑每一种可能的方法（一项不可能完成的任务），而是集中精力展示我们认为最广泛适用的方法**。

*Statistical learning should not be viewed as a series of black boxes.* No single approach will perform well in all possible applications. Without understanding all of the cogs inside the box, or the interaction between those cogs, it is impossible to select the best box. Hence,**we have attempted to carefully describe the model, intuition, assumptions, and trade-offs behind each of the methods that we consider.**

统计学习不应该被视为一系列的黑盒子。没有一种方法在所有可能的应用中都表现良好。如果不了解盒子里所有的所有齿轮，或者这些齿轮之间的相互作用，就不可能选择最好的盒子。因此，**我们试图仔细描述我们所考虑的每一种方法背后的模型、直觉、假设和交易**。

We will let *p* denote the number of variables that are available for use in making predictions. For example, the Wage data set consists of 11 ==variables==(变量) for 3*,*000 people, so we have *n* = 3*,*000 observations and *p* = 11 variables (such as year, age, race, and more). 

 In Chapter 4 we discuss two of the most important classical classification methods, ==*logistic regression*== and ==*linear discriminant analysis*==.

在第四章中，我们讨论了两种最重要的经典分类方法，==逻辑回归==和==线性判别分析==。

A central problem in all statistical learning situations involves **choosing the best method for a given application**. Hence, in Chapter 5 we introduce ==*cross-validation*== and the *==bootstrap==*, which can be used to estimate the accuracy of a number of different methods in order to choose the best one.

在所有的统计学习情况下的一个中心问题包括为一个给定的应用程序选择最佳的方法。因此，在第5章中，我们介绍了==交叉验证==和==自助法==，它可以用来估计一些不同的方法的准确性，以选择最好的方法。

![image-20240424113535781](C:\Users\27198\AppData\Roaming\Typora\typora-user-images\image-20240424113535781.png)

In essence, statistical learning refers to a set of approaches for ==estimating *f*==. In this chapter we outline some of the key theoretical concepts that arise in estimating *f*, as well as tools for evaluating the estimates obtained.

在本质上，统计学习指的是一套==估计f==的方法。在本章中，我们概述了在估计f时出现的一些关键的理论概念，以及评估所获得的估计数的工具。

*prediction* and *inference*    预测和推断

The focus of this book is on techniques for estimating *f* with the aim of variance ==minimizing the reducible error==. It is important to keep in mind that the irreducible error will always provide an upper bound on the accuracy of our prediction for *Y* . **This bound is almost always unknown in practice**.

这本书的重点是在估计f的技术，目的为==最小化可约误差==。重要的是要记住，不可约误差总是为我们对Y的预测精度提供一个上限。**这个界限在实践中几乎总是未知的**。

#### 箱型图

- *Q*0/4：[[最小值](https://zh.wikipedia.org/wiki/%E6%9C%80%E5%B0%8F%E5%80%BC)](https://zh.wikipedia.org/wiki/最小值)（minimum）
- *Q*1/4：第1[[四分位数](https://zh.wikipedia.org/wiki/%E5%9B%9B%E5%88%86%E4%BD%8D%E6%95%B0)](https://zh.wikipedia.org/wiki/四分位数)（lower quartile）
- *Q*2/4：[[中位数](https://zh.wikipedia.org/wiki/%E4%B8%AD%E4%BD%8D%E6%95%B8)](https://zh.wikipedia.org/wiki/中位數)（第2[[四分位数](https://zh.wikipedia.org/wiki/%E5%9B%9B%E5%88%86%E4%BD%8D%E6%95%B0)](https://zh.wikipedia.org/wiki/[四分位数](https://zh.wikipedia.org/wiki/%E5%9B%9B%E5%88%86%E4%BD%8D%E6%95%B0))、median）
- *Q*3/4：第3[四分位数](https://zh.wikipedia.org/wiki/四分位数)（upper quartile）
- *Q*4/4：[[最大值](https://zh.wikipedia.org/wiki/%E6%9C%80%E5%A4%A7%E5%80%BC)](https://zh.wikipedia.org/wiki/最大值)（maximum）

以第1四分位数（*Q*1/4）和第3四分位数（*Q*３/4）的数值作为箱型的上下限。



![](C:\Users\27198\Downloads\箱ひげ図の具体例.png)

这组数据显示出：

- 下边界=5
- 第1四分位数（Q1）=7
- 中位数、第2四分位数（median、Q2）=8.5
- 第3四分位数（Q3）=9
- 上边界=10
- 四分位间距（interquartile range，简称IQR）=![{\displaystyle (Q3-Q1)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a73064552e3cf8d693d2ca9b2e4f184429c47c67)=2 （即ΔQ)

当有数值与第1与第3四分位数的范围差距1.5×IQR以上时，该值为离群值（outlier）。

数值位于范围外1.5×IQR到3×IQR范围的数值，称作适度离群值（mild outlier）。
数值位于范围外3×IQR以上的数值，称作极端离群值（extreme outlier）。

因此该图中的离群值有：

- 适度离群值（mild outlier） = 3.5
- 极端离群值（extreme outlier） = 0.5

![](D:\Desktop\markdowm\建模.img\a9bfba199d7142539d51bf50ea79a36e.png)

但箱形图也有他的局限性，比如：不能精确地衡量数据分布的偏态和尾重程度；对于批量比较大的数据，反映的信息更加模糊以及用中位数代表总体评价水平有一定的局限性。

优点：

1.直观地观察到异常值，如果数据存在离群点，即位于上下边缘区域之外，以圆点的形式表示
2.当箱型图很短时，意味着很多数据多集中分布在很小的范围内
3.当箱型图很长时，意味着数据分布比较离散，数据间的差异比较大
4.当中位数接近底部时，说明大部分的数据值比较小
5.当中位数接近顶部时，说明大部分的数据值比较大
6.中位数所处的高低位置能反映数据的偏斜程度
7.如果上下虚线比较长，说明上下四分位数之外的数据变化比较大，整体数据的方差和标准偏差也比较大
8.箱型图的上下边缘并非最大值或最小值



### Chapter 1. Statistical Learning

In other words, our goal is to develop **an accurate model** that can be used to predict sales on the basis of the three media budgets.