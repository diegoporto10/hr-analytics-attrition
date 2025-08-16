# HR Analytics — Attrition & Tenure (Power BI)

**Live artifacts**
- **Dashboard (PDF, 2 pages):** [`assets/HR-Attrition-Report.pdf`](assets/HR-Attrition-Report.pdf)
- **Overview (PNG):** [`assets/overview_1280x720.png`](assets/overview_1280x720.png)
- **Quick Wins (PNG):** [`assets/quickwins_1280x720.png`](assets/quickwins_1280x720.png)
- **PBIX:** [`assets/HR-Attrition-Overview.pbix`](assets/HR-Attrition-Overview.pbix)

**Highlights**
- Overall attrition **16.1%** (n=1,470); **Attrition Count: 237**
- Key drivers: **Overtime** (30.5%), **Travel Frequently** (24.9%), **Early Tenure <1y** (36.4%)
- Estimated **Cost of Attrition ≈ $3.08M** (assumes 2 months of salary to replace)
- **Quick wins:** Overtime guardrails, travel relief, early-tenure onboarding, role-specific playbooks

**Full case study:** [`docs/case-study.md`](docs/case-study.md)

---

## Tech
- Power BI (Power Query + DAX)
- Single-table model; calculated groups for **Age** and **Tenure**
- Key measures: `Attrition Count`, `Attrition Rate`, `Overall Attrition Rate`, `Cost of Attrition (est)`,
  and `Bar Color (Risk)` for above-average highlighting

```DAX
Attrition Count :=
COUNTROWS(FILTER('HRData','HRData'[Attrition] = "Yes"))
