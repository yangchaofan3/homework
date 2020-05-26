分别尝试DIN先train1取小样本训练后直test2测试、xgboost在train1小样本训练test2测试、xgboost在train1全样本训练test2测试，提交结果的得分情况由后往前如下：

> ![tianchi](https://github.com/yangchaofan3/homework/blob/master/L11/tianchi.PNG)

同时在excel中对DIN和xgboost的预测结果降序排列

>**DIN**
>
>![din](https://github.com/yangchaofan3/homework/blob/master/L11/din.PNG)
>
>**XGBOOST**
>
>![xgboost](https://github.com/yangchaofan3/homework/blob/master/L11/din.PNG)
>
>可以看到，din的预测概率结果明显太小，xgboost相对正常，猜测是由于使用了抽样的方式，且原数据集样本标签不均衡导致深度神经网络模型过拟合，希望进一步在DIN用全量数据集尝试但受到设备运算能力的限制，打算在colab上用GPU跑但数据集太大翻墙上传有点慢。。。后面上传完再尝试，同时尝试在小样本时欠采样抽取平衡标签的效果。





