# A changing astrocyte niche for *Spp1*-positive microglia in ageing and amyloid pathology

Analysis code for the Brief Research Report by Steger et al. (Frontiers in Network Physiology, 2026).
The notebooks reproduce all figures, statistics and supplementary tables of the paper.

## Data

| Cohort | Source | Folder expected by the notebooks |
|---|---|---|
| Own cohort (Xenium, 247-gene panel): WT 12 mo, WT 3 mo, AQP4 KO 3 mo | Zenodo: https://doi.org/10.5281/zenodo.XXXXXXX (`own_cohort_xenium_247panel.h5ad`) | `data/` |
| Public Xenium cohort: WT 2.5, 5.7, 13.4 mo and TgCRND8 2.5, 5.7, 17.9 mo | 10x Genomics, "Xenium In Situ Analysis of Alzheimer's Disease Mouse Model Brain Coronal Sections from One Hemisphere Over a Time Course" (CC BY 4.0). Download the six output bundles. | `data/Xenium_V1_FFPE_*_outs/` |
| Public CosMx cohort: four 4 mo and four 24 to 25 mo WT mice | SenNet Aged Mouse Brain Spatial Transcriptomics Collection, https://doi.org/10.60586/SNT249.TPCD.565 (run 2, files `05_Schafer_F1_236_YF01` to `08_Schafer_F4_243_YF04`) | `age_nature_dataset/` |

Cell-type labels of the public Xenium cohort as used in the paper are also on Zenodo (`public10x_celltype_labels.csv`).

## Folder layout

```
repository/
├── notebooks/            analysis notebooks
├── data/                 own cohort (.h5ad) and the six 10x bundles (download, not tracked)
├── age_nature_dataset/   CosMx files
├── tables/               written by the notebooks
├── figures/              written by the notebooks (drafts and panels)
└── final_data/           written by the notebooks (final figures and supplementary tables)
```

Data and output folders are not tracked by git. The notebooks use the parent folder of `notebooks/` (the repository root) as project folder.
To use another location, set the environment variable `SPP1_PROJECT_DIR`.

## Notebooks

Run each notebook in a fresh kernel, in this order:

| Notebook | Content | Output |
|---|---|---|
| `03_robustness_own_cohort.ipynb` | Robustness analyses of the own cohort (interaction, composition, contact exclusion, radii) | tables Z1 to Z5 |
| `01_own_cohort.ipynb` | Own cohort: statistics, Figure 2, Supplementary Figure S4 | Figure 2, Figure S4, Supplementary Table S2 |
| `05_cosmx_nature_aging.ipynb` | CosMx cohort: old age | Figure 3, Supplementary Table S4 |
| `02_public_xenium_WT_TgCRND8.ipynb` | Public Xenium cohort: midlife and amyloid pathology, summary across cohorts. Part A builds the annotated object once (label transfer), Part B runs the analyses. | Figures 1 and 4, Supplementary Tables S1, S5 |
| `04_supplement.ipynb` | Methods controls, identity control, per-animal results | Figures S1 to S3, Supplementary Tables S3, S6, S7 |

Notebook 02 (cell B7, Figure 4G) reads tables written by notebooks 01, 03 and 05, so run those first.

## Environment

```
conda env create -f environment.yml
conda activate spp1-niche
```

## Citation

Steger L, et al. A changing astrocyte niche for *Spp1*-positive microglia in ageing and amyloid pathology. Frontiers in Network Physiology (2026). [DOI will be added]

## License

Code: MIT (see `LICENSE`). Data on Zenodo: CC BY 4.0.
