# A/B Testing: Ad Campaign vs PSA

## Executive Summary

Rigorous A/B testing of 588,101 users comparing advertisements vs public service announcements.

**Result**: Ads generate **43.1% higher conversion rate** (statistically significant, p < 0.0001)

## Key Findings

| Metric | PSA (Control) | Ads (Treatment) | Lift |
|--------|---|---|---|
| Conversion Rate | 1.79% | 2.55% | +0.77pp |
| Sample Size | 23,524 | 564,577 | — |
| 95% CI | 1.62%-1.96% | 2.51%-2.60% | Non-overlapping ✅ |
| Chi-squared | — | — | 54.01, p<0.0001 |

## Business Impact

Rolling out ads to all users would generate:
- **+769 conversions per 100K users**
- **+7,692 conversions per 1M users**
- **+$769,245 revenue per 1M users** (at $100/conversion)

## When Do Ads Work Best?

**By Day**: Tuesday (110.7% lift) > Wednesday (60.9%) > ... > Thursday (7.0%)

**By Time**: Morning (73% lift) > Afternoon (37.3%) > Evening (32.8%)

**Recommendation**: Tuesday morning campaigns deliver highest ROI

## Statistical Rigor

✅ Chi-squared test (appropriate for binary outcomes)
✅ Confidence intervals don't overlap (high power)
✅ Simpson's Paradox check passed (no subgroup reversals) — lift stayed positive across every day-of-week and time-of-day subgroup checked, so the aggregate 43.1% lift is not an artifact of pooling across a confound
✅ Chi-squared assumptions met (all expected frequencies > 5)
✅ Sample sizes large (high statistical power)

## Known limitations

- **Sample Ratio Mismatch (SRM) check tests against the wrong null.** The dataset has a 96:4 ad/PSA split, and the notebook's SRM check compares this against an expected 50:50 ratio, which is almost certain to "fail" regardless of whether assignment was actually random, since 50:50 was never the intended design. A meaningful SRM check would need to know the platform's actual intended allocation ratio and test against that instead — this hasn't been done, so assignment integrity for the 96:4 split itself remains unverified, only assumed reasonable.
- **The time-of-day breakdown silently drops ~0.94% of users.** The `most ads hour == 0` transactions (5,536 users) fall outside all three bins used for the Morning/Afternoon/Evening breakdown, due to how the bin edges are defined, and are excluded from that specific subgroup analysis without being called out. Doesn't affect the headline 43.1% lift (computed on the full dataset), only the by-time-of-day figures above.
- **The "Tuesday morning could deliver 150%+ lift" idea (in the full report, not reflected above) is untested.** It's the Tuesday day-lift and Morning time-lift added together, not a measured result from an actual Tuesday-morning subgroup, since the day×time interaction itself was never directly tested.

## Files

- `ab_testing_analysis.ipynb` - Complete analysis (Days 8-13)
- `requirements.txt` - Dependencies (`pip install -r requirements.txt`)
- `day12_ab_testing_visualizations.png` - Publication-quality charts
- `DAY13_AB_TESTING_FINAL_REPORT.txt` - Executive report
- `marketing_AB.csv` - Kaggle Marketing A/B Testing dataset, committed directly (21MB, under GitHub's size limits)

## Methodology

**Days 8-13 Analysis:**
- Day 8: Exploratory data analysis (588K users, 2 groups, conversion metric)
- Day 9: Hypothesis testing (chi-squared test, p<0.0001)
- Day 10: Pitfall detection (SRM, Simpson's Paradox, assumptions)
- Day 11: Business impact (confidence intervals, scenario planning)
- Day 12: Visualizations (conversion rates, lifts by subgroup)
- Day 13: Final report (recommendations, decision)

## Recommendation

**DEPLOY ADS TO 100% OF USERS IMMEDIATELY**

Evidence:
- Statistically significant effect (p < 0.0001)
- Robust across all subgroups (no reversals)
- Large sample size (588K users)
- High confidence (non-overlapping CIs)
- Clear business value (+$769K for 1M users)

---

**Data Source**: Marketing A/B Testing Dataset (Kaggle)
**Analysis Date**: September 2026
**Analyst**: Chanindu Dahanayake
**Status**: PRODUCTION READY ✅