# Network Pharmacology Investigation of Lycium barbarum (Goji Berry) Metabolites against NAFLD

A network pharmacology study exploring how bioactive metabolites from Lycium barbarum (goji berry) exert therapeutic effects against Non-Alcoholic Fatty Liver Disease (NAFLD) through multi-target and multi-pathway mechanisms.

Author: Maryam Muarij

---

## 📌 Project Overview

Non-Alcoholic Fatty Liver Disease (NAFLD) affects 25–30% of adults globally and involves complex mechanisms including lipid metabolism dysregulation, insulin resistance, oxidative stress, and inflammation, making single-target treatments largely ineffective.

This study applies a network pharmacology approach to systematically investigate how 20 bioactive metabolites from *Lycium barbarum* interact with NAFLD-associated gene targets and biological pathways.

---

## 🌿 Bioactive Metabolites

20 metabolites selected via literature review from PubMed:

> Quercetin, Kaempferol, Luteolin, Hesperetin, Chrysin, Cyanidin, Apigenin, Arbutin, Patuletin, Citric Acid, Gallic Acid, Epicatechin, Catechin, Sinapinic Acid, LBP-1, Caffeic Acid, p-Hydroxybenzoic Acid, Ellagic Acid, Cinnamic Acid

---

## 🔬 Workflow

### 1. Disease Gene Identification
- NAFLD-associated genes retrieved from GeneCards
- 589 high-confidence genes retained using relevance score threshold ≥ 0.7

### 2. ADMET Filtering
- SwissADME — drug-likeness and pharmacokinetic properties (Lipinski's Rule of Five, bioavailability score ≥ 0.55, molecular weight < 500 Da)
- ProTox-II — toxicity prediction; metabolites with low toxicity (Class IV–V) retained

### 3. Target Prediction
- SwissTargetPrediction — protein targets predicted for each metabolite
- High-confidence predictions retained at probability threshold ≤ 0.7
- ~1,500 initial targets identified before filtering

### 4. Target Overlap
- Venny 2.1 — overlapping genes between NAFLD-associated genes and metabolite targets identified
- Common targets carried forward for network construction

### 5. PPI Network & Hub Gene Identification
- Common targets imported into STRING (confidence score > 0.4)
- Network visualized in Cytoscape
- Top 10 hub genes identified using CytoHubba plugin (degree centrality)
- Key hub genes: AKT1, MTOR, TNF, PPARA, PPARG, SIRT1, ESR1, EGFR, HSP90AA1, ALB

### 6. Functional Enrichment Analysis
- DAVID used for GO and KEGG pathway enrichment analysis
- GO analysis revealed involvement in lipid metabolism, inflammatory response, oxidative stress, and insulin signaling
- KEGG identified 34 pathways — top enrichments:
  - Adipocytokine signaling pathway
  - Insulin resistance
  - NAFLD pathway
  - FoxO signaling
  - AMPK signaling pathway

### 7. Integrated Network
- Metabolite–gene–pathway network built in Cytoscape
- Multi-level interactions between metabolites, gene targets, and enriched pathways visualized

---

## 📁 Repository Structure

```
NAFLD-Network-Pharmacology/
│
├── data/
│   ├── metabolites.xlsx                         # 20 Lycium barbarum bioactive metabolites
│   └── GeneCards-SearchResults.xlsx             # 589 NAFLD-associated genes from GeneCards
│
├── results/
│
│   ├── Targets_prediction+probability_check.xlsx # After SwissTargetPrediction cutoff
│   ├── Common_genes.xlsx                        # Overlapping targets from Venny 2.1
│   ├── Rank.xlsx                                # Top 10 hub genes by degree centrality
│   ├── metabolite_gene_pathway.xlsx             # Integrated network table
│   ├── String_interactions.xlsx                 # STRING PPI network data
│   ├── GO_MF_DIRECT.xlsx                        # GO Molecular Function (DAVID)
│   ├── GO_CC_DIRECT.xlsx                        # GO Cellular Component (DAVID)
│   ├── GO_BP_DIRECT.xlsx                        # GO Biological Process (DAVID)
│   └── KEGG_PATHWAY.xlsx                        # KEGG pathway enrichment (DAVID)
│
├── images/
│   ├── 10genes.png                              # Top 10 hub gene subnetwork (Cytoscape)
│   └── final_network.png                        # Integrated compound-target-pathway network
│   └── String_PPI.png                           #  PPI Network in STRING
│
└── README.md
```

---

##  Tools & Databases

| Tool / Database | Purpose |
|---|---|
| PubMed | Literature review for metabolite selection |
| GeneCards | NAFLD-associated gene retrieval |
| SwissADME | Drug-likeness & pharmacokinetic assessment |
| ProTox-II | Toxicity prediction |
| SwissTargetPrediction | Protein target prediction |
| Venny 2.1 | Overlapping target identification |
| STRING | PPI network construction |
| DAVID | GO and KEGG enrichment analysis |
| Cytoscape + CytoHubba | Network visualization & hub gene identification |

---

## 📊 Key Findings

- 20 bioactive metabolites from Lycium barbarum screened
- 589 NAFLD-associated genes identified
- 10 hub genes identified — AKT1, MTOR, TNF among the most critical
- 34 KEGG pathways enriched — top pathways linked to insulin resistance, lipid metabolism, and inflammation
- Integrated network reveals multi-component, multi-target therapeutic mechanism of goji berry against NAFLD

---

## 📸 Network Visualizations

### Hub Genes Network
![Hub Genes Network](images/10genes.png)

### Integrated Metabolite–Gene–Pathway Network
![Integrated Network](images/final_network.png)

---

## 📄 License

This project is for research and academic purposes. All data used were obtained from publicly available databases and published literature.
