***针对MQ2008数据集中的Fold1，使用RankNet,  ListNet, LambdaMart三种模型进行排序学习，并对比三种模型的NDCG@10结果***     

使用LambdaMart训练结果

>![Lambdamart](https://github.com/yangchaofan3/homework/blob/master/L10/Lambdamart.PNG)
>
>![Lambdamart结果](https://github.com/yangchaofan3/homework/blob/master/L10/Lambdamart结果.PNG)

使用RankNet训练结果

>![Ranknet](https://github.com/yangchaofan3/homework/blob/master/L10/Ranknet.PNG)
>
>![Ranknet结果](https://github.com/yangchaofan3/homework/blob/master/L10/Ranknet结果.PNG)

使用ListNet训练结果

> ![ListNet](https://github.com/yangchaofan3/homework/blob/master/L10/ListNet.PNG)
>
> ![ListNet结果](https://github.com/yangchaofan3/homework/blob/master/L10/ListNet结果.PNG)

三种模型效果对比

|    模型    | 训练集NDCG@10结果 | 验证集NDCG@10结果 | 测试集NDCG@8结果 | 迭代次数 |
| :--------: | :---------------: | :---------------: | ---------------- | :------: |
| LambdaMart |      0.5322       |      0.5477       | 0.4858           |   135    |
|  RankNet   |      0.4875       |      0.5227       | 0.4595           |   100    |
|  ListNet   |      0.4807       |      0.5136       | 0.4598           |   1500   |

