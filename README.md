# Neonatal Pulse Oximetry Screening (POS) Equity in Ghana

A reproducible care-cascade simulation modeling how screening coverage and echocardiography referral capacity shape critical congenital heart disease (CCHD) detection across care tiers in Ghana.

## Clinical Anchor & Model Scope
* **Empirical Baseline:** Screening uptake, POS screen-failure rate, and echocardiogram completion parameters are anchored to published newborn pulse oximetry screening data from tertiary facilities in Accra, Ghana (Yao et al., *BMJ Global Health*, 2026; PMC12853520).
* **Modeled Equity Scenarios:** District Hospital and Rural/CHPS parameters (`pos_coverage`, `echo_completion_rate`, and `pos_sensitivity`) are illustrative scenario assumptions designed to evaluate structural bottlenecks across a standardized `10,000`-birth cohort—not empirical rural surveillance measurements.

## Key Findings
1. **Care-Tier Equity Gap (`cchd_cascade_by_care_tier.png`):** Under a constant underlying CCHD prevalence (`0.22%` among eligible births), modeled confirmed CCHD drops from **67.0%** in Urban Tertiary settings to **32.4%** in District Hospitals and **9.5%** in Rural/CHPS settings, driven primarily by unscreened infants (**55.0%**) and pre-echocardiogram loss to follow-up (**22.1%**).
2. **Paired Intervention Effect (`rural_what_if_cascade.png`):** Expanding Rural/CHPS screening coverage from `45%` to `80%` without strengthening echocardiography referral (`30%` echo completion) increases confirmed CCHD only modestly (`9.5%` to `16.8%`) while inflating pre-echo loss (`22.1%` to `39.2%`). Pairing `80%` screening coverage with `75%` echo completion raises confirmed CCHD to **42.0%**.

## Repository Structure
* `notebooks/chd_screening_cascade.ipynb` — End-to-end simulation model, conservation checks, scenario tables, and figures.
* `results/figures/` — High-resolution (`300 dpi`) stacked bar charts of cascade outcomes.
* `results/tables/` — Exported cohort counts and percentage shares across care tiers and Rural/CHPS interventions.

## Reproducibility
Install dependencies (`numpy`, `pandas`, `matplotlib`) and run `notebooks/chd_screening_cascade.ipynb` from top to bottom. Built-in conservation assertions verify that confirmed cases, pre-echo losses, false negatives, and unscreened misses sum to total true CCHD cases across every simulated tier.