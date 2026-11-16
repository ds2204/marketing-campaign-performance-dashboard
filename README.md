# Marketing Campaign Performance Dashboard

An interactive HTML/CSS/JavaScript dashboard using Chart.js and synthetic campaign data, prepared for maintenance under **ds2204**. Original authorship and MIT copyright are retained in [ATTRIBUTION.md](ATTRIBUTION.md) and [LICENSE](LICENSE).

## Run

```sh
python3 -m http.server 8000 --directory docs
```

Open `http://localhost:8000`. HTTP serving is required because the dashboard fetches `data.json`. Chart.js and Google Fonts are loaded from external CDNs; an offline browser may not render all features.

To regenerate the supplied synthetic dataset with Python 3.12:

```sh
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python scripts/generate_data.py
```

The generator resolves paths relative to its source location. It creates 120 raw campaigns and applies sequential IQR filters, yielding the cleaned dataset used by the dashboard. Run it only when you intend to regenerate data. Raw and cleaned files are both retained.

## Features and analytical scope

Filters, campaign comparisons, weighted portfolio KPIs, funnel, regional/platform heatmap, monthly start-date aggregation, and executive scenario panels are implemented in `docs/script.js`. The supplied data contains 104 cleaned campaigns. Aggregate ROI is `(total revenue - total spend) / total spend`; CTR and conversion rate use aggregate numerators and denominators, not averages of percentages.

All amounts and business outcomes are **synthetic**. Platform, region and audience assignment follows generator rules; this is not a randomized causal experiment. Outlier filtering changes the observed distribution. Monthly charts attribute the full campaign totals to the start month, not daily recognized revenue.

The scenario panel uses fixed hypothetical multipliers (+9.8% revenue, +11% relative ROI, +10.2% conversions). It is not a fitted forecasting model; the former confidence percentage has been removed. Targets, scores and recommendations are illustrative heuristics, not validated performance claims.

[Project report](PROJECT_REPORT.md) contains recomputed findings. The [dashboard screenshot](screenshots/dashboard_overview.png) reflects the cleaned interface. No ds2204 live deployment is claimed. See [AUDIT.md](AUDIT.md) for checks and remaining limitations.
