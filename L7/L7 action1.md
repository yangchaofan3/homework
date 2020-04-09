首先，对movielens_sample数据进行测试集和训练集的二八分割，然后先libfm对train和test格式转换，第一次采用默认方式:

> ![normal](https://github.com/yangchaofan3/homework/blob/master/L7/libfm_normal.PNG)

得到预测结果输出:

![normal_result](https://github.com/yangchaofan3/homework/blob/master/L7/libfm_normal_out.PNG)

迭代过程输出结果：

![verbose_normal](https://github.com/yangchaofan3/homework/blob/master/L7/verbose_normal.PNG)



接下来指定sgd对数据集训练，指定学习率0.01：

> ![sgd](https://github.com/yangchaofan3/homework/blob/master/L7/libfm_sgd.PNG)

得到预测结果输出:

![sgd_result](https://github.com/yangchaofan3/homework/blob/master/L7/libfm_sgd_out.PNG)

迭代过程输出结果：

![verbose_sgd](https://github.com/yangchaofan3/homework/blob/master/L7/verbose_sgd.PNG)

可以看到，虽然libfm在训练集上下降效果表现更好，但测试集上sgd的下降表现比默认的mcmc泛化能力弱了一半，说明sgd的方式训练在特征较少时存在过拟合现象，适用性一般。



