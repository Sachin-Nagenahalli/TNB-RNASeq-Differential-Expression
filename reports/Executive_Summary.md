# Executive Summary: MP_403 RNA-seq Analysis

**Title:** Differential Gene Expression and Functional Enrichment Analysis of TNB and Normal RNA-seq Samples  
**Author:** Sachin Nagenahalli  
**Context:** Bversity Bioinformatics & Genomics Mini-Project (MP_403)  
**Primary Platforms:** Galaxy | R / Bioconductor  

---

## 🔬 Key Highlights at a Glance

| Metric / Dimension | Value | Description / Significance |
| :--- | :--- | :--- |
| **Total Samples** | **6 Samples** | 3 Normal controls (`Normal_1, 2, 3`) vs. 3 TNB replicates (`TNB_1, 2, 3`) |
| **Raw Gene Matrix** | **78,733 Genes** | featureCounts quantified transcriptomic profiles |
| **Differential Expression (DESeq2)** | **94 DEGs** | Filtered by $|\log_2\text{FC}| > 1.0$ and FDR adjusted $p$-value $< 0.05$ |
| **Upregulated in TNB** | **38 Genes** (40.4%) | Associated with proliferation, cell motility, and TNF signaling |
| **Downregulated in TNB** | **56 Genes** (59.6%) | Associated with normal differentiation, ESR1 signaling, and metabolic homeostasis |
| **PCA Variance Explained** | **88.02% (PC1+PC2)** | PC1: 75.59% (stark condition separation), PC2: 12.43% |
| **Top Upregulated Genes** | `GABRP`, `SLC6A14`, `MAPK15`, `CD44`, `FN1` | High oncogenic and migratory association |
| **Top Downregulated Genes** | `CA6`, `FBP1`, `ESR1`, `IGF1`, `KLF15` | Loss of hormone receptivity and normal metabolic controls |

---

## 📊 Summary of Major Figures

1. **Volcano Plot (`figures/94_DEG_volcano_plot.png`):** Shows prominent statistical separation with strong fold changes for key oncogenes and tumor suppressors.
2. **PCA Plot (`figures/PCA_DEGs_TNB_vs_Normal.png`):** 75.59% PC1 variance demonstrates distinct, clean grouping between Normal and TNB replicates.
3. **Heatmap (`figures/94_DEG_heatmap.png`):** Gene-wise Z-score standardized clustering highlights coordinated transcriptional shifts across all 94 DEGs.
4. **KEGG Pathway Dotplots (`figures/UP_KEGG_dotplot.png`, `figures/DOWN_KEGG_dotplot.png`):** Identifies TNF signaling, Ribosome, Phospholipase D, and NF-$\kappa$B pathways as leading exploratory targets.

---

## 💡 Key Biological Insights

- **Loss of Luminal/Estrogen Signatures:** Significant repression of `ESR1` and `FBP1` mirrors the classic molecular signature of Triple-Negative Breast Cancer.
- **Oncogenic Activation:** Strong upregulation of amino acid transporters (`SLC6A14`), cell adhesion/stemness markers (`CD44`), and extracellular matrix proteins (`FN1`).
- **Exploratory Pathways:** Candidate pathways including TNF signaling and Phospholipase D provide actionable hypotheses for targeted experimental validation.
