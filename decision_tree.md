## 1️⃣ 熵（Entropy）

度量一个数据集的不确定性：

$$
H(D) = - \sum_{k=1}^{K} p_k \log_2(p_k)
$$

* $D$：当前节点的数据集
* $K$：类别数（信用风险里通常是 2：违约/不违约）
* $p_k$：类别 $k$ 在节点中所占比例

📌 熵越大 → 数据越混乱；熵越小 → 数据越纯。

---

## 2️⃣ 信息增益（Information Gain, ID3 用）

某个特征 $A$ 的分裂效果：

$$
Gain(D, A) = H(D) - \sum_{v=1}^{V} \frac{|D_v|}{|D|} H(D_v)
$$

* $V$：特征 $A$ 的可能取值个数
* $D_v$：按特征 $A=v$ 分裂后的子集
* $|D_v|$：子集大小

📌 **信息增益越大 → 特征越好**。

---

## 3️⃣ 基尼指数（Gini Index, CART 用）

另一种纯度度量：

$$
Gini(D) = 1 - \sum_{k=1}^{K} p_k^2
$$

* 完全纯（全部同一类） → Gini = 0
* 类别均匀混合 → Gini 最大（例如二分类时 Gini=0.5）。

CART 算法选择使得 **加权 Gini 最小** 的特征。

---

## 4️⃣ 信息增益率（Gain Ratio, C4.5 用）

为避免特征取值多时偏向性问题，引入**信息增益率**：

$$
GainRatio(D, A) = \frac{Gain(D, A)}{IV(A)}
$$

其中：

$$
IV(A) = - \sum_{v=1}^{V} \frac{|D_v|}{|D|} \log_2 \frac{|D_v|}{|D|}
$$

---

## 5️⃣ 通用流程（每次迭代）

1. 在当前节点数据集 $D$ 上：

   * 计算 $H(D)$ 或 $Gini(D)$。
2. 对每个特征 $A$：

   * 计算分裂后的加权熵/基尼。
   * 计算信息增益 / 基尼减少量。
3. 选择最优特征做分裂。
4. 对子集递归重复以上步骤。

Reference:

* https://www.atmosp.physics.utoronto.ca/~shahnas/Courses/Machine_Learning_Grad/Lecture_09.pdf 
