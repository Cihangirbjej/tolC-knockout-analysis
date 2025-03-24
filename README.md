# tolC-knockout-analysis
BIO 340 Project: CRISPR knockout of tolC in E. coli and antibiotic sensitivity analysis
# CRISPR Knockout of *tolC* in *E. coli* – BIO 340 Project

This repository contains the full report, data, figures, and code for our BIO 340 project investigating the role of the *tolC* gene in antibiotic resistance in *Escherichia coli* using CRISPR-Cas9.

Here is my full code for the project: 

# tolC_knockout_analysis.py
"""
Analysis of antibiotic sensitivity in tolC knockout E. coli strains.
Performs basic statistical comparison between wild-type and knockout strains
and generates visualizations.
"""

import pandas as pd
import matplotlib.pyplot as plt
import scipy.stats as stats

# Load data (can be replaced with CSV import if needed)
data = {
    'Antibiotic': ['Tetracycline', 'Erythromycin', 'Chloramphenicol'],
    'WT': [[8, 9, 8.5], [7, 6.5, 7.2], [10, 10.2, 9.8]],
    'KO': [[20, 19.5, 21], [18, 18.3, 17.5], [22, 21.8, 22.1]]
}

# Convert to DataFrame with mean and p-value calculations
summary = []
for i in range(len(data['Antibiotic'])):
    ab = data['Antibiotic'][i]
    wt = data['WT'][i]
    ko = data['KO'][i]
    t_stat, p_val = stats.ttest_ind(wt, ko)
    summary.append({
        'Antibiotic': ab,
        'WT Mean': round(sum(wt)/len(wt), 2),
        'KO Mean': round(sum(ko)/len(ko), 2),
        'p-value': round(p_val, 5)
    })

summary_df = pd.DataFrame(summary)
print("\nAntibiotic Sensitivity Comparison:")
print(summary_df)

# Plot bar graph
labels = data['Antibiotic']
wt_means = [sum(x)/len(x) for x in data['WT']]
ko_means = [sum(x)/len(x) for x in data['KO']]
x = range(len(labels))

plt.figure(figsize=(8, 5))
plt.bar([i - 0.2 for i in x], wt_means, width=0.4, label='WT')
plt.bar([i + 0.2 for i in x], ko_means, width=0.4, label='ΔtolC')
plt.xticks(x, labels)
plt.ylabel('Zone of Inhibition (mm)')
plt.title('Antibiotic Sensitivity: WT vs ΔtolC')
plt.legend()
plt.tight_layout()
plt.savefig("antibiotic_sensitivity_comparison.png")
plt.show()

# Save summary table
summary_df.to_csv("antibiotic_sensitivity_summary.csv", index=False)

print("\nResults saved to 'antibiotic_sensitivity_summary.csv' and figure exported as 'antibiotic_sensitivity_comparison.png'.")

