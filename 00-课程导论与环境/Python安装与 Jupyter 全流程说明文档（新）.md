# 🐍 Windows 系统 Python（Miniconda）安装与 Jupyter 全流程说明文档

------

# 目录

1. 什么是 Miniconda？为什么要安装它？
2. 什么是终端？如何打开终端？
3. 下载并安装 Miniconda（正确网址＋版本选择）
4. **创建稳定版本 Python 环境（3.10–3.12，强烈推荐）**
5. 验证 Python / Conda 是否安装成功
6. 配置国内镜像源（加速 pip/conda）
7. Jupyter Notebook 与 Jupyter Lab 的区别
8. 如何安装 Jupyter Notebook / Lab（在哪里装）
9. 如何启动 Notebook / Lab
10. 如何制作启动脚本（.bat 文件，适合新手）
11. 可选优化：中文界面、自动补全、运行时间
12. 完整流程图

------

# 1. 什么是 Miniconda？为什么要安装它？

Miniconda 是一个 **轻量级的 Python 环境管理工具**，包含：

- Python 解释器
- Conda 包管理器
- 多版本、多环境管理能力

它相比 Anaconda 更轻量、更灵活、更稳定，适合课程教学与科研使用。

------

# 2. 什么是终端？如何打开终端？

## 2.1 终端是什么？

📌 **终端（Terminal）就是输入命令的窗口。**

示例命令：

```
python
pip install numpy
jupyter lab
```

------

## 2.2 如何打开终端？

### ⭐ 方法 A（最推荐）

```
Win + R → 输入 cmd → 回车
```

### 方法 B：搜索

```
Win + Q → 输入 cmd 或 PowerShell
```

### 方法 C：在当前文件夹打开终端

文件夹空白处右键 → **在终端中打开**

------

# 3. 下载并安装 Miniconda（最新稳定安装方法）

## 3.1 正确下载地址

👉 **https://www.anaconda.com/download**

页面底部（Miniconda Installers）选择：

- **Windows**
- **Python 3.13**
- **Windows 64-Bit Graphical Installer**
   （最右下方的紫色链接）

📌 不要担心它显示 “Python 3.13”：
 你后面会创建 **真正用于学习的稳定版本 Python 3.10/3.11/3.12 环境**。

------

## 3.2 安装步骤

1. 双击安装包

2. 一路点击 **Next**

3. 默认路径可用，也可改成：

   ```
   C:\Miniconda3
   ```

4. 点击 **Install** → 完成后 **Finish**

👉 全部默认设置即可。
 👉 不需要勾选额外选项。

------

# 4. ★创建稳定版本 Python 环境（3.10–3.12 必做）

Miniconda 默认带 Python 3.13，但很多库（金融/科研类）暂不完全支持。
 因此课程与科研推荐使用 **Python 3.10–3.12 的稳定版本**。

------

## 4.1 创建 Python 3.11 的课程稳定环境（推荐）

在终端输入：

```bash
conda create -n py311 python=3.11
```

激活环境：

```bash
conda activate py311
```

你之后所有安装都在这个环境里进行，例如：

```bash
pip install jupyterlab numpy pandas matplotlib statsmodels
```

------

## 4.2 可选择 Python 3.10 或 3.12

```bash
conda create -n py310 python=3.10
conda create -n py312 python=3.12
```

课程统一环境建议设定为：
 📌 **Python 3.11（最佳综合稳定性+性能）**

------

# 5. 验证环境是否成功

确认当前环境的 Python 版本：

```bash
python --version
```

应显示：

```
Python 3.11.x
```

检查 conda：

```bash
conda
```

若能正常显示命令列表 → 安装成功。

------

# 6. 配置国内镜像源（推荐，速度提升 10 倍）

```bash
conda config --set custom_channels.auto https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/
```

测试：

```bash
pip install numpy
```

速度明显变快即可。

------

# 7. Jupyter Notebook 与 Jupyter Lab 的区别

## 7.1 Jupyter Notebook（基础版）

✔ 入门简单
 ✔ 可运行 ipynb
 ❌ 多标签不方便
 ❌ 文件管理弱
 ❌ 扩展能力低

------

## 7.2 Jupyter Lab（推荐）

Jupyter Lab = Notebook 的增强版 IDE。

优势：

- 多标签
- 文件浏览器
- 内置终端
- 插件丰富
- 适合科研与课程作业

👉 **课程统一推荐使用 Jupyter Lab**

------

# 8. 安装 Jupyter Notebook / Lab（在稳定环境中安装）

📌 必须在你激活的 py311（或 py310/py312）环境中安装
 📌 不要在 base 环境中安装
 📌 不需要进入 Miniconda 安装目录

------

## 8.1 安装 Jupyter Notebook

```bash
pip install notebook
```

启动：

```bash
jupyter notebook
```

------

## 8.2 安装 Jupyter Lab（优先）

```bash
pip install jupyterlab
```

启动：

```bash
jupyter lab
```

------

# 9. 如何启动 Notebook / Lab

进入你的项目文件夹，例如：

```
D:\MyProjects\PythonCourse\
```

### 方法 1：右键在文件夹打开终端

```
jupyter lab
```

### 方法 2：地址栏输入 cmd

```
cmd → 回车 → jupyter lab
```

### 方法 3：使用启动脚本（见下节）

------

# 10. 启动脚本（.bat 文件）——最适合新手

## 10.1 启用文件扩展名显示

- Win11：查看 → 显示 → 勾选 “文件扩展名”
- Win10：查看 → 勾选 “文件扩展名”

------

## 10.2 在项目文件夹创建脚本

右键 → 新建 → 文本文档
 改名为：

```
start.bat
```

------

## 10.3 编辑脚本内容

```bash
@echo off
jupyter lab
pause
```

保存退出。

------

## 10.4 双击启动

- 不需要打开终端
- 不需要输入命令
- 自动在当前目录启动 Jupyter Lab

学生最友好！

------

# 11. 可选优化（让 Lab 更好用）

## 11.1 中文界面

```bash
pip install jupyterlab-language-pack-zh-CN
```

------

## 11.2 自动补全（LSP 支持）

让 Lab 拥有 VSCode 级智能提示：

```bash
pip install jupyter-lsp
pip install python-lsp-server[all]
```

Lab → 扩展管理 → 搜索 “LSP” → 安装。

------

## 11.3 显示单元运行时间

```bash
pip install jupyterlab_execute_time
```

------

# 12. 完整流程图

```
Win + R → cmd
        ↓
官网 anaconda.com/download 下载 Miniconda
        ↓
安装（默认设置）
        ↓
★ 创建稳定 Python 环境（如 py311）
        ↓
conda activate py311
        ↓
配置清华镜像
        ↓
pip install jupyterlab
        ↓
进入项目文件夹打开终端
        ↓
jupyter lab
        ↓
（可选）start.bat 一键启动
        ↓
（可选）中文界面 + 自动补全 + 运行时间插件
```

