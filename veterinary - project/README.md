# Veterinary Clinical Intelligence — Companion Animal Dataset

A data analytics project combining veterinary domain expertise with Python to explore clinical patterns in companion animal medicine.

## Overview

The dataset consists of ~15,000 synthetic records for dogs and cats, generated using published prevalence statistics from **VetCompass UK** (n=22,333 dogs; n=142,576 cats) and **SAVSNET**. It covers 6 dog breeds and 5 cat breeds across a two-year period (2023–2024).

The data was intentionally seeded with **9 types of clinical data quality errors** — including impossible ages, breed-diagnosis mismatches, and sex-diagnosis conflicts — to simulate the kind of domain-specific issues that appear in real veterinary practice management systems. Identifying and resolving these errors requires veterinary knowledge that goes beyond standard data cleaning techniques.

## Project Structure

```
veterinary - project/
├── clinical-veterinary-project.ipynb     # Main analysis notebook
├── generate_dataset_executed.ipynb       # Dataset generation script (executed)
└── veterinary_clinical_data.csv          # Generated dataset
```

## Notebook Structure

- **Part A** — Data loading and initial exploration
- **Part B** — Domain-expert data cleaning (9 error types, 795 records removed)
- **Part C** — Exploratory data analysis (7 charts)

## Key Findings

- Dental disease is the leading diagnosis across all breeds and both species, consistent with VetCompass UK published prevalence data
- Breed-specific predispositions are clearly detectable — French Bulldog respiratory burden (18.2%), German Shepherd musculoskeletal load (20.6%), and Persian urinary prevalence (27%) all align with published clinical literature
- Outcome correlates strongly with severity: mild cases recover in nearly 100% of visits; referral and mortality appear exclusively in severe cases
- Urinary and dental conditions skew toward older animals; ear and dermatology cases present earlier in life

## Tools

Python · pandas · matplotlib · seaborn

## Dataset Methodology

Synthetic data parameterised from VetCompass/SAVSNET prevalence statistics. Breed-specific predispositions based on clinical expertise and published breed studies. Error types designed to require veterinary domain knowledge to detect and resolve.
