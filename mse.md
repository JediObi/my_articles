## **MSE**

variance and expectation

$$Var(X) = E(X-E(X))^2=E(X^2-2XE(X)+[E(X)]^2)$$
$$=E(X^2)-E(2XE(X))+E([E(X)]^2)$$
$$=E(X^2)-2E(X)E(X)+E(E(X)E(X))$$
$$=E(X^2)-2[E(X)]^2+[E(X)]^2$$
$$=E(X^2)-[E(X)]^2$$

constant

E(C)=C

$$Var(C) = E(C-E(C))^2=E(C-C)^2=E(0)^2=0$$




使用mse评估误差：不同的训练集训练得到不同的模型，每次训练的模型在一个指定的样本（x,y）上预测，就会得到一组离散的预测结果。

因为只选了一个样本，它的标签y是测量值，f(x)是真实的线性关系，而在此处就是一个确定的值（E(fx)=fx），所以有如下推导

$$y=f(x) + \epsilon$$

$$\hat y= \hat f(x)$$
$$E(y-\hat y)^2=E(y^2-2y\hat y+\hat y^2)=E(y^2)-E(2y\hat y)+E(\hat y^2)
$$
$$=E\{[f(x)+\epsilon]^2\}-2E(y)E(\hat y)+E\{\hat f(x)^2\}$$ (2)
$$$$
$$E\{[f(x)+\epsilon]^2\}=E\{f(x)^2\}+2E\{f(x)\epsilon\}+E(\epsilon^2)$$
$$=Var\{f(x)\}+\{E[f(x)]\}^2+Var(\epsilon)+\{E(\epsilon)\}^2$$
$$=0+\{f(x)\}^2+\epsilon^2+0=\{f(x)\}^2+\epsilon^2$$
$$$$
$$2E(y)E(\hat y)=2E\{f(x)+\epsilon\}E\{\hat f(x)\}$$
$$=2f(x)E\{\hat f(x)\}$$
$$$$
$$E\{\hat f(x)^2\}=Var\{\hat f(x)\}+\{E[f(x)]\}^2$$
$$$$
$$(2)=\epsilon^2+\{f(x)\}^2-2f(x)E\{\hat f(x)\}+\{E[f(x)]\}^2+Var\{\hat f(x)\}$$
$$=\epsilon^2+\{f(x)-E[\hat f(x)]\}^2+Var\{\hat f(x)\}$$

所以每次训练的模型对一个样本预测的误差构成有三部分：

(1) 系统误差 

$$\epsilon^2$$<br>

(2) bias------偏差，每次训练过获得的多个线性关系预测的结果的均值和真实线性关系的差的平方，它代表预测结果偏离真实的程度，即准确度

$$bias = \{f(x)-E[\hat f(x)]\}^2$$<br>

(3) variance-------方差，每次训练获得的多个线性关系预测结果的方差，它代表预测结果的离散程度，即稳定性

$$variance = Var\{\hat f(x)\}$$
