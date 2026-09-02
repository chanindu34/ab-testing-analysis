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
✅ Simpson's Paradox check passed (no subgroup reversals)
✅ Chi-squared assumptions met (all expected frequencies > 5)
✅ Sample sizes large (high statistical power)

## Files

- `ab_testing_analysis.ipynb` - Complete analysis (Days 8-13)
- `day12_ab_testing_visualizations.png` - Publication-quality charts
- `DAY13_AB_TESTING_FINAL_REPORT.txt` - Executive report

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