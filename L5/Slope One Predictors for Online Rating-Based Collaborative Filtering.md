#### Slope One Predictors for Online Rating-Based Collaborative Filtering

*Author： Daniel Lemire ; Anna Maclachlan*

***Abstract***

> SlopeOne算法是一种基于模型的协同过滤算法，以*f(x) = x+b*为基本思想对用户和item之间的评分回归分析，然后根据已有评分预测未知评分，该算法具有容易实现、查询效率以及精确度高的特点，文章基于EachMovie和Movielens数据集进行训练并得到了和基于内存的低效协同过滤模型相比有竞争力的结果。

***Introduction***

> 作者期望提供的CF模型具有的特点：**容易实施和维护，方便实时更新，省时，输入简单，准确合理**
>
> **SlopeOne**的原理是基于用户A对商品I,J的评分，预测同样对I评分的用户B可能会对J的评分，采用差值求解。算法主要贡献在于模型能够达到和基于内存的协同过滤模型相似精度结果的同时更容易承担CF工作（占用内存更少）

***Related Work***

> 基于内存的协同过滤模型的优缺点包括精确率高但基于采集数据的合理性以及数据量有最低要求，可扩展性差，对稀疏矩阵的敏感性；基于算法的协同过滤模型包括基于线性算法，人工智能中的贝叶斯模型、潜类别和神经网络，聚类。前者实时得到结果但查询速度慢，后者需要线下训练但结果查询速度快。最后确定文章只使用简单但效果也好的*f(x) = x+b*

***几种 CF方案***

>1. *Per User Average*：即用户评分均值表示用户其他未评分项
>
>2. *Bias From Mean*：平均分加上整个用户训练集中其他用户对j的评分j的偏差均值
>
>3. *Adjusted Cosine Item Based* ：用余弦修正偏差求权重和，引入回归协差系数α和β减少误差
>
>4. 提供Pearson Scheme 作为基于内存模型的代表
>
>   > 3.4 *基本Slope One 模型*
>   >
>   > ​	![slope one](https://github.com/yangchaofan3/homework/blob/master/L5/slope-one.PNG)
>   >
>   > ​	模型的实现不依赖于用户对单个商品如何评分，而是依赖于用户的平均分和到底对哪些商品评了分
>
>   > 3.5 *Weighted Slope One 模型*
>   >
>   > ![weighted slop one](https://github.com/yangchaofan3/homework/blob/master/L5/weighted-slope-one.PNG)
>   >
>   > 基本模型3.4基础上考虑了评分样本数量对评分可置信度的权重影响
>
>   > 3.6 *The Bi-Polar Slope One 两极Slope模型*
>   >
>   > ![bipolar weighted slopone](https://github.com/yangchaofan3/homework/blob/master/L5/bipolar-slope-one.PNG)
>   >
>   > 基于3.5模型，按用户所有评分的均值作为threshold把item类型二分为like和dislike，然后在like集内的item评分预测只考虑like集内和其他item的偏差，dislike集同理，使用模型3.5计算
>



***Experimental Results***

用**MAE**评价上述模型在EachMovie和MovieLens数据集中的运用效果，两级Slope One模型表现最好，三种Slope One模型的准确度和Pearson误差不超过0.6%，说明模型虽然简单但效果好。

***个人总结***

>SlopeOne是一种Item-based的算法模型，具有简单、可操作性强以及可拓展性强的优点，核心思想是*f(x) = x+b*，可以根据已有评分计算出未知评分，并对预测的item评分进行推荐，不足在于遇到冷启动问题时需要自己构造评分。
>