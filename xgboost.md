## 📐 一、XGBoost 的数学公式

XGBoost 的目标函数是：

$$
Obj = \sum_{i=1}^{n} l(y_i, \hat{y}_i) + \sum_{k=1}^{K} \Omega(f_k)
$$

其中：

* $l(y_i, \hat{y}_i)$：损失函数（如平方误差、逻辑回归损失等）
* $\Omega(f_k) = \gamma T + \frac{1}{2}\lambda \|w\|^2$：正则化项

  * $T$：树的叶子节点数
  * $w$：叶子节点的权重
  * $\gamma, \lambda$：正则化参数

### 🌱 第 t 次迭代时

我们要在已有预测 $\hat{y}_i^{(t-1)}$ 上加一棵新树 $f_t(x)$：

$$
\hat{y}_i^{(t)} = \hat{y}_i^{(t-1)} + f_t(x_i)
$$

于是新的目标函数近似展开成二阶泰勒展开：

$$
Obj^{(t)} \approx \sum_{i=1}^n \left[ g_i f_t(x_i) + \tfrac{1}{2} h_i f_t(x_i)^2 \right] + \Omega(f_t)
$$

其中：

* $g_i = \frac{\partial l(y_i, \hat{y}_i^{(t-1)})}{\partial \hat{y}_i^{(t-1)}}$ （一阶梯度）
* $h_i = \frac{\partial^2 l(y_i, \hat{y}_i^{(t-1)})}{\partial (\hat{y}_i^{(t-1)})^2}$ （二阶梯度）

### 🌳 如何分裂节点

假设一个叶子节点包含样本集合 $I$，它的最优权重为：

$$
w^* = - \frac{\sum_{i \in I} g_i}{\sum_{i \in I} h_i + \lambda}
$$

该节点的得分（也叫 Gain）是：

$$
Score(I) = -\frac{1}{2} \cdot \frac{(\sum_{i \in I} g_i)^2}{\sum_{i \in I} h_i + \lambda} + \gamma
$$

当尝试一个划分（分成左、右两个子集 $I_L, I_R$）时，增益为：

$$
Gain = \tfrac{1}{2} \left[ \frac{(\sum_{i \in I_L} g_i)^2}{\sum_{i \in I_L} h_i + \lambda} 
+ \frac{(\sum_{i \in I_R} g_i)^2}{\sum_{i \in I_R} h_i + \lambda}
- \frac{(\sum_{i \in I} g_i)^2}{\sum_{i \in I} h_i + \lambda} \right] - \gamma
$$

只要 Gain > 0，就值得分裂。

---

## 📝 二、简单例子（手工训练一个 XGBoost 树）

假设我们要做 **回归问题**：
训练数据：

| x | y |
| - | - |
| 1 | 2 |
| 2 | 3 |
| 3 | 4 |

### Step 1: 初始预测

一般先设 $\hat{y}=0$。

### Step 2: 计算一阶、二阶梯度

损失函数用平方误差 $l = \frac{1}{2}(y - \hat{y})^2$。

* 一阶梯度：$g_i = \hat{y}_i - y_i$
* 二阶梯度：$h_i = 1$

所以：

| i | y | 预测 $\hat{y}$ | g  | h |
| - | - | ------------ | -- | - |
| 1 | 2 | 0            | -2 | 1 |
| 2 | 3 | 0            | -3 | 1 |
| 3 | 4 | 0            | -4 | 1 |

### Step 3: 建树并计算分裂增益

假设我们只考虑一维特征 $x$，划分点可以在 1.5 和 2.5。

* 划分点 1.5：

  * 左节点 (x=1): g=-2, h=1
  * 右节点 (x=2,3): g=-7, h=2

  Gain = $\tfrac{1}{2} [ \frac{(-2)^2}{1+λ} + \frac{(-7)^2}{2+λ} - \frac{(-9)^2}{3+λ}] - γ$

如果 λ=0, γ=0：
Gain = 0.5 \* \[4/1 + 49/2 - 81/3] = 0.5 \* (4 + 24.5 - 27) = 0.75 > 0 ✅ 可分裂。

### Step 4: 计算叶子权重

* 左叶子权重 = $-\frac{-2}{1+0} = 2$
* 右叶子权重 = $-\frac{-7}{2+0} = 3.5$

于是第一棵树学到的预测：

* x=1 → 2
* x=2,3 → 3.5

---

👉 这就是 XGBoost 如何通过 **梯度 + 增益公式** 来训练树的过程。

要不要我给你写一段 **Python 代码（用手算公式而不是 sklearn 调库）**，展示这个简单例子怎么跑？
