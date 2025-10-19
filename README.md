# HNSCC_MultiOmics_Analysis.ipynb
Multi-omics bioinformatics analysis of TCGA Head &amp; Neck Squamous Cell Carcinoma (HNSCC) using Python. Includes RNA-seq preprocessing, gene expression profiling, and Kaplan–Meier survival analysis for CD44/CD24 biomarkers.
🧬 HNSCC Multi-Omics Analysis (TCGA RNA-seq + Clinical Data)
🎯 Project Overview

This project performs an integrated bioinformatics analysis of the Head and Neck Squamous Cell Carcinoma (HNSCC) cohort from The Cancer Genome Atlas (TCGA).
It combines RNA-seq expression, clinical metadata, and survival outcomes to identify and visualize prognostic biomarker patterns — with a focus on CD44 and CD24, two key genes linked to tumor aggressiveness and cancer stem-cell phenotype.

⚙️ Workflow Summary

Data Acquisition

RNA-seq (FPKM-UQ), clinical, and survival data downloaded from the UCSC Xena TCGA-HNSC dataset.

Files loaded into Colab via pandas with compression handling (gzip, tsv).

Preprocessing & Alignment

Cleaned and standardized sample barcodes across all datasets.

Merged expression, clinical, and survival tables for 520 common patients.

Verified consistent sample alignment using Python integrity checks.

Exploratory Analysis

Generated survival time distributions and expression variance histograms.

Visualized z-score normalized RNA-seq matrix using hierarchical clustering heatmaps (Seaborn).

Biomarker Selection (CD44/CD24)

Extracted normalized expression values for ENSG00000026508 (CD44) and ENSG00000137203 (CD24).

Created a combined biomarker table across 565 patients.

Performed scatter plot correlation between CD44 and CD24 expression (log₂ FPKM-UQ).

Survival Analysis

Merged biomarker and survival data using the lifelines library.

Conducted Kaplan–Meier survival analysis to compare high-CD44/low-CD24 vs. other subgroups.

Computed log-rank test (p-value ≈ 0.93, not significant) confirming comparable survival profiles between groups.

📈 Results & Visualizations

Heatmap: Top variable genes across TCGA-HNSC patients show clustered expression signatures.

Scatter Plot: Positive correlation trend between CD44 and CD24 expression.

Kaplan–Meier Curve: CD44_high/CD24_low subgroup shows slightly different survival trends but without statistical significance.

🧩 Biological Insight:
CD44 and CD24 co-expression suggests a potential interaction pattern in HNSCC, though survival correlation may require larger multi-omics validation.

🧩 Data Quality & Missing Values

The clinical dataset contains missing (NaN) entries for several exposure variables, which is expected in TCGA datasets.
These values reflect incomplete patient metadata — not processing errors.

Categorical fields (sample, disease_type, primary_site) are non-numeric and appear as NaN during summary.

Lifestyle exposure fields (years_smoked.exposures, pack_years_smoked.exposures) contain missing values for non-smokers or unreported cases.

Retaining these NaN values preserves data authenticity and aligns with TCGA’s real-world clinical completeness standards.

🧠 Tools & Technologies
Category	Tools/Libraries
Language	Python 3
Environment	Google Colab
Libraries Used	pandas, numpy, seaborn, matplotlib, lifelines, sklearn
Dataset	TCGA-HNSC (via UCSC Xena)
Analysis Type	RNA-seq normalization, survival analysis, biomarker correlation
🧪 Key Takeaways

Successfully integrated TCGA RNA-seq, clinical, and survival data for 500+ HNSCC patients.

Built reproducible bioinformatics pipeline for real-world cancer data.

Demonstrated visualization and survival modeling workflow for future biomarker validation projects.

📂 Repository Structure
HNSCC_MultiOmics_Analysis.ipynb     # Main analysis notebook
data/                                # (Optional) Input TSV files if shared
figures/                             # Saved heatmaps and plots
README.md                            # Documentation file

📚 References

The Cancer Genome Atlas (TCGA): https://portal.gdc.cancer.gov/

UCSC Xena Data Hub: https://xenabrowser.net/

Python Lifelines Documentation: https://lifelines.readthedocs.io

👩‍💻 Author

Zeel Vaghela
MSc Bioinformatics – Teesside University, UK
🔗 LinkedIn Profile: www.linkedin.com/in/zeel-vaghela
✉️ zjvaghela01@gmail.com
