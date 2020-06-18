对比结果

> |   模型   |  得分   |
> | :------: | :-----: |
> |    LR    | 0.69747 |
> | LightGBM | 0.63445 |
> | XGBoost  | 0.61659 |
> | Catboost | 0.60294 |
> | NGBoost  | 0.56722 |
>
> 

可以看到，在离职率预测中模型表现依次排序：LR>LightGBM>XGBoost>Catboost>NGBoost,

同时耗时排序：CatBoost>NGBoost>XGBoost>LightGBM>LR

因此，LR模型在数据集上的整体表现优于决策树模型。

