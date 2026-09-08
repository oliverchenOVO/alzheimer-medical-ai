# 资料来源与使用条件

## Task 1：Alzheimer's Disease Dataset（表格资料）

- 发布者：Rabie El Kharoua（2024）
- 来源：[Kaggle — Alzheimer's Disease Dataset](https://www.kaggle.com/datasets/rabieelkharoua/alzheimers-disease-dataset)
- DOI：[`10.34740/KAGGLE/DSV/8668279`](https://doi.org/10.34740/KAGGLE/DSV/8668279)
- 内容：2,149 笔合成病人记录，含人口统计、生活型态、病史、临床量测、认知／功能评估与诊断标签。
- 授权：Creative Commons Attribution 4.0（CC BY 4.0）。本仓库保留原始 CSV，并在此标示作者、来源与授权。

建议引用：

> El Kharoua, R. (2024). Alzheimer's Disease Dataset. Kaggle. DOI: 10.34740/KAGGLE/DSV/8668279.

## Task 2：OASIS-1 MRI 与衍生资料集

原始资料来自 [Open Access Series of Imaging Studies（OASIS-1）](https://sites.wustl.edu/oasisbrains/home/oasis-1/)。OASIS-1 是横断面 MRI 资料集，共 416 位受试者；原始论文为：

> Marcus, D. S., Wang, T. H., Parker, J., Csernansky, J. G., Morris, J. C., & Buckner, R. L. (2007). Open Access Series of Imaging Studies (OASIS): Cross-sectional MRI Data in Young, Middle Aged, Nondemented, and Demented Older Adults. *Journal of Cognitive Neuroscience, 19*(9), 1498–1507. https://doi.org/10.1162/jocn.2007.19.9.1498

课程实验使用的整理版本为 [Kaggle — OASIS Alzheimer's Detection Multi-Class Dataset](https://www.kaggle.com/datasets/shreyanmohanty/oasis-alzheimers-detection-multi-class-dataset)，资料卡标示：

- 基于 OASIS-1，整理成四个失智程度类别。
- 影像经过裁切／缩放，并含 Roboflow 扩增版本。
- DOI：[`10.34740/KAGGLE/DSV/10215637`](https://doi.org/10.34740/KAGGLE/DSV/10215637)
- 衍生资料集授权标示为 CC BY-NC-SA 4.0。

### 为什么仓库不含 MRI 与 metadata

OASIS 的[资料使用条款](https://sites.wustl.edu/oasisbrains/home/access/)包含安全保存、禁止重新识别、研究用途与引用要求；衍生 Kaggle 资料亦有限定非商业与相同方式分享的授权。为了避免重新散布影像、受试者层级 metadata 或产生授权误解，本仓库只保存程式与汇总结果。使用者应自行阅读并同意最新条款，从官方／资料集页面取得资料。

OASIS 致谢文字应依官方 Access 页面当时的最新版本填写；公开论文或报告时也应引用 OASIS-1 原始论文。
