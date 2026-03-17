# 🧠 Differential Gene Expression Analysis in Major Depressive Disorder (MDD)

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-orange)
![Data](https://img.shields.io/badge/Data-NCBI%20GEO-green)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## 📌 Overview
This project performs a complete **Differential Gene Expression (DEG) analysis**
on post-mortem human brain RNA-seq data from patients with Major Depressive 
Disorder (MDD) vs healthy controls.

The data is sourced directly from **NCBI GEO** using Python — no manual 
downloading, no Excel. Everything is reproducible from a single Colab notebook.

---

## 🧬 Dataset
| Field | Details |
|---|---|
| **GEO Accession** | GSE80655 |
| **Title** | RNA-sequencing of human post-mortem brain tissues |
| **Brain Region** | Dorsolateral Prefrontal Cortex (DLPFC) |
| **MDD Samples** | 23 |
| **Control Samples** | 24 |
| **Total Genes** | 57,905 (22,766 after filtering) |
| **Species** | Homo sapiens |
| **Data Type** | RNA-seq raw counts |

---

## 🔬 Pipeline
```
NCBI GEO (GSE80655)
        ↓
Metadata Extraction (281 samples)
        ↓
Filter → DLPFC + MDD + Control (47 samples)
        ↓
Expression Matrix (57,905 genes × 47 samples)
        ↓
Quality Filtering (22,766 genes remaining)
        ↓
DEG Analysis (Welch's t-test per gene)
        ↓
FDR Correction (Benjamini-Hochberg)
        ↓
107 Significant DEGs found
        ↓
Visualizations (Volcano, PCA, Heatmap, Boxplots)
```

---

## 📊 Results
| Category | Count |
|---|---|
| Total genes analyzed | 22,766 |
| Upregulated in MDD | 34 |
| Downregulated in MDD | 73 |
| Total significant DEGs | 107 |

### 🔝 Top Significant Genes
| Gene | Direction | p-value | Biological Role |
|---|---|---|---|
| SNTG2 | Upregulated | 0.0042 | Synaptic organization |
| NKG7 | Downregulated | 0.0076 | Immune/neuroinflammation |
| PRF1 | Downregulated | 0.0099 | Immune cell activity |
| SPX | Downregulated | 0.0171 | Stress neuropeptide |
| USH1C | Downregulated | 0.0055 | Neurological function |

---

## 📈 Visualizations
## 📈 Visualizations

### 🌋 Volcano Plot
![Volcano Plot](volcano_plot.png)
Shows all 22,766 genes — red = upregulated in MDD, blue = downregulated

### 🔵 PCA Plot
![PCA Plot](PCA_plot.png)
Sample clustering using top 1000 variable genes — PC1 explains 71.8% variance

### 🔥 Heatmap
![Heatmap](heatmap.png)
Hierarchical clustering of 107 significant DEGs across all 47 samples

### 📦 Boxplots
![Boxplots](boxplots.png)
Expression distribution of top 4 most significant genes

---

## ⚙️ Tools & Libraries
```python
GEOparse    # NCBI GEO data fetching
pandas      # Data manipulation
numpy       # Numerical operations
scipy       # Welch's t-test
matplotlib  # Plotting
seaborn     # Statistical visualizations
sklearn     # PCA and normalization
mygene      # ENSEMBL ID to gene name conversion
```

---

## 📁 Output Files
```
DEG_Final_Results.xlsx   ← Full results table with gene names
volcano_plot.png         ← Volcano plot
PCA_plot.png             ← PCA clustering
heatmap.png              ← DEG heatmap
boxplots.png             ← Top gene boxplots
```

---

## 🧠 Biological Interpretation
The DLPFC is the brain's emotion regulation center — reduced activity here
is a hallmark of MDD. Key findings:

- **Neuroinflammation** — immune genes (NKG7, PRF1) downregulated
- **Synaptic dysfunction** — synaptic genes (SNTG2) upregulated  
- **Stress response** — neuropeptide SPX downregulated
- **Mixed PCA signal** — consistent with MDD heterogeneity across patients

---

## References
1. NCBI GEO: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE80655
2. Bowling et al. (2017). PMID: 28754123
3. GEOparse: https://github.com/guma44/GEOparse

---

## 👤 Author
**Sakshi Lodhi**  
Biotechnologist | Bioinformatics | Computational Neuroscience  
🔗 LinkedIn | 🐙 GitHub
"""
