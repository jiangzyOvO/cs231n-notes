# CS231n 学习笔记

**从直觉出发，跟着例子计算，再读懂公式与代码。** 这套中文笔记按 Stanford CS231n Spring **2025** 的实际课程材料整理，适合有一些 Python 和数学基础、刚开始学习视觉与神经网络的读者。

**18 章均已整理，并于 2026-09-26 完成初学者阅读重组。** 每章有学习卡、分层阅读路线、关键概念解释和复习卡；保留专业公式、来源与适用条件。笔记完成不代表学习完成，可以按自己的进度阅读。

## 从这里开始

| 阅读需求 | 入口 |
|---|---|
| **第一次打开这套笔记** | [初学者阅读指南](READING_GUIDE.md)：怎样读两遍，哪些推导可以稍后再看 |
| **看不懂数组、矩阵或公式符号** | [数学与 NumPy 工具箱](notes/00-math-and-numpy.md)：求和、矩阵乘法、广播、偏导 |
| 不明白图片怎样成为模型输入 | [图片如何变成数字](notes/00-getting-started.md) |
| 想复习某个概念 | [全课程复习路线与概念索引](REVIEW_MAP.md) |
| 想看目前讨论到哪里 | [学习与讨论进度](PROGRESS.md) |

> **阅读提示**：加粗文字与引用框标出核心结论、直觉和易错点。先看每章学习卡、图与手算，再看完整推导。符号在出现处解释，不需要先背完所有缩写。

## 完整目录

| 章 | 笔记 | 重点 |
|---|---|---|
| 01 | [课程导论](notes/01-introduction.md) | 计算机视觉、历史与课程方向 |
| 02 | [图像分类与线性分类器](notes/02-image-classification.md) | k-NN、线性分数、Softmax、损失 |
| 03 | [正则化与优化](notes/03-regularization-optimization.md) | 梯度、SGD、Momentum、Adam、AdamW |
| 04 | [神经网络与反向传播](notes/04-neural-networks-backprop.md) | 非线性、计算图、链式法则、矩阵梯度 |
| 05 | [卷积神经网络](notes/05-convolutional-networks.md) | 卷积、形状、参数量、池化、感受野 |
| 06 | [训练 CNN 与经典架构](notes/06-cnn-architectures.md) | BN、Dropout、初始化、ResNet、迁移 |
| 07 | [循环神经网络](notes/07-recurrent-networks.md) | 序列、BPTT、语言生成、LSTM |
| 08 | [注意力与 Transformer](notes/08-attention-transformers.md) | QKV、掩码、多头、ViT、现代组件 |
| 09 | [检测、分割与模型可视化](notes/09-detection-segmentation.md) | FCN、U-Net、检测器、IoU、CAM/Grad-CAM |
| 10 | [视频理解](notes/10-video-understanding.md) | 采样、3D CNN、光流、SlowFast、音视频 |
| 11 | [大规模分布式训练](notes/11-distributed-training.md) | 数据并行、FSDP、重算、CP/TP/PP、利用率 |
| 12 | [自监督学习](notes/12-self-supervised-learning.md) | 预文本任务、MAE、InfoNCE、SimCLR、MoCo、DINO |
| 13 | [生成模型（一）](notes/13-generative-models-1.md) | 最大似然、自回归、VAE、ELBO、重参数化 |
| 14 | [生成模型（二）](notes/14-generative-models-2.md) | GAN、Rectified Flow、CFG、潜空间扩散 |
| 15 | [三维视觉](notes/15-3d-vision.md) | 点云、网格、体素、SDF、PointNet、NeRF |
| 16 | [视觉与语言](notes/16-vision-language.md) | CLIP、VLM、LLaVA、Flamingo、SAM、程序组合 |
| 17 | [机器人学习](notes/17-robot-learning.md) | 感知行动闭环、RL、规划、模仿、VLA |
| 18 | [以人为中心的 AI](notes/18-human-centered-ai.md) | 人类视觉、偏差、隐私、辅助与真实任务 |

## 两篇重点配套讲解

- [Softmax 数值稳定性](notes/02-softmax-numerical-stability.md)：为什么减最大值，为什么还要直接计算对数损失。
- [两层 NumPy 网络逐行讲解](notes/04-numpy-network-walkthrough.md)：截图中的 Sigmoid 网络，从每行形状、反向传播一直讲到红框中的权重更新。

## 怎样使用图片与重点提示

每章的图下有读图说明，交代坐标、颜色和示意范围。重点通过 **粗体**、表格与引用块区分，兼容浅色和深色阅读主题。数学公式、图解与代码互相对应；第一遍暂缓的内容仍保留在原章内，方便第二遍复习。

新补充的 5 张基础图覆盖：课程路线、广播、两层网络反传、BN/LN 统计轴、注意力读取过程。课程中已有的近邻、优化、卷积、生成与其他主题图继续保留。

## 例子与配图

在仓库根目录运行以下命令，只用 Python 标准库，无需下载数据或安装深度学习框架：

```bash
python3 experiments/chapter02_forward.py
python3 experiments/chapter03_optimization.py
python3 experiments/remaining_examples.py
```

第三个脚本复现第 4–18 章中的数值例子，包括反向传播的数值梯度核验、卷积、注意力、IoU、VAE KL、流采样和报警基率等。**它们是教学算例，不是真实数据集上的训练实验。**

截图对应的网络另有完整脚本，需要 NumPy：

```bash
python3 experiments/sigmoid_network.py
```

它先用小网络做数值梯度核验，再用固定随机数据演示 2000 次更新；输出的是训练损失，不是图片分类准确率。

原创配图存于 `assets/`，同时保留 PNG 和 SVG。生成脚本存于 `scripts/`，使用 Matplotlib；部分脚本还使用 NumPy，中文字体按环境配置。本次基础图的源码为 [draw_beginner.py](scripts/draw_beginner.py)。

## 版本、引用与 GitHub

- [官方 2025 课程安排](https://cs231n.stanford.edu/2025/schedule.html)
- [用户提供的 B 站课程](https://www.bilibili.com/video/BV1aXhJ64EmW/)
- [官方配套笔记](https://cs231n.github.io/)

原先用户给出的官网链接当前显示 2026 版；所提供 B 站视频的实际内容对应 2025 版。本仓库沿用 2025，不混入另一年度的章节安排。正文按学习逻辑重组，不是讲义或视频逐字复制。

具体核对方式、课程内容与补充解释的区别，以及第十八讲的来源限制，见 [SOURCES.md](SOURCES.md)。本次重组以既有核对材料为基础，没有新增“完整观看所有视频”的声明。

计划 GitHub 仓库名为 `cs231n-notes`，初始设想为 Private。**当前资料保存在本地 Git 仓库，尚未创建远程仓库或上传。** 后续公开与否由用户决定。课件、视频优先提供链接，不整套转载；作业解答与原创教学小实验分开管理。

[笔记模板](templates/lecture.md) · [学习疑问](QUESTIONS.md)
