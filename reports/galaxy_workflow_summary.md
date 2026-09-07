# Galaxy Processing Workflow & History Summary

**History:** `MP_403 — TNB vs Normal RNA-seq`  
**Direct Galaxy History URL:** [https://usegalaxy.org/u/sachinmn989/h/mp-403-tnb-vs-normal-rna-seq](https://usegalaxy.org/u/sachinmn989/h/mp-403-tnb-vs-normal-rna-seq)  
**Mini-Project:** MP_403  

---

## 🛠️ Complete Tool Pipeline

```mermaid
graph TD
    A[Raw Paired-End FASTQ Reads] --> B[FastQC: Quality Control Assessment]
    B --> C[fastp: Adapter Trimming & Quality Filtering Q>=20]
    C --> D[STAR: Splice-aware Genome Alignment to GRCh38]
    D --> E[featureCounts: Gene-level Read Quantification]
    E --> F[Galaxy136 Count Matrix: 78,733 Genes x 6 Samples]
    F --> G[DESeq2: Differential Expression Testing GLM/Wald Test]
    G --> H[Galaxy174 DESeq2 Results]
    H --> I[Galaxy176: 94 DEGs |log2FC|>1, padj<0.05]
    I --> J[Galaxy177: 38 Upregulated DEGs]
    I --> K[Galaxy178: 56 Downregulated DEGs]
    J --> L[Galaxy184 g:Profiler / R clusterProfiler: UP GO & KEGG]
    K --> M[Galaxy185 g:Profiler / R clusterProfiler: DOWN GO & KEGG]
```

---

## 📋 Galaxy Datasets and Output Files

| Galaxy Dataset ID | File Name | Type | Description |
| :--- | :--- | :--- | :--- |
| **Galaxy136** | `Galaxy136_count_matrix_78733_genes.tabular` | Raw Counts | Raw gene count matrix across all 6 samples (78,733 genes) |
| **Galaxy174** | `Galaxy174_DESeq2_results.tabular` | Statistics | Full DESeq2 statistical results table |
| **Galaxy175** | `Galaxy175_DESeq2_plots.pdf` | PDF Plots | Diagnostic dispersion, MA, and sample distance plots |
| **Galaxy176** | `Galaxy176_94_DEGs.tabular` | Filtered DEGs | Significant 94 DEGs ($|\log_2\text{FC}| > 1.0, \text{padj} < 0.05$) |
| **Galaxy177** | `Galaxy177_38_Upregulated.tabular` | Upregulated | 38 genes with $\log_2\text{FC} > 1.0, \text{padj} < 0.05$ |
| **Galaxy178** | `Galaxy178_56_Downregulated.tabular` | Downregulated | 56 genes with $\log_2\text{FC} < -1.0, \text{padj} < 0.05$ |
| **Galaxy184** | `Galaxy184_UP_gProfiler_GOSt.tabular` | Enrichment | g:Profiler GO and pathway enrichment for UP DEGs |
| **Galaxy185** | `Galaxy185_DOWN_gProfiler_GOSt.tabular` | Enrichment | g:Profiler GO and pathway enrichment for DOWN DEGs |
