---
{"dg-publish":true,"permalink":"/计算机相关/机器学习/概念碎片/基础概念/监督学习vs非监督学习/","dgPassFrontmatter":true,"created":"2025-04-24T22:46:22.349+08:00","updated":"2025-05-09T02:17:10.381+08:00"}
---

# supervised learning
supervised learning：x到y的映射，模型基于正确的答案进行学习，因为训练样本中存在答案，因此称为监督学习

监督学习可以分为两类任务——分类任务classifier与回归任务regression
分类任务即需要模型在获得输入之后输入类别，例如经典的鸢尾花分类问题
回归任务是需要模型在无穷多个数字当中预测准确的数字，比如说一些数值预测任务，例如预测第二天的温度，这种就是回归任务。

回归任务和分类任务实际上是预测的东西不同：连续数值/离散有限集合
# unsupervised learing
非监督学习unsupervised learning的数据没有标签label
因此非监督学习往往用于寻找数据集中的某种pattern
例如某些clustering聚类
anomaly detection异常检测
dimensionality reduction降维

无监督算法的奖励函数从何而来，如何控制无监督算法尽可能寻找有意义的pattern而不是仅关注某些明显的pattern