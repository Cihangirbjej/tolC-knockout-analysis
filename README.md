# tolC-knockout-analysis
BIO 340 Project: CRISPR knockout of tolC in E. coli and antibiotic sensitivity analysis
# CRISPR Knockout of *tolC* in *E. coli* – BIO 340 Project

This repository contains the full report, data, figures, and code for our BIO 340 project investigating the role of the *tolC* gene in antibiotic resistance in *Escherichia coli* using CRISPR-Cas9.

## 🧪 Project Overview
Antibiotic resistance is a major global health issue. The *tolC* gene encodes an essential outer membrane channel in the AcrAB-TolC efflux pump system, which contributes to bacterial resistance by exporting antibiotics out of the cell.

We hypothesized that a CRISPR-mediated knockout of *tolC* would significantly increase *E. coli* sensitivity to multiple antibiotics.

## 📂 Contents
| File | Description |
|------|-------------|
| `BIO340_Project2_Full_Report.docx` | Final manuscript, includes embedded figures |
| `Supplementary_Data_Tables.xlsx` | Raw OD600 growth curves and inhibition zone measurements |
| `Figure_1_PCR_Gel.png` | Simulated gel image confirming *tolC* knockout |
| `Figure_2_Inhibition_Zones.png` | Bar chart comparing WT and ∆tolC antibiotic sensitivity |
| `tolC_knockout_analysis.py` | Python script for statistical analysis and figure generation |
| `antibiotic_sensitivity_summary.csv` | Summary of inhibition zone stats with p-values |
| `antibiotic_sensitivity_comparison.png` | Output figure from Python script |

## 🧬 Methods Summary
- CRISPR-Cas9 was used to knock out the *tolC* gene in *E. coli* DH5α.
- Colony PCR confirmed gene deletion.
- Disk diffusion assays were performed using tetracycline, erythromycin, and chloramphenicol.
- Growth curves verified that knockout did not affect general viability.
- Analysis was done in Python using `pandas`, `matplotlib`, and `scipy`.

## 📈 How to Run the Analysis
Make sure you have Python 3.8+ installed, then:

```bash
pip install pandas matplotlib scipy
python tolC_knockout_analysis.py
```

This will output:
- `antibiotic_sensitivity_summary.csv`
- `antibiotic_sensitivity_comparison.png`

## 🔬 Citation
- CDC (2019). Antibiotic Resistance Threats Report
- Li et al. (2015). Clinical Microbiology Reviews
- Piddock (2006). Nature Reviews Microbiology

## 📬 Contact
For questions, feel free to reach out to [Your Name] at [your-email@example.com].
