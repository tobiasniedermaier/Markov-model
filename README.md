# COPD Markov model in R

R implementation of a German COPD Markov model for health-economic evaluation, including a benchmark reimplementation of the original Menn et al. model and a simplified version for future model updating.

This repository contains R code for a cohort Markov model of chronic obstructive pulmonary disease (COPD) for health-economic evaluation in Germany. The model is based on the published lifetime COPD Markov model by Menn et al. and was reimplemented in R to improve transparency, reproducibility, and future extensibility.

The repository includes two main model versions. The benchmark implementation reproduces the original model structure, including GOLD stages 1–4, lung volume reduction surgery, lung transplantation, mild, moderate and severe exacerbations, and death as the absorbing state. This version is intended to document and validate the translation of the original spreadsheet-based model into R.

The simplified implementation retains GOLD stages 1–4 and death, omits lung volume reduction surgery, lung transplantation, and mild exacerbations, and retains moderate and severe exacerbations as cycle-specific events. This simplified version was developed as a more parsimonious platform for future parameter updating and methodological extensions.

Both implementations use a 3-month cycle length and compare a smoking cessation intervention with usual care. The code includes deterministic calculations, discounted costs and effects, indirect costs, incremental cost-effectiveness calculations, graphical output, consistency checks, and probabilistic sensitivity analysis.

The code is provided for transparency and reproducibility. It is not intended to represent a fully updated cost-effectiveness analysis of a current COPD intervention. Updated parameter inputs, including COSYCONET-based mortality, lung-function decline, costs, utilities, and exacerbation inputs, are being documented separately as part of the staged model update process.

Files:
- Markov_model_Menn_Benchmark_Github_style_comments.r
Benchmark R implementation of the original COPD Markov model by Menn et al. This version retains the full original model structure, including lung volume reduction surgery, lung transplantation, mild exacerbations, moderate and severe exacerbations, and death. Comments indicate where code components are specific to the original model and are not present in the simplified implementation.

- Markov_model_simplified_Github_incl_checks.r
Simplified R implementation of the COPD Markov model. This version retains GOLD stages 1–4 and death, omits lung volume reduction surgery, lung transplantation, and mild exacerbations, and includes consistency checks for state occupancy and deaths. It serves as the main platform for future staged parameter updating.
Citation

The original model structure and parameterisation are based on:
- Menn P, Leidl R, Holle R. A lifetime Markov model for the economic evaluation of chronic obstructive pulmonary disease. Pharmacoeconomics. 2012;30(9):825–840.
- Menn P, Holle R. Comparing three software tools for implementing Markov models for health economic evaluations. Pharmacoeconomics. 2009;27(9):745–753.

The benchmark implementation is intended to reproduce the original model exactly. Therefore, some spreadsheet-specific conventions, boundary values, and rounding rules were retained deliberately.
