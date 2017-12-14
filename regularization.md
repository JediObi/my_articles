## **Regularization**

在上一节，已经推导出了mse的构成
偏差，方差，系统误差
偏差是真实值和平均预测值的误差
方差是多次预测的方差
系统误差是测量值和真实值的误差

在 Adaline中使用差平方和作为损失函数
在 logistic中使用构建了条件概率的函数，和它的反函数即激活函数。然后构建了单个样本的似然函数，似然函数把分段的激活函数变成了一个函数。然后构建样本集的对数似然，取反就成了新的损失函数，该损失函数取w的偏导就会和Adaline的损失函数求偏导的结果完全一样。

正则化可以解决过拟合。



![图片](./variance_bias.jpg "图1")

Variance measures the consistency (or variability) of the model prediction for a particular sample instance if we would retrain the model multiple times, for example, on different subsets of the training dataset. We can say that the model is sensitive to the randomness in the training data. In contrast, bias measures how far off the predictions are from the correct values in general if we rebuild the model multiple times on different training datasets; bias is the measure of the systematic error that is not due to randomness.

在损失函数里加上bias

$$J(\bold w)=J(\bold w)+\frac {\lambda}{2}||\bold w||^2=J(\bold w)+{\frac {\lambda}{2}}{\sum_{j=1}^m}{w_j^2}$$
$$$$
$$\frac {\lambda}{2}$$ 
正则化系数

那么新的损失函数和mse有什么关系？

$$J(\bold w)=[\sum_{i=1}^n\{-log(\phi(z^{(i)}))+(1-y^{(i)})[-log(\ 1-\phi(z^{(i)})\ )]\}]+{\frac {\lambda}{2}}{\sum_{j=1}^m}{w_j^2}$$

$$MSE=\epsilon^2+\{f(x)-E[\hat f(x)]\}^2+Var[\hat f(x)]$$

J(w)取偏导

$$\Delta w_j= -\eta [\sum_{i=1}^n(y^{(i)}-\phi(z^{(i)}))x^{(i)}+{\lambda}w_j]$$


