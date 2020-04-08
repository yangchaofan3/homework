首先，对movielens_small数据进行测试集和训练集的二八分割，然后先libfm对train和test格式转换，使用sgd学习，指定学习率0.01

> ![sgd](https://github.com/yangchaofan3/homework/blob/master/L7/libfm.PNG)

得到预测结果输出

![sgd_result](https://github.com/yangchaofan3/homework/blob/master/L7/movielens_out.PNG)

可以看到，虽然libfm在训练集上下降效果表现较好，但测试集上下降效果不明显，存在过拟合现象，说明特征较少时libfm适用性一般

![sgd_verbose](https://github.com/yangchaofan3/homework/blob/master/L7/verbose.PNG)

