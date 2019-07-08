---
title: Logistic Regression

date: 2019-07-08 23:50:11.000000000 +09:00

tags: ml-dl, logistic regression
---

### 1. 回归 & logistic回归

logistic回归：**二值型输出分类器**：
 * 回归：用一条直线对一些数据点进行拟合的过程；
 * logistic回归：根据现有数据对**分类边界线**建立回归公式，从而进行分类。
>“回归”（最佳拟合）--> 寻找**最佳拟合参数集**（使用**最优化算法**）；


### 2. 优缺点

* 优点：简单易实现，计算代价不高；
* 缺点：**拟合能力不行**（易欠拟合），分类精度可能不高；
>适用数据类型：数值型 & 标称型数据；

### 3. logistic回归实现
1. 在每个特征上乘以一个回归系数，然后相加；
2. 将总和代入sigmoid函数中，得到一个0~1之间的数值；
3. 大于0.5被归入1类，小于0.5被归于0类。
> logistic回归可以被看成是一种**概率估计**。

### 4. loss取binary cross entropy
或从概率生成模型的角度看logistic回归，构造最大似然函数。

### 5. 梯度上升法
1. 要找到某函数的最大值，最好的方式是沿着该函数的梯度的方向探寻；
2. 梯度存在，函数在待计算的点上有定义，且可微；
3. 一直迭代更新参数集，直至达到某个停止条件为止：
    * **迭代次数**达到某个指定的值；
    * 算法达到某个可以被允许的**误差范围内**。
> 梯度上升法：用来**求最大值**；
>
> 梯度下降法：用来求最小值。

### 6. 随机梯度上升
* 一次只用一个样本来更新回归参数；
* 可以在新样本到来时对分类器进行**增量式更新**，是一种**在线学习算法**；
> 但具有一些小的周期性波动。

### 7. 使优化算法快速收敛 & 减小随机梯度上升时的来回波动
* 使lr随着迭代次数不断变小: lr = 4/(1.0 + epoch_id + step_id) + 0.01；
* **random sampling**（随机取样）: 每次随机从列表中选出一个值，然后从列表中删掉该值，再进行下一次迭代。

### 8. 缺失值（Nan）处理
1. 补均值：
    * 可用特征的均值；
    * 相似样本的均值;
2. 用特殊值来标记：如-1；
3. 扔掉样本；
4. 用其它ML方法预测均值。