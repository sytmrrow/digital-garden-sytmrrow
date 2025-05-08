---
{"dg-publish":true,"permalink":"/计算机相关/机器学习/概念碎片/基础概念/MAEloss/","dgPassFrontmatter":true,"created":"2025-05-09T00:45:13.422+08:00","updated":"2025-05-09T02:17:34.106+08:00"}
---

平均绝对误差![Pasted image 20250509004533.png](/img/user/Pasted%20image%2020250509004533.png)

对<font color="#c00000">离群点的敏感度较低</font>，鲁棒性更强

并且与原始目标的单位相同

<font color="#c00000">导数在0处不连续</font>，所以优化时具有挑战

对应预测误差的中位数估计（最小化绝对偏差）
![Pasted image 20250509005559.png](/img/user/Pasted%20image%2020250509005559.png)
# 何时选择maeloss
当希望对所有误差一视同仁，不想让少数大误差过度影响总体评价时
需要模型具有更好的鲁棒性，减少对离群点的敏感时
