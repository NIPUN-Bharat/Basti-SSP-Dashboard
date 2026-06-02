# Basti SSP Dashboard
### NIPUN Bharat · School Support Program · District Basti, Uttar Pradesh

A single-file monitoring dashboard for tracking Foundational Literacy & Numeracy (FLN) assessment outcomes across schools in Basti district. Built for the NIPUN Team at Central Square Foundation.

---

## What it does

The dashboard pulls live data from a Google Apps Script backend and presents three views:

| Tab | What it shows |
|---|---|
| **Overview** | District-level KPI cards + block-wise and grade-wise performance tables |
| **School Level Overview** | Per-school proficiency, priority status, and subject-level drill-down |
| **Student Level Overview** | Per-student assessment records with literacy, numeracy, ORF, and focus competency |

---

## Files in this repo

| File | Purpose |
|---|---|
| `Monitoring_Dashboard_Basti_v17.html` | The full dashboard — open directly in any browser |
| `NIPUN_Basti_AppScript_v2.js` | Google Apps Script backend — paste into Apps Script editor |

---

## How to use

### Viewing the dashboard
Open the GitHub Pages link in any browser — no installation needed:
```
https://nipun-bharat.github.io/Basti-SSP-Dashboard/Monitoring_Dashboard_Basti_v17.html
```

### Enabling GitHub Pages (one-time setup)
1. Go to **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` · Folder: `/ (root)`
4. Click **Save** — the URL will be live within ~1 minute

---

## Data & Backend

All assessment data lives in a **Google Sheet** and is served via a **Google Apps Script** web app.

### Sheet structure
| Tab | Contents |
|---|---|
| `sheet1` | Raw Tangerine assessment exports — one row per student assessment |
| `Sheet2` | School master list — UDISE, school name, block, category |

### Apps Script setup
1. Open the Google Sheet → **Extensions → Apps Script**
2. Paste the full contents of `NIPUN_Basti_AppScript_v2.js`, replacing everything
3. Click **Deploy → Manage deployments → Edit → New version → Deploy**
4. Make sure access is set to **"Anyone"** (not "Anyone with Google account")
5. Copy the deployment URL and confirm it matches `SCHOOL_DATA_URL` / `STUDENT_DATA_URL` in the HTML

> Re-deploy with a **new version** every time you update the Apps Script. The URL stays the same.

---

## Key metrics & definitions

| Term | Definition |
|---|---|
| **Literacy %** | % of applicable literacy competencies passed (score ≥ 75% of max per competency) |
| **Numeracy %** | % of applicable numeracy competencies passed (score ≥ 75% of max per competency) |
| **NIPUN** | Literacy % ≥ 75 **AND** Numeracy % ≥ 75 |
| **Approaching** | Proficient in at least one subject but not both |
| **At Risk** | Below proficiency threshold in at least one subject |
| **ORF** | Oral Reading Fluency in correct words per minute (cwpm) |
| **ORF — G2 NIPUN** | ≥ 45 cwpm · Approaching: 30–44 · At Risk: < 30 |
| **ORF — G3 NIPUN** | ≥ 60 cwpm · Approaching: 45–59 · At Risk: < 45 |
| **High Priority school** | < 40% of students are NIPUN |
| **Medium Priority school** | 40–74% of students are NIPUN |
| **Low Priority school** | ≥ 75% of students are NIPUN |

---

## Filters available

- **Quarter** — Q1 (Apr–Jun) · Q2 (Jul–Sep) · Q3 (Oct–Dec) · Q4 (Jan–Mar)
- **Month** — narrows within the selected quarter
- **Grade** — All / Grade 1 / Grade 2 / Grade 3
- **School type** — All / Government / Private / etc.
- **Block** — All blocks or specific block (School & Student tabs)

---

## Updating the dashboard

### New assessment data
1. Append new rows to `sheet1` in the Google Sheet — no script changes needed
2. The dashboard re-fetches live on every page load

### New version of the HTML
1. Edit `Monitoring_Dashboard_Basti_v17.html` locally
2. Upload to this repo (**Add file → Upload files**)
3. GitHub Pages serves the new version within seconds

### New version of the Apps Script
1. Edit `NIPUN_Basti_AppScript_v2.js` locally
2. Paste into Apps Script editor, deploy as a **new version**
3. Upload the updated `.js` file to this repo for version tracking

---

## Built by

NIPUN Team · [Central Square Foundation](https://centralsquarefoundation.org)  
District: **Basti, Uttar Pradesh**  
Programme: **NIPUN Bharat — School Support Program**
