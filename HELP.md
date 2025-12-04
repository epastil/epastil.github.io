# 📘 ICU Long-Term Outcomes — Interactive Sankey Explorer

*A User Guide*

This page explains how to use the interactive Sankey diagram tool for visualizing multimorbidity trajectories and
long-term outcomes of ICU patients.
The visualization is fully interactive and supports filtering by **surgical status**, **sex**, **age group**, **CCI
calculation mode**, and **labeling mode**.

---

# 🔍 Overview

The Sankey diagram tracks patient distributions across several time points:

1. **Before admission**
2. **Hospital discharge**
3. **6 months after discharge**
4. **1 year after discharge**
5. **2 years after discharge**

Each colored block represents a **CCI category** at that time point:

| CCI Category | Color                                                   |
|--------------|---------------------------------------------------------|
| 0            | <span style="color:rgb(31, 119, 180)">█</span> Blue     |
| 1–2          | <span style="color:rgb(255, 127, 14)">█</span> Orange   |
| 3–4          | <span style="color:rgb(44, 160, 44)">█</span>  Green    |
| 5+           | <span style="color:rgb(214, 39, 40)">█</span>  Red      |
| Death        | <span style="color:rgb(148, 103, 189)">█</span>  Purple |

Flows between blocks show how patients transition from one category to another over time.

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

## 3️⃣ Surgical Status
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

### 🔹 Zoom and Pan

Use mouse scroll or touchpad pinch to zoom.
Click-and-drag to pan the view.

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


