---
{"dg-publish":true,"permalink":"/计算机相关/机器学习/概念碎片/基础概念/误差曲面error surface/","dgPassFrontmatter":true,"created":"2025-05-09T01:01:36.045+08:00","updated":"2025-05-09T02:17:26.275+08:00"}
---

也叫做loss surface（损失曲面）

指的是当讲模型的所有参数看作坐标轴，把模型在这些参数下的损失值看作高度，所形成的一个多维曲面。

通常来说，
- 横轴 → 模型的参数（比如权重 weight、偏置 bias）；
    
- 纵轴 → 损失函数的值（比如 MSE、交叉熵）。

我们优化的目标就是在error surface中寻找最低点，也就是<u>损失最小的参数组合</u>。

一个光滑的error surface容易找到最优解，而一个具有很多[[计算机相关/机器学习/概念碎片/基础概念/鞍点Saddle Point\|鞍点Saddle Point]]/[[计算机相关/机器学习/概念碎片/基础概念/局部最低点 local minima\|局部最低点 local minima]]的图的优化算法则容易被卡住，可能需要更加复杂的优化器（如[[计算机相关/机器学习/概念碎片/Adam优化器\|Adam优化器]]、[[计算机相关/机器学习/概念碎片/RMSProp优化器\|RMSProp优化器]]）

[[计算机相关/机器学习/概念碎片/基础概念/梯度下降gradient descent\|梯度下降gradient descent]]就是沿着error surface上最陡的下坡反向走，直到到达最低点。