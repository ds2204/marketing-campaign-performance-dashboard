# Marketing Campaign Performance — Reproducible Findings

This report supersedes unsupported figures in the supplied report. All results below are computed from the included synthetic cleaned CSV, not measured business outcomes. Currency is unspecified in the generator; the dashboard uses a rupee display convention, not a documented currency conversion.

## Data quality

- Raw: 120 campaigns; cleaned: 104 campaigns.
- Missing cells: raw 0, cleaned 0.
- Duplicate rows: raw 0, cleaned 0.
- Sequential IQR filtering removes 16 records in total; synthetic extremes are not necessarily erroneous records.

## Portfolio results

- Spend: 3,827,129.31 synthetic currency units.
- Revenue: 12,220,508.86 synthetic currency units.
- Profit: 8,393,379.55 synthetic currency units.
- Weighted ROI: 219.31%.
- Impressions: 68,233,737; clicks: 1,974,933; leads: 131,291; conversions: 28,783.

## Platform totals

| Platform | Spend | Revenue | Weighted ROI |
|---|---:|---:|---:|
| Email | 518,129.12 | 1,486,055.00 | 186.81% |
| Facebook | 642,473.92 | 2,245,661.15 | 249.53% |
| Google Ads | 631,636.92 | 2,030,995.24 | 221.54% |
| Instagram | 673,218.18 | 2,837,592.33 | 321.50% |
| LinkedIn | 694,550.03 | 1,801,149.08 | 159.33% |
| YouTube | 667,121.14 | 1,819,056.06 | 172.67% |

## Methods and limitations

The fixed-seed generator creates 120 campaigns. Fields include campaign identifiers, type, platform, start/end dates, region, audience segment, impressions, clicks, leads, conversions, spend, revenue, ROI, CPC, CPM and acquisition cost. The generator validates metric formulas and exports CSV/JSON. The raw and cleaned CSV and dashboard JSON were compared during the audit.

The dashboard uses aggregate ratios. Monthly charts assign whole campaign totals to the start month. There is no daily revenue allocation, currency source, experiment, customer-level attribution model, trained predictor, or validated confidence interval. The forecast panel is a fixed what-if scenario; health scores and targets are heuristics. Prior score/trend claims were removed because no prior score dataset exists. Reallocation benefits are illustrative, not guaranteed incremental revenue.

The original generator couples some category assignments by modular indexing, so apparent differences can be confounded. No external commercial conclusions or annual savings are established by these data.

Run `node test_metrics.js` to validate portfolio totals. Run the generator in a disposable copy to reproduce supplied data. No GitHub Pages deployment for ds2204 has occurred. Original author credit and MIT notice remain in [ATTRIBUTION.md](ATTRIBUTION.md) and [LICENSE](LICENSE).
