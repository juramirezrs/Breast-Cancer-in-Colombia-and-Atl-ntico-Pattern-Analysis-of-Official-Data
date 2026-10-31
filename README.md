# Breast Cancer in Colombia and Atlántico — Pattern Analysis of Official Data 🎗️

## Language Note
This project is developed and written in Spanish.  
This README is provided in English for accessibility.

---

## Project Overview

Behind every number in a health report there is a woman, a family, and a wait.

This project analyzes breast cancer in Colombia, with a special focus on the department of Atlántico (Barranquilla's region), using official data from the Cuenta de Alto Costo (CAC) and DANE (national statistics office). It looks for patterns in detection, mortality, inequality between health regimes, waiting times and population aging.

The goal is to find where the health system is falling behind and what the data can (and cannot) tell us about it.

---

## Personal Motivation

My aunt lived through breast cancer, and so did my best friend's mother. Almost everyone knows someone affected. This project is dedicated to them and to all the women and families who have gone through it.

---

## Objectives

- Describe the burden of breast cancer in Colombia (2015–2025)
- Compare Atlántico with the national average and the Caribbean region
- Detect inequalities between health insurance regimes
- Evaluate stage at diagnosis, treatment and care waiting times
- Measure the demographic pressure of an aging female population (up to 2035)

---

## Research Question

**What patterns do the available official data show about breast cancer in Colombia and Atlántico, and what do they say about detection, care and inequality?**

---

## Hypotheses

- **H1.** Atlántico has higher reported new-case and mortality rates than the national average
- **H2.** Prevalence and reported cases grow from 2015 to 2025, but the share of women with breast cancer who die each year does not rise as fast
- **H3.** The subsidized regime reports fewer new cases but has more deaths per reported case (possible late or missed diagnosis)
- **H4.** Care waiting times exceed official targets, and are worse in the subsidized regime
- **H5.** Women aged 50–74 grow faster than the total female population

---

## Data Sources

### **Cuenta de Alto Costo (CAC), 2025 report**
- National series 2015–2025 (prevalence, reported new cases, mortality)
- Regions, health regimes and some departments (2025)
- Stage at diagnosis, subtypes, treatment and care waiting times

### **DANE, Vital Statistics**
- Non-fetal deaths by year, age, sex and area (all causes, national)

### **DANE, Population Projections**
- Women by 5-year age group, 2018–2070 (national)

---

## Methodology

### **1. Data Loading and Validation**
Automatic file lookup, schema checks, and an inventory of what each file does and does not contain.

### **2. Data Processing**
- Mapping age groups between files
- Using only the "Total" population rows (to avoid double counting)
- Flagging preliminary (2019) and partial (2026) figures

### **3. National Trend Analysis (2015–2025)**
- Prevalence, reported new cases and mortality
- Compound annual growth rate
- Deaths per 100 women living with the diagnosis

### **4. Age Standardization**
Direct method with the WHO standard population (Ahmad et al., 2001).

### **5. Pandemic Effect**
Comparison of all-cause female mortality (DANE) against the CAC cohort mortality.

### **6. Territorial Comparison**
Atlántico vs Colombia vs Caribbean region, plus a detection-vs-mortality map by region.

### **7. Inequality by Health Regime**
Contributory vs subsidized vs exception regimes, with 95% confidence intervals.

### **8. Clinical Profile and Care Timeliness**
Stage, subtype, treatment, and waiting times against official targets.

### **9. Demographic Pressure**
Growth of women at higher-risk ages up to 2035 (not a case forecast).

### **10. Automatic Conclusions**
Every figure in the findings is generated from the code, not typed by hand.

---

## Key Indicators

- **PCNR** → Reported new cases (not pure incidence)
- **Prevalence** → Women living with the diagnosis
- **Mortality (CAC)** → Deaths from *any cause* in women with breast cancer
- **Standardized rate** → Rate adjusted for age structure
- **Mortality per new case** → Standardized mortality ÷ standardized new cases

---

## Key Formulas

### **Age-standardized rate**

ASR = Σ ( w_i × d_i / n_i ) × 100,000

where w_i is the WHO standard weight, d_i the events and n_i the women in age group i.

### **Deaths per 100 prevalent women**

(crude mortality ÷ crude prevalence) × 100

### **Mortality per new case**

standardized mortality ÷ standardized reported new cases

### **Compound annual growth rate**

((last value ÷ first value) ^ (1 / years) − 1) × 100

---

## Main Findings

- **Atlántico is above the national average:** reported new cases ×1.32 and mortality ×1.36 (2025, standardized)
- **But its mortality is proportional to its cases:** the mortality-per-case ratio is almost the same as the national one (0.52 vs 0.50)
- **Burden is growing:** prevalence +12.3% per year and reported cases +6.9% per year (2015–2025)
- **Survival signal:** deaths per 100 women living with the diagnosis fell from 4.9 to 3.8
- **Inequality by regime:** the subsidized regime reports fewer new cases (21.4 vs 30.6) with similar mortality, so it has more deaths per case (0.60 vs 0.45)
- **Late detection:** 27.6% of new cases are diagnosed at stages III–IV
- **Long waits:** 108 days from first consultation to treatment (target ≤ 75); confirming the diagnosis takes 49 days in the subsidized regime vs 34 in the contributory (target ≤ 30)
- **Aging:** women aged 50–74 grow 18.1% by 2035, versus 4.4% for all women

### **Critical Insight**
Regions that report fewer cases have more deaths per case, which is consistent with part of the disease going undetected.

---

## Pandemic Effect

- All-cause female mortality was 38.9% higher in 2021 than in 2018–2019
- The CAC cohort mortality jumps in the same years
- **Interpretation:** the CAC mortality counts deaths from any cause, so it must not be read as breast cancer mortality

---

## Limitations

- CAC mortality is all-cause, not breast cancer (C50) mortality
- Reported new cases are not true incidence
- Atlántico has a single-year cut (2025), with no trend and no Barranquilla data
- DANE files are national and have no cause of death
- Aggregated data: comparisons are descriptive and do not prove causes
- Few years and few regions: correlations are hints, not proof

---

## Future Work ("Super Notebook")

- Breast cancer deaths (C50) by municipality from DANE microdata
- Population by department and municipality
- Full CAC tables by department (stage, waiting times)
- Joinpoint trend analysis and Poisson projection to 2035 with scenarios
- Decomposition of change: population growth vs aging vs risk
- Interactive dashboard

---

## Conclusion

The data show a growing burden, real territorial and insurance-regime inequalities, and waiting times above the targets.

**Key insight:**  
Behind every rate there is a person. Early detection and fast access to care are not abstract ideas: they can be **measured, compared and improved**.

---

*Educational project. This is not medical advice.*
