## **Regularization**

正则化可以解决过拟合。



![图片](./variance_bias.jpg "图1")

Variance measures the consistency (or variability) of the model prediction for a particular sample instance if we would retrain the model multiple times, for example, on different subsets of the training dataset. We can say that the model is sensitive to the randomness in the training data. In contrast, bias measures how far off the predictions are from the correct values in general if we rebuild the model multiple times on different training datasets; bias is the measure of the systematic error that is not due to randomness.


加入l2正则项，一个直观的解释是，模型在测试集上表现糟糕，可以体现为在一个小区间上波动的厉害，那么导数值就这些区间上很大，既原函数的系数很大。也就有必要减小权重，而加入l2正则项，更新权重的幅度明显减小，防止权重过大。那么就会有效抑制过拟合。

