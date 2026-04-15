# Structural Prediction and Cryo-EM Evaluation of CASP Target H1036

**Glycoprotein B – Neutralizing Antibody Complex (A₃B₃C₃) Using AlphaFold Multimer**


[![EM Map](https://img.shields.io/badge/EMDB-EMD--21247-green)](https://www.ebi.ac.uk/emdb/EMD-21247)

---

## Abstract

In this research study presented a comprehensive computational study of CASP15 target H1036, a hetero-9-mer complex of Glycoprotein B (gB) bound to a neutralizing antibody Fab fragment with A₃B₃C₃ stoichiometry (2,568 residues). Five structural models were generated using AlphaFold Multimer v3 via ColabFold, employing a protomer prediction strategy with C₃ symmetry expansion to accommodate memory constraints. Each model was evaluated against the experimental Cryo-EM density map EMD-21247 (~3.7 Å resolution) through cross-correlation (CC) analysis. The best-performing model achieved a CC of 0.6084, exceeding the approximate top CASP15 group score (~0.50). Notably, the AlphaFold confidence-based ranking (pLDDT) showed weak correlation with experimental map agreement (Pearson r = −0.108, p = 0.863), underscoring the necessity of independent experimental validation. Structural deviations were concentrated at chain termini, CDR loops, and inter-chain interfaces. These results demonstrate that AlphaFold Multimer can produce experimentally competitive models for large heteromeric antibody–antigen complexes, even under significant computational constraints.

Index Terms - AlphaFold Multimer, Cryo-EM, cross-correlation, CASP15, protein complex prediction, antibody–antigen modeling, structural bioinformatics, glycoprotein B

---

## Repository Contents

```
├── README.md                        # This file
│
├── input_sequences/
│   ├── complex.fasta                # Full A3B3C3 9-mer FASTA
│   └── protomer.fasta               # Single A:B:C protomer FASTA
│
├── models/
│   ├── protomers/                   # AlphaFold Multimer predicted protomers (A:B:C)
│   │   ├── rank_001_model_4.pdb
│   │   ├── rank_002_model_1.pdb
│   │   ├── rank_003_model_5.pdb
│   │   ├── rank_004_model_3.pdb
│   │   └── rank_005_model_2.pdb
│   │
│   └── full_complexes/              # C3-expanded A3B3C3 9-mer models
│       ├── H1036_A3B3C3_rank_001.pdb
│       ├── H1036_A3B3C3_rank_002.pdb
│       ├── H1036_A3B3C3_rank_003.pdb
│       ├── H1036_A3B3C3_rank_004.pdb
│       └── H1036_A3B3C3_rank_005.pdb
│
├── scores/                          # AlphaFold score JSONs (pLDDT, PAE, pTM, ipTM)
│   ├── scores_rank_001.json
│   ├── scores_rank_002.json
│   ├── scores_rank_003.json
│   ├── scores_rank_004.json
│   ├── scores_rank_005.json
│   └── predicted_aligned_error.json
│
└── figures/
    ├── msa_coverage.png             # MSA coverage plot
    ├── plddt_colabfold.png          # ColabFold pLDDT output
    ├── pae_colabfold.png            # ColabFold PAE output
    ├── pae_all_models.png           # PAE matrices for all models
    ├── plddt_per_residue_all_models.png  # Per-residue pLDDT profiles
    ├── model_rank001_fitting.png    # Model–map fitting visualizations
    ├── model_rank002_fitting.png
    ├── model_rank003_fitting.png
    ├── model_rank004_fitting.png
    ├── model_rank005_fitting.png
    ├── cc_ranking.png               # CC score ranking
    ├── plddt_iptm_vs_cc.png        # Correlation analysis
    ├── structural_deviations.png    # Deviation analysis
    └── best_vs_worst_comparison.png # Best/worst model comparison
```

---

## Target Information

| Property | Value |
|----------|-------|
| **CASP Target** | H1036 (CASP15) |
| **Complex** | Glycoprotein B (gB) – Neutralizing Antibody Fab |
| **Stoichiometry** | A₃B₃C₃ (hetero-9-mer) |
| **Chain A** | Glycoprotein B ectodomain (622 residues × 3) |
| **Chain B** | Antibody Heavy Chain VH (128 residues × 3) |
| **Chain C** | Antibody Light Chain VL (106 residues × 3) |
| **Total Residues** | 2,568 |
| **EM Map** | [EMD-21247](https://www.ebi.ac.uk/emdb/EMD-21247) (~3.7 Å) |

---

## Key Results

### Model Scores (AlphaFold Multimer v3)

| Rank | AF Model | pLDDT | pTM | ipTM | PAE (Å) |
|------|----------|-------|-----|------|----------|
| 1 | Model 4 | 58.8 | 0.372 | 0.140 | 24.8 |
| 2 | Model 1 | 45.6 | 0.321 | 0.144 | 27.1 |
| 3 | Model 5 | 42.1 | 0.353 | 0.133 | 26.5 |
| 4 | Model 3 | 40.3 | 0.238 | 0.155 | 28.0 |
| 5 | Model 2 | 20.6 | 0.163 | 0.135 | 28.7 |

### Cross-Correlation with EMD-21247

| CC Rank | AF Rank | CC Score | pLDDT |
|---------|---------|----------|-------|
| 1 | Rank 2 | **0.6084** | 45.6 |
| 2 | Rank 4 | 0.6048 | 40.3 |
| 3 | Rank 3 | 0.5964 | 42.1 |
| 4 | Rank 5 | 0.5963 | 20.6 |
| 5 | Rank 1 | 0.5917 | 58.8 |

---

## Methods Summary

- **Prediction:** AlphaFold Multimer v3 via ColabFold 1.6.1
- **Strategy:** Single A:B:C protomer (856 residues) → C₃ symmetry expansion → full A₃B₃C₃
- **Parameters:** 5 models, 1 recycle, MSA 32:64, single seed
- **Evaluation:** Cross-correlation against EMD-21247 using gemmi density sampling
- **Analysis:** pLDDT–CC correlation, structural deviations, best/worst comparison, CASP benchmarking

---

## Data Availability

- **EM Map:** [EMD-21247](https://www.ebi.ac.uk/emdb/EMD-21247) (not included due to size; 217 MB)
- **Predicted Models:** Included in `models/` directory
- **AlphaFold Scores:** Included in `scores/` directory


