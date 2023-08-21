## RNA-seq 笔记

### 1. 样品准备 (Sample Preparation)
- **RNA 提取 (RNA Extraction)**
    - Extract RNA from cells or tissues
- **RNA 质量检查 (RNA Quality Check):**
    - 用电泳来检查 RNA 的完整性
- **cDNA 合成 (cDNA Synthesis)**
    - 使用reverse transcriptase将 RNA 转化为 cDNA
- **文库制备 (Library Preparation)**
    - Add adapters and amplify through PCR to create a sequencing-ready DNA library.

### 2. 测序 (Sequencing)
- 使用高通量测序技术（High-Throughput Sequencing）生成读段。

### 3. 质量控制 (Quality Control)
- FastQC
    -   对高通量测序数据进行质量控制分析。这个工具可以为用户提供测序数据的概览和详细的质量报告，帮助用户快速了解数据的质量状况。

### 4. 读段比对 (Reads Alignment)
- 使用 STAR 或 HISAT2 将读段比对到参考基因组。
- 使用 SAMtools 或 BAMtools 管理和排序比对结果。

### 5. 计数 (Quantification)
- 使用 featureCounts 或 HTSeq 计算每个基因或转录本的读段数。

### 6. 差异表达分析 (Differential Expression Analysis)
- 使用 DESeq2 或 edgeR 对不同条件或组的基因表达进行统计比较。
确定哪些基因的表达发生了显著变化。

### 7. 功能富集分析 (Functional Enrichment Analysis)
- 使用 DAVID 或 GOATools 进行 GO 富集分析。
    - >Gene Ontology Enrichment Analysis 是个生物信息学分析方法，用于确定某个基因集合中哪些生物过程、分子功能或细胞组成的 GO 术语被过度表示。Gene Ontology是个综合数据库，描述了基因产品的生物过程、分子功能和细胞组成。
- 使用 KEGG 进行通路分析

### 8. 数据可视化 (Data Visualization)
- ggplot2 进行差异表达的可视化。
    - [How to Use ggplot2-like libary in Python](https://towardsdatascience.com/how-to-use-ggplot2-in-python-74ab8adec129) plotnine is a Python package allowing you to use ggplot2-like code that is implementing the grammar of graphics
    -  ```conda install -c conda-forge plotnine```
- Gviz 或 IGV 对比对结果进行可视化。
