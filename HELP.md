# 📘 ICU Long-Term Outcomes — Interactive Sankey Explorer

*A User Guide*

This page explains how to use the interactive Sankey diagram tool for visualizing multimorbidity trajectories and
long-term outcomes of ICU patients.
The visualization is fully interactive and supports filtering by **admission type**, **sex**, **age group**, **CCI
calculation mode**, and **labeling mode**.

---

# 🔍 Overview

The Sankey diagram tracks patient distributions across several time points:

1. **Before admission**
2. **Hospital discharge**
3. **6 months post-discharge**
4. **1 year post-discharge**
5. **2 years post-discharge**

Each colored block represents a **CCI category** at that time point:

| CCI Category | Color                                                   |
|--------------|---------------------------------------------------------|
| 0            | <span style="color:rgb(31, 119, 180)">█</span> Blue     |
| 1–2          | <span style="color:rgb(44, 160, 44)">█</span> Green     |
| 3–4          | <span style="color:rgb(255, 127, 14)">█</span> Orange   |
| 5+           | <span style="color:rgb(214, 39, 40)">█</span>  Red      |
| Death        | <span style="color:rgb(148, 103, 189)">█</span>  Purple |

Flows between blocks show how patients transition from one category to another over time.

---

# 📊 How CCI is Calculated

The **Charlson Comorbidity Index (CCI)** is a weighted score that predicts 10-year mortality risk based on the presence of specific comorbid conditions. Each condition is assigned a weight reflecting its impact on mortality.

## Condition Weights

| Weight | Conditions |
|--------|-----------|
| **1 point** | Myocardial infarction, Congestive heart failure, Peripheral vascular disease, Cerebrovascular disease, Dementia, Chronic pulmonary disease, Connective tissue disease, Peptic ulcer disease, Mild liver disease, Diabetes without complications |
| **2 points** | Hemiplegia, Moderate/severe renal disease, Diabetes with complications, Cancer (any), Leukemia, Lymphoma |
| **3 points** | Moderate/severe liver disease |
| **6 points** | Metastatic solid tumor, AIDS/HIV |

## Age Factor

When age is included, additional points are added based on age decade:

| Age Range | Points Added |
|-----------|-------------|
| Under 50 | 0 |
| 50–59 | +1 |
| 60–69 | +2 |
| 70–79 | +3 |
| 80+ | +4 |

The **CCI Age factor** filter in this tool lets you choose whether to include or exclude the age component from the CCI score. Excluding age isolates the effect of comorbidities alone.

## Reference

Charlson ME, Pompei P, Ales KL, MacKenzie CR. A new method of classifying prognostic comorbidity in longitudinal studies: development and validation. *J Chronic Dis.* 1987;40(5):373-383. [DOI: 10.1016/0021-9681(87)90171-8](https://doi.org/10.1016/0021-9681(87)90171-8)

---

# 🎛 Filters

The tool allows five independent filters.
Each selection updates the Sankey plot immediately.

## 1️⃣ Sex 


* **All**
* **Female**
* **Male**

## 2️⃣ Age Group

* **All**
* **18–49**
* **50–59**
* **60–69**
* **70–79**
* **80+**

## 3️⃣ Admission Type
* **All**
* **Surgical**
* **Medical**


## 4️⃣ CCI Calculation Mode

* **Include age** — age contributes to the Charlson score
* **Exclude age** — Charlson score computed without age

## 5️⃣ Label Mode

* **Count** — shows patient counts only
* **Count & %** — shows both counts and percentages

---

# 🧭 Interacting with the Sankey Diagram

### 🔹 Hover

Move your mouse over nodes or flows to view:

* Number of patients in that category
* Percentage (if enabled)
* Transition counts between categories


### 🔹 Tooltips

Hovering nodes shows counts or count + percentage depending on selection.

---

# 🔗 Sharing a View

Every filter selection updates the browser URL dynamically:

```
? surg=VALUE & sex=VALUE & age=VALUE & isage=VALUE & label=VALUE
```

Copy & paste the full URL to share the exact same view with others.

Example:

```
https://yourdomain/index.html?surg=all&sex=female&age=70_79&isage=include_age&label=label_count
```

---

# 💾 Automatic State Saving

Your last selected filters are stored locally in the browser.
When re-opening the page:

* The saved configuration is restored
* Unless overridden by URL query parameters

---

# 🏷 Legend 

A legend shows the color assigned to each CCI category and death nodes.

---


