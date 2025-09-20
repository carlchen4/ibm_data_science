# 机器学习笔记 / Machine Learning Notes

## 1. 基础概念 / Basics
- 什么是机器学习 / What is Machine Learning. 
- Python 和常用库 / What is Python and its libraries.
- Hugging Face
- Github 
- 机器学习 vs 统计学 / ML vs Statistics
- 监督学习 / 无监督学习 / 强化学习 / Supervised / Unsupervised / Reinforcement Learning
- 训练集、测试集、验证集 / Train, Test, Validation Sets
- 偏差与方差 (Bias & Variance)
- 过拟合与欠拟合 / Overfitting & Underfitting
- 模型评估指标 / Evaluation Metrics
  - Accuracy 准确率
  - Precision 精确率
  - Recall 召回率
  - F1 Score
  - AUC
  - MSE 均方误差
  - R² 决定系数
  - KS（Kolmogorov-Smirnov Statistic）
  - Gini 系数：跟 AUC 有关，公式是 Gini = 2*AUC - 1，常用于信用评分卡。
  - Lift 值：看在某个客户群里，模型挑出的坏客户比例比随机抽样高多少。
  - Population Stability Index (PSI)：监控模型是否“漂移”（即样本分布变化太大）。
  - Brier Score：看预测概率的校准度。
  - AR（Accuracy Ratio）：跟 Gini 很像，也是衡量排序能力。

## 2. 数据处理 / Data Processing
- 数据清洗 / Data Cleaning
- 特征工程 / Feature Engineering
  - One-hot 编码
  - Label 编码
  - 标准化 & 归一化 / Scaling & Normalization
  - 特征选择 & 降维 / Feature Selection & Dimensionality Reduction
    - PCA 主成分分析
    - LDA 线性判别分析
- 数据集划分 / Train-Test Split
  - Cross-Validation 交叉验证

## 3. 经典算法 / Classical Algorithms

### 3.1 监督学习 / Supervised Learning
- 回归模型 / Regression
  - 线性回归 / Linear Regression
  - 逻辑回归 / Logistic Regression
- 决策树 / Decision Tree
- 随机森林 / Random Forest
- 梯度提升 / Gradient Boosting
  - GBDT, XGBoost, LightGBM, CatBoost
- 支持向量机 / SVM
- K 最近邻 / K-Nearest Neighbors (KNN)
- 朴素贝叶斯 / Naive Bayes

### 3.2 无监督学习 / Unsupervised Learning
- 聚类 / Clustering
  - K-Means, DBSCAN, HDBSCAN, Hierarchical
- 降维 / Dimensionality Reduction
  - PCA, t-SNE, UMAP
- 异常检测 / Anomaly Detection
  - Isolation Forest, Autoencoder

### 3.3 深度学习 / Deep Learning
- 神经网络基础 / Neural Networks
  - 感知机, BP
- CNN 卷积神经网络 / Convolutional Neural Network
- RNN / LSTM / GRU
- 自编码器 / Autoencoder
- Transformer 基础 / Transformers
  - Attention, BERT, GPT

### 3.4 强化学习 / Reinforcement Learning
- 基础概念 / Basic Concepts
  - Agent, Environment, Reward
- Q-Learning
- Deep Q-Learning

## 4. 模型优化 / Model Optimization
- 超参数调优 / Hyperparameter Tuning
  - Grid Search, Random Search, Bayesian Optimization
- 正则化 / Regularization
  - L1, L2, Dropout
- 集成学习 / Ensemble Learning
  - Bagging, Boosting, Stacking

## 5. 应用案例 / Use Cases
- 信用评分模型 / Credit Scoring
- 欺诈检测 / Fraud Detection
- 客户流失预测 / Churn Prediction
- 推荐系统 / Recommendation System
- 时间序列预测 / Time Series Forecasting
  - ARIMA, Prophet, LSTM

## 6. 工具与框架 / Tools & Frameworks
- Python 数据分析 / Python Data Analysis
  - NumPy, Pandas
- 可视化 / Visualization
  - Matplotlib, Seaborn
- 机器学习 / Machine Learning
  - scikit-learn
- 深度学习 / Deep Learning
  - TensorFlow, Keras, PyTorch

## 7. 银行业与金融应用 / Banking & Finance Applications
- 信贷风险建模 / Credit Risk Modeling (PD, LGD, EAD)
- 反洗钱 / Anti-Money Laundering (AML)
- 交易欺诈检测 / Transaction Fraud Detection
- 客户营销与个性化推荐 / Marketing & Personalization
- 流动性预测 / ATM & Branch Cash Forecasting

## 8. 学习资源 / Learning Resources
- 书籍 / Books
- 在线课程 / Online Courses
- GitHub & Kaggle 项目 / GitHub & Kaggle Projects
