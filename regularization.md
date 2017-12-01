## **Regularization**

正则化可以解决过拟合。



![图片](./variance_bias.jpg "图1")

Variance measures the consistency (or variability) of the model prediction for a particular sample instance if we would retrain the model multiple times, for example, on different subsets of the training dataset. We can say that the model is sensitive to the randomness in the training data. In contrast, bias measures how far off the predictions are from the correct values in general if we rebuild the model multiple times on different training datasets; bias is the measure of the systematic error that is not due to randomness.

variance衡量模型对同一个样本预测多次的结果的离散程度（一致性）。举个例子，把一个训练集分成若干子集，每次使用一个子集训练重建模型，每个模型对指定样本预测结果，variance就是这些预测结果的离散程度。

模型复杂度会影响拟合性能。
太复杂会导致过拟合。
太简单会导致欠拟合。



variance：方差，用来表示数据的离散程度。在书上有如上一段，这段是说使用同一个训练集的不同子集训练模型（就像是mini-batch），那么每次训练的结果可能就是不同的模型，每次预测的结果也就各不相同。

那么variance和bias是怎么关联上模型复杂度的呢？

为什么太复杂导致过拟合？
复杂的模型有更多参数，在训练时能捕捉到更多的模式，因此许多不值得关注的特征也会被捕捉到，这些无关特征会影响结果的输出。在多次训练之后，模型对训练集拟合度非常高，但是泛化性很差，因为它捕捉了太多训练集里的无关特征。

为什么复杂度或者拟合伴随着variance,bias?

得这么解释
训练集数据包含特征X和标签y。
训练处的模型可以预测得到结果_y， 训练过程构建了损失函数用于评估模型的好坏（E(y-_y)^2，mse根据预测误差来评估）。
但是标签y是测量结果， _y是预测结果。测量存在误差，系统存在误差，它俩都不是真实值。
一个大前提是，的确存在一个理想的真实的线性关系f(x),但是由于样本有限，我们无法得到它。像平面直角坐标系的(x,y)，如果是一条直线，那么这样的f(x)很好建立，但模型通常都不是。
但是测量出的标签y和真实值f(x)存在一个关系 y = f(x)+ξ
因此均方误差公式就能变形

$$E(y- \hat y)^2=E(\ f(x) \ + \ \epsilon \ -\ \hat y)^2$$
$$=E(\ (\ f(x) \ + \ \epsilon \ )^2 \ + \ \hat y^2 \ - 2(\ f(x) \ + \ \epsilon \ )\hat y)$$
$$=E()$$
