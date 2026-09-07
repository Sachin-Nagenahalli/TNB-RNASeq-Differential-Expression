# MP_403: Differential Gene Expression and Functional Enrichment Analysis of TNB and Normal RNA-seq Samples

**Submitted by:** Sachin Nagenahalli  
**Context:** Bversity Bioinformatics / Genomics Project  
**Primary Platform:** Galaxy  
**Downstream Analysis:** R / Bioconductor  

---

## 📁 Project Directory Structure

```
MP403/
├── index.html                           # Interactive Web Dashboard (Live Plots, Tables, Report)
├── README.md                            # Project Overview & Navigation Guide
│
├── reports/                             # Comprehensive Project Reports & Summaries
│   ├── MP403_Full_Report.md             # Complete 9-section report extracted from PDF
│   ├── Executive_Summary.md             # High-level executive summary & key findings
│   ├── galaxy_workflow_summary.md       # Galaxy tools, parameters, & history manifest
│   └── MP403_full_report.pdf            # Original 26-page publication report PDF
│
├── data/                                # Structured Data Files & Tables
│   ├── counts/                          # Expression counts & coordinates
│   │   ├── 94_DEG_counts.csv            # Normalized count matrix for 94 DEGs
│   │   ├── 94_DEG_heatmap_zscore.tsv    # Gene-wise Z-score standardized values
│   │   ├── PCA_coordinates.csv          # 2D PCA coordinates (PC1: 75.59%, PC2: 12.43%)
│   │   └── Galaxy136_count_matrix_78733_genes.tabular # Raw matrix (78,733 genes x 6 samples)
│   ├── degs/                            # Differential expression result tables
│   │   ├── all_94_DEGs.csv              # Full dataset of 94 DEGs with DESeq2 statistics
│   │   ├── 38_upregulated_DEGs.csv      # 38 Upregulated genes (log2FC > 1.0, padj < 0.05)
│   │   ├── 56_downregulated_DEGs.csv    # 56 Downregulated genes (log2FC < -1.0, padj < 0.05)
│   │   ├── top_20_DEGs.csv              # Top 20 most significant DEGs
│   │   ├── top_20_DEGs_original.csv     # Unprocessed top 20 DEGs
│   │   ├── Galaxy174_DESeq2_results.tabular # Full DESeq2 output table
│   │   ├── Galaxy176_94_DEGs.tabular    # Galaxy filtered 94 DEGs
│   │   ├── Galaxy177_38_Upregulated.tabular # Galaxy 38 UP DEGs
│   │   └── Galaxy178_56_Downregulated.tabular # Galaxy 56 DOWN DEGs
│   └── enrichment/                      # Functional GO & KEGG pathway analyses
│       ├── UP_KEGG_pathways.csv         # KEGG pathways for upregulated genes
│       ├── DOWN_KEGG_pathways.csv       # KEGG pathways for downregulated genes
│       ├── UP_GO_exploratory.csv        # GO terms for upregulated genes
│       ├── DOWN_GO_exploratory.csv      # GO terms for downregulated genes
│       ├── ALL_DEGs_GO.csv              # Combined Gene Ontology enrichment across all 94 DEGs
│       ├── Galaxy184_UP_gProfiler_GOSt.tabular # Galaxy g:Profiler results for UP DEGs
│       └── Galaxy185_DOWN_gProfiler_GOSt.tabular # Galaxy g:Profiler results for DOWN DEGs
│
└── figures/                             # High-Resolution Publication Plots & Graphics
    ├── 94_DEG_volcano_plot.png          # High-resolution Volcano Plot
    ├── 94_DEG_heatmap.png               # Clustered Heatmap of 94 DEGs
    ├── PCA_DEGs_TNB_vs_Normal.png       # 2D PCA Scatter Plot
    ├── UP_KEGG_dotplot.png              # KEGG Pathway Dotplot (Upregulated)
    ├── DOWN_KEGG_dotplot.png            # KEGG Pathway Dotplot (Downregulated)
    └── Galaxy175_DESeq2_plots.pdf       # Galaxy DESeq2 Diagnostic Plots PDF
```

---

## 🔬 Key Project Results

- **Experimental Design:** 3 Normal control replicates vs. 3 TNB replicates.
- **Quantification:** 78,733 genes quantified via `featureCounts` from STAR-aligned BAMs.
- **Differential Expression:** **94 DEGs** ($|\log_2\text{FC}| > 1.0$, FDR adjusted $p < 0.05$):
  - **38 Upregulated DEGs** (e.g., `GABRP`, `SLC6A14`, `MAPK15`, `CD44`, `FN1`)
  - **56 Downregulated DEGs** (e.g., `CA6`, `FBP1`, `ESR1`, `IGF1`, `KLF15`)
- **PCA Separation:** PC1 accounts for **75.59%** and PC2 for **12.43%** of total variance (88.02% cumulative).
- **Pathways:** Leading exploratory pathways include **TNF signaling** (UP) and **Phospholipase D signaling / NF-$\kappa$B** (DOWN).

---

## 🌐 Running the Web Application

To open and interact with the web dashboard:
```bash
# Open directly in your default browser:
open index.html

# Or run a local HTTP server:
python3 -m http.server 8080
# then navigate to http://localhost:8080/index.html
```
