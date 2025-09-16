## 1️⃣ Python

**Python** 是一种高级编程语言，广泛用于数据分析、机器学习、Web 开发等。

### 安装步骤：

1. 访问 Python 官方网站：[https://www.python.org/downloads/](https://www.python.org/downloads/)
2. 点击下载对应操作系统的最新版 Python（推荐 3.11 或更高）。
3. 安装时勾选 **“Add Python to PATH”**（非常重要）。
4. 安装完成后，打开终端或命令提示符，输入：

   ```bash
   python --version
   ```

   显示版本号说明安装成功。


在 Python 中创建新的 **虚拟环境（Environment, env）** 可以隔离不同项目的依赖库，避免冲突。下面我详细说明 **用 `venv` 和 `conda` 两种方式**创建新的环境。

---

#### 使用 `venv`（Python 自带工具）

##### 创建新的虚拟环境：

1. 打开终端（Mac/Linux）或命令提示符（Windows）。
2. 输入命令：

```bash
python -m venv myenv
```

这里：

* `myenv` 是你新环境的名字，可以改成任何名字。
* 命令会在当前目录下创建一个 `myenv` 文件夹，里面包含独立的 Python 和 `pip`。

##### 激活环境：

* **Windows**:

```bash
myenv\Scripts\activate
```

* **Mac/Linux**:

```bash
source myenv/bin/activate
```

激活后，你会看到命令行前面多了 `(myenv)`，表示当前在这个环境里。

##### 安装库：

```bash
pip install numpy pandas
```

##### 退出环境：

```bash
deactivate
```

---

## 2️⃣ 使用 `conda`（Anaconda 专用）

### 创建新的虚拟环境：

```bash
conda create -n myenv python=3.11
```

这里：

* `myenv` 是环境名字。
* `python=3.11` 指定 Python 版本，可根据需要改。

### 激活环境：

```bash
conda activate myenv
```

### 安装库：

```bash
conda install numpy pandas
```

或者用 `pip`：

```bash
pip install matplotlib
```

### 列出环境：

```bash
conda env list
```

### 删除环境：

```bash
conda remove -n myenv --all
```

---

## 2️⃣ Anaconda

**Anaconda** 是一个 Python 发行版，包含 Python 和大量科学计算库（如 NumPy、Pandas、Scikit-learn、Matplotlib 等），还自带 **Jupyter Notebook**。

### 安装步骤：

1. 访问官网：[https://www.anaconda.com/products/distribution](https://www.anaconda.com/products/distribution)
2. 下载对应操作系统的版本（Windows、Mac、Linux）。
3. 安装时选择 **“Add Anaconda to PATH”** 或使用 Anaconda Prompt。
4. 安装完成后，打开 **Anaconda Navigator** 或终端，输入：

   ```bash
   conda --version
   ```

   如果显示版本号就安装成功。

### 常用功能：

* **Jupyter Notebook**：交互式 Python 编程环境。
* **Spyder**：类似 MATLAB 的 Python IDE。
* **Conda**：管理 Python 包和虚拟环境。

---

## 3️⃣ Google Colab

**Colab** 是 Google 提供的在线 Python 编程环境，不需要安装任何软件，直接在浏览器运行。

### 使用步骤：

1. 打开网址：[https://colab.research.google.com/](https://colab.research.google.com/)
2. 登录 Google 账号。
3. 点击 **“New Notebook”** 创建新的 Notebook。
4. 直接在浏览器中写 Python 代码并运行：

   ```python
   print("Hello, Colab!")
   ```

### 优势：

* 免费使用 GPU / TPU 计算资源。
* 适合数据科学、深度学习实验。
* 不需要本地安装 Python。

---

## 4️⃣ VS Code（可选，但推荐）

**VS Code** 是微软开发的免费代码编辑器，可以安装 Python 插件，用于写 Python、调试和管理项目。

### 安装步骤：

1. 下载 VS Code：[https://code.visualstudio.com/](https://code.visualstudio.com/)
2. 安装后，进入 **Extensions（扩展）** 搜索 `Python`，安装 Microsoft 官方插件。
3. 可以结合 Anaconda 或 Python 解释器使用。

---

✅ **总结**：

| 工具       | 用途                         | 安装方式             |
| -------- | -------------------------- | ---------------- |
| Python   | 基础编程语言                     | 官方网站安装           |
| Anaconda | Python 发行版，科学计算库 + Jupyter | 官网安装             |
| Colab    | 在线 Python Notebook，无需安装    | 浏览器使用            |
| VS Code  | 代码编辑器，可调试和管理项目             | 官网安装 + Python 插件 |

---

如果你愿意，我可以帮你画一张**图示流程图**，显示从安装 Python 到在 Colab 或 Jupyter Notebook 运行代码的完整流程，非常直观。

你想让我画吗？
