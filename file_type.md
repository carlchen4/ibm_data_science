

### 1. **Text files（文本文件）**

* **内容：** 人类可读，主要是字符（ASCII、UTF-8 等编码）。
* **例子：**

  * `.txt` → 纯文本
  * `.csv` → 数据表格
  * `.json`、`.xml`、`.yaml` → 配置/数据交换
  * `.py`、`.java`、`.html`、`.md` → 代码/文档

---

### 2. **Binary files（二进制文件）**

* **内容：** 任意字节，不一定可读，需要特定软件解析。
* **例子：**

  * 图片：`.jpg`、`.png`
  * 视频：`.mp4`
  * 音频：`.mp3`
  * 可执行：`.exe`、Linux ELF
  * 压缩：`.zip`、`.tar.gz`
  * 模型：`.pkl`、`.onnx`

---

### 3. **Executable files（可执行文件）**

严格来说是 **binary 的一个子类**，但经常单独拿出来：

* **Windows：** `.exe`、`.dll`
* **Linux / Unix：** ELF (`a.out`，无扩展名也可能是可执行)
* **脚本型可执行：** `.sh`、`.bat`（其实是文本，但能被解释器执行）

---

### 4. **Special files（特殊文件）**

在 Linux / Unix 系统特别重要：

* **Device files（设备文件）** → `/dev/sda`（磁盘）、`/dev/null`
* **Socket files（套接字）** → 进程间通信
* **FIFO / Pipe（命名管道）** → 数据流通信

---

### 5. **Archive / Container files（归档/容器文件）**

* 本质上是封装多种数据的格式，既可包含文本又可包含二进制。
* **例子：**

  * `.zip`、`.tar`、`.rar`
  * `.iso`（光盘镜像）
  * `.docx`、`.xlsx`（其实是 zip 容器 + XML 文件）

---

📌 总结：
一般我们说的主要就是 **Text file vs Binary file**。
但从系统角度，还可以细分为 **Executable、Special、Archive/Container** 等。

要不要我给你画一个 **文件类型分类图（树状图）**，让你一眼就看清楚它们的关系？
