# Alzheimer’s Medical AI

這是大學「人工智慧醫療」課程的作品整理，包含兩個阿茲海默症機器學習實驗：臨床表格資料的二元分類，以及腦部 MRI 的四分類。此專案用於學習與作品展示，**不是醫療器材，也不可用於臨床診斷或醫療決策**。

## 實驗成果

| 實驗 | 方法 | 評估方式 | 最佳結果 |
| --- | --- | --- | --- |
| 臨床表格分類 | 多模型比較，最佳為 XGBoost | Macro F1 | **0.9463** |
| MRI 四分類 | EfficientNet-B0、類別平衡、Focal Loss、TTA | 驗證集 Macro F1 | **0.9539** |

MRI 實驗在未使用 TTA 時為 0.9453；五次 TTA 後為 0.9539。以上是課程實驗結果，不代表對外部醫院或不同族群的泛化能力。

## 我做了什么

### 1. 临床与生活型态资料

- 完成资料清理、探索性分析、相关性与特征重要度分析。
- 比较 Logistic Regression、Random Forest、Gradient Boosting 与 XGBoost。
- 使用分层切分及 Macro F1，避免只看整体准确率而忽略类别表现。

![表格模型比较](results/tabular/model_comparison.png)

![XGBoost 混淆矩阵](results/tabular/confusion_matrix.png)

### 2. MRI 四分类

- 将目标分为 NonDemented、VeryMildDemented、MildDemented、ModerateDemented。
- 使用 EfficientNet-B0 迁移学习，并以抽样、类别权重、Focal Loss 与 label smoothing 处理类别不平衡。
- 分阶段解冻模型，并用 test-time augmentation（TTA）整合预测。
- 采用病人层级切分的衍生资料，降低同一受试者影像同时出现在训练与验证资料的风险。

![MRI 训练曲线](results/mri/training_curves_C.png)

![MRI TTA 混淆矩阵](results/mri/confusion_matrix_tta_C.png)

## 资料夹结构

```text
data/tabular/       可随专案发布的合成临床 CSV
notebooks/          两个实验的完整 Notebook
results/tabular/    表格实验图表
results/mri/        MRI 实验的汇总图表（不含原始 MRI）
docs/               资料来源、授权与公开检查说明
```

## 运行方式

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

表格 Notebook 可直接读取仓库内的 CSV。MRI Notebook 预期资料放在 `data/oasis-derived/`；请依 [资料来源说明](docs/DATA_SOURCES.md) 自行申请／下载，仓库不会重新散布 MRI 或受试者 metadata。

## 公开与引用

发布前请阅读 [DATA_SOURCES.md](docs/DATA_SOURCES.md) 与 [PUBLICATION_CHECKLIST.md](docs/PUBLICATION_CHECKLIST.md)。仓库内各资料不一定采用相同授权；临床 CSV 适用 CC BY 4.0，程式与课程内容的再授权则需另行确认。
