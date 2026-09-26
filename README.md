# CS231n 学习笔记

中文、适合初学者的 Stanford CS231n Spring 2025 学习笔记。按用户提供的 B 站课程及对应年份的官方课件整理，包含概念解释、符号与形状、公式推导、手算例子、原创图示和易错点。

**第 1–18 章均已有笔记。2026-09-26 按用户要求，一次补齐第 4–18 章；笔记已整理不代表用户已经学完。** 第一章继续保留、暂缓讨论，后续可以按自己的进度阅读和讨论任意章节。

## 阅读入口

- [全课程复习路线与概念索引](REVIEW_MAP.md)：查某个概念该回到哪章，以及章节怎样衔接。
- [学习与讨论进度](PROGRESS.md)：分别记录笔记状态与讨论状态。
- [来源核对范围](SOURCES.md)：课程版本、正文与补充区别，第十八讲的特殊来源情况。
- [图片如何变成数字](notes/00-getting-started.md)：额外基础材料，不是正式第一讲。

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

专题补充：[Softmax 数值稳定性](notes/02-softmax-numerical-stability.md)。

## 怎么阅读

第一遍先读每章的问题、直觉、图示和手算例子，再对照公式。遇到矩阵乘法，先看形状；遇到生成模型，先分清训练目标与采样过程。讲师课件中的例子、整理者补充和没有完整核对的部分分别注明。

用户已授权完成全部剩余笔记，不需要逐章等待确认。实际讨论仍按用户选择的章节展开，不安排测验，不据笔记完成状态推断掌握程度。

## 例子与配图

在仓库根目录运行以下命令，无需下载数据或安装深度学习框架：

```bash
python3 experiments/chapter02_forward.py
python3 experiments/chapter03_optimization.py
python3 experiments/remaining_examples.py
```

第三个脚本复现第 4–18 章中的数值例子，包括反向传播的数值梯度核验、卷积、注意力、IoU、VAE KL、流采样和报警基率等。**它们是教学算例，不是真实数据集上的训练实验。**

原创配图存于 `assets/`，同时保留 PNG 和 SVG。生成脚本存于 `scripts/`，使用 NumPy 和 Matplotlib；中文字体按环境配置。新增 15 章每章配有一张原创图。

## 版本、引用与 GitHub

- [官方 2025 课程安排](https://cs231n.stanford.edu/2025/schedule.html)
- [用户提供的 B 站课程](https://www.bilibili.com/video/BV1aXhJ64EmW/)
- [官方配套笔记](https://cs231n.github.io/)

原先用户给出的官网链接当前显示 2026 版；所提供 B 站视频的实际内容对应 2025 版。本仓库沿用 2025，不混入另一年度的章节安排。正文按学习逻辑重组，不是讲义或视频逐字复制。

计划 GitHub 仓库名为 `cs231n-notes`，初始设想为 Private。**当前资料保存在本地 Git 仓库，尚未创建远程仓库或上传。** 后续公开与否由用户决定。课件、视频优先提供链接，不整套转载；作业解答与原创教学小实验分开管理。

[笔记模板](templates/lecture.md) · [学习疑问](QUESTIONS.md)
