# CariesXrays: 基于特征金字塔对比学习的医院级全景牙科X射线龋齿检测增强方法

<!-- 语言选择器 -->
<p align="center">
  <a href="README.md">English</a> | 
  <a href="README_zh.md">中文</a>
</p>

<img src="./FPCL_main.jpg" width="800">

## 摘要

龋齿已被广泛认为是公共卫生领域最普遍的慢性疾病之一。尽管自动化诊断在各个医学领域都取得了进展，但由于龋齿固有的变异性和复杂性，龋齿检测仍然是一个重大挑战。为了弥补这一差距，我们发布了一个医院级全景牙科X射线基准数据集"CariesXrays"，以促进龋齿高精度计算机辅助诊断的发展。该数据集包含6,000张全景牙科X射线图像，总共13,783个龋齿实例，均由牙科专业人员精心标注。

在本文中，我们提出了一种新颖的特征金字塔对比学习（FPCL）框架，在统一的诊断范式中联合结合特征金字塔学习和对比学习，用于自动化龋齿检测。具体而言，我们设计了一个鲁棒的双向特征金字塔网络（D2D-FPN），自适应地从多级特征图中捕获丰富且信息量大的上下文信息，从而增强龋齿检测在不同尺度上的泛化能力。此外，我们的模型还配备了有效的提案-原型对比正则化学习（P2P-CRL）机制，该机制能够灵活地弥合具有不同外观的多样化龋齿之间的语义差距，从而产生高质量的龋齿提案。在我们新建立的CariesXrays基准上进行的大量实验证明了FPCL在龋齿诊断方面具有显著社会影响的潜力。

## 环境要求

* Python 3.6/3.7/3.8
* PyTorch 1.7.1
* pycocotools (Linux: `pip install pycocotools`; Windows: `pip install pycocotools-windows`)
* Ubuntu 或 CentOS
* 详细要求见 `requirements.txt`

<img src="./FPCL_subFig.jpg" width="400">

## 下载测试模型权重

```
https://drive.google.com/file/d/1bHaUjqPWrL-OXM2-IPl5gBBgTs0TfULT/view?usp=drive_link
```

## 下载CariesXrays数据集

```
https://drive.google.com/drive/folders/1qWL2f0A-vf91StHxs24eoiFDyuoHEh4N?usp=drive_link
```

## 在CariesXrays数据集上运行代码（VOC格式）

* CariesXrays数据集将在上传时遵循此格式
* FPCL训练：`python train.py`

## 引用

如果您发现此工作对您的研究有用，请考虑引用以下论文：

```bibtex
@inproceedings{chen2024cariesxrays,
  title={CariesXrays: Enhancing caries detection in hospital-scale panoramic dental X-rays via feature pyramid contrastive learning},
  author={Chen, Bingzhi and Fu, Sisi and Liu, Yishu and Pan, Jiahui and Lu, Guangming and Zhang, Zheng},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
  volume={38},
  number={20},
  pages={21940--21948},
  year={2024}
}
```

## 联系方式

如果您有任何问题，请联系我们：
- 邮箱：chenbingzhi@m.scnu.edu.cn 或 darrenzz219@gmail.com

---

## 项目结构

```
AAAI2024_CariesXrays/
├── CariesXrays_Dataset(0.5%)/     # 示例数据集（0.5%的数据）
│   ├── Annotations/               # XML格式的标注文件
│   └── JEPGImages/                # JPEG图像文件
├── FPCL-main/                     # 主要代码目录
│   ├── backbone/                  # 骨干网络模块
│   ├── network_files/             # 网络文件
│   ├── train_utils/               # 训练工具
│   ├── train.py                   # 训练脚本
│   ├── predict.py                 # 预测脚本
│   ├── validation.py              # 验证脚本
│   └── requirements.txt           # 依赖包列表
├── README.md                      # 英文说明文档
├── README_zh.md                   # 中文说明文档
└── *.jpg                         # 示例图片
```

## 快速开始

1. **克隆仓库**
   ```bash
   git clone https://github.com/Binz-Chen/AAAI2024_CariesXrays.git
   cd AAAI2024_CariesXrays
   ```

2. **安装依赖**
   ```bash
   cd FPCL-main
   pip install -r requirements.txt
   ```

3. **下载数据集和模型权重**
   - 从上述Google Drive链接下载CariesXrays数据集和预训练权重

4. **开始训练**
   ```bash
   python train.py
   ```

5. **进行预测**
   ```bash
   python predict.py
   ```

## 许可证

本项目的使用请遵循相应的许可证条款。

## 贡献

欢迎贡献代码和改进建议。请通过提交Issue或Pull Request的方式参与项目。
