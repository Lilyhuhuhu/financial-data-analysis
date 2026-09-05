------

# 🐍 Windows 系统 Python（Miniconda）安装与 Jupyter 全流程说明文档



------

# 目录

1. 什么是 Miniconda？为什么要安装它？
2. 什么是终端？如何打开终端？
3. 下载并安装 Miniconda
4. 验证 Python / Conda 是否安装成功
5. 配置国内镜像源（加速 pip/conda）
6. Jupyter Notebook 与 Jupyter Lab 的区别
7. 如何安装 Jupyter Notebook / Lab（在哪里装）
8. 如何启动 Notebook / Lab
9. 如何制作启动脚本（.bat 文件，适合新手）
10. 可选优化：中文界面、自动补全、运行时间
11. 完整流程图（适合集成进课件）

------

# 1. 什么是 Miniconda？为什么要装它？

Miniconda 是一个 **轻量级的 Python 环境管理工具**，它包含：

- Python 解释器
- Conda 包管理器
- 多环境管理能力（适合课程/科研）

与 Anaconda 相比：

| 工具          | 内容           | 体积 | 优点                           |
| ------------- | -------------- | ---- | ------------------------------ |
| **Anaconda**  | 内置大量科学库 | 大   | 开箱即用                       |
| **Miniconda** | 仅核心功能     | 小   | **更灵活、更稳定、更适合学生** |

👉 推荐学生使用 **Miniconda + 自己安装所需库**。

------

# 2. 什么是终端？如何打开终端？

## 2.1 终端是什么？

📌 终端（Terminal）就是一个输入命令的窗口，你可以在里面输入：

```
python
pip install numpy
jupyter lab
```

终端=电脑的“命令对话框”。

------

## 2.2 如何打开终端？

### ✅ 方法 A（最推荐）

按：

```
Win + R
```

输入：

```
cmd
```

按回车 → 打开命令提示符（CMD）。

------

### 方法 B：通过搜索打开

按：

```
Win + Q
```

搜索 `cmd` 或 `PowerShell`。

------

### 方法 C：在某个文件夹直接打开终端

进入你的项目文件夹
 空白处 **右键 → 在终端中打开**

这个方法非常适合启动 Jupyter。

------

# 3. 下载并安装 Miniconda

### 3.1 下载

进入官网下载页面：

👉 https://docs.conda.io/en/latest/miniconda.html

滚动到底部 → 选择：

- **Windows**
- **64-bit**
- **Graphical Installer（图形界面安装程序）**

------

### 3.2 安装步骤

1. 双击安装包
2. 一路点击 “Next”
3. 路径可默认，也可改成：

```
C:\Miniconda3
```

1. 点击 Install
2. 完成后点击 Finish

**全部使用默认设置即可。**

------

# 4. 验证 Python 与 Conda 是否成功安装

打开终端（Win + R → cmd），输入：

------

## 4.1 检查 Python

```bash
python
```

如果显示：

```
Python 3.12.x ...
>
```

说明安装成功。

退出：

```
quit()
```

------

## 4.2 检查 conda

```bash
conda
```

如果看到大量命令说明（create / install / list …），说明成功。

------

# 5. 配置国内镜像源（强烈建议）

终端输入：

```bash
conda config --set custom_channels.auto https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/
```

测试包安装速度：

```bash
pip install numpy
```

速度显著加快即成功。

------

# 6. Jupyter Notebook 与 Jupyter Lab 的区别

## 6.1 Jupyter Notebook（简洁）

✔ 适合基础练习
 ✔ 简单易用
 ❌ 不支持多标签
 ❌ 文件管理弱
 ❌ 扩展能力弱

------

## 6.2 Jupyter Lab（推荐）

Jupyter Lab = Notebook 的升级版 IDE。

优势：

- 支持多文档标签页
- 内置文件浏览器
- 内置终端
- 插件丰富
- 适合科研与课程作业
- 更现代、更稳定

👉 **推荐使用 Lab**

------

# 7. 安装 Jupyter Notebook / Jupyter Lab

📌 **必须在“系统终端”中执行安装命令：CMD / PowerShell / Windows Terminal。**

📌 **不需要进入 Miniconda 的安装目录**

------

## 7.1 安装 Notebook

在终端运行：

```bash
pip install notebook
```

启动：

```bash
jupyter notebook
```

------

## 7.2 安装 Jupyter Lab（推荐）

在终端运行：

```bash
pip install jupyterlab
```

启动：

```bash
jupyter lab
```

------

# 8. 如何启动 Notebook / Lab

启动时建议在你的“项目文件夹”中打开终端，例如：

```
D:\MyProjects\PythonCourse\
```

### 方法 1：右键在文件夹打开终端 → 输入

```
jupyter lab
```

### 方法 2：地址栏打开终端

在文件夹地址栏输入：

```
cmd
```

再输入：

```
jupyter lab
```

### 方法 3：使用启动脚本（适合新手学生）

见下一节。

------

# 9. 制作启动脚本（双击即可打开）

启动脚本是一个 `.bat` 文件，可以一键启动 Jupyter Lab。

------

## 9.1 第一步：启用文件扩展名显示

为了看到 `.bat` 后缀：

- Win11：查看 → 显示 → 勾选 **文件扩展名**
- Win10：查看 → 勾选 **文件扩展名**

------

## 9.2 第二步：创建启动脚本

在你的项目文件夹里：

1. 右键 → 新建 → 文本文档
2. 命名为：

```
start.bat
```

（必须含 .bat 后缀）

------

## 9.3 第三步：编辑脚本内容

右键 → 编辑
 输入：

```
@echo off
jupyter lab
pause
```

保存退出。

------

## 9.4 第四步：双击即可启动

双击 `start.bat` → 自动打开 Jupyter Lab。

👍 优点：

- 不用打开终端
- 不用记命令
- 自动在当前目录打开 Lab
- 零基础学生最友好

------

# 10. 可选优化（让环境更好用）

------

## 10.1 Jupyter Lab 中文界面

```bash
pip install jupyterlab-language-pack-zh-CN
```

刷新浏览器即可。

------

## 10.2 自动补全（LSP 支持）

LSP 全称是 Language Server Protocol（语言服务器协议）。 它是由微软提出的一个统一标准，让编辑器能够智能地理解你的代码，从而提供更强的编程体验。

简单理解： 📌 LSP = 让 Jupyter Lab 拥有像 VSCode、PyCharm 那样的智能代码提示系统。

```bash
pip install jupyter-lsp
pip install python-lsp-server[all]
```

在 Lab 界面 → 扩展管理 → 搜索 “LSP” → 安装。

------

## 10.3 显示每个单元运行时间

```bash
pip install jupyterlab_execute_time
```

刷新即可。

------

# 11. 完整流程图

```
打开终端（Win + R → cmd）
       ↓
下载 Miniconda
       ↓
安装（默认设置即可）
       ↓
验证 python / conda
       ↓
配置清华镜像
       ↓
pip install jupyterlab
       ↓
进入项目文件夹打开终端
       ↓
jupyter lab
       ↓
（可选）创建 start.bat 一键启动
       ↓
（可选）中文界面 + 自动补全 + 运行时间插件
```

