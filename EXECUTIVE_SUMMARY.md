# Executive Summary
## European Football Transfer Market Analysis

**Tools:** R, Quarto, Tableau  
**Study period:** 2009–2021  
**Coverage:** Seven major European leagues  
**Analytical sample:** 7,203 paid incoming player transfers

## Purpose

European football transfer fees are shaped by league purchasing power, player characteristics, and changing market conditions. This project examines how paid transfer fees evolved across seven major European leagues from 2009 through 2021 and evaluates whether fees differ systematically by league, player age, and position.

The analysis was designed to support recruitment and financial-planning decisions. Specifically, it helps distinguish broad market inflation from the influence of exceptional deals, identify league-specific fee benchmarks, and clarify which player profiles command higher transfer prices.

## Data and methodology

The source dataset contains 70,006 raw football-transfer records and 23 variables covering player attributes, club context, transaction details, transfer windows, and fees. To create a comparable analytical sample, the data were restricted to incoming transfers—the acquiring club's perspective—and filtered to retain paid permanent acquisitions only.

Loans, loan-end records, retirements, free transfers, observations with missing fees, implausible player ages, and fee values above €222M were excluded. Detailed positions were consolidated into Forward, Midfielder, Defender, and Goalkeeper groups. The final dataset contains **7,203 paid incoming transfers** across the Premier League, La Liga, Serie A, Bundesliga, Ligue 1, Primeira Liga, and Eredivisie.

The analytical workflow was completed in R and Quarto. It includes data cleaning, exploratory analysis, Pearson correlation testing, ordinary least squares regression, quadratic age modeling, ANOVA model comparison, seasonal fee indices, and linear and log-linear trend models. A Tableau dashboard provides interactive exploration by aggregation, season, league, and position group.

## Key findings

### Transfer fees increased over the long run, but not steadily

Transfer fees rose materially between 2009 and 2021. The median paid transfer fee increased from **€2.50M** in 2009 to **€3.82M** in 2021, a 52.8% increase. Mean fees rose more sharply, from **€4.55M** to **€8.30M**, an 82.4% increase.

The difference between mean and median growth is meaningful. It shows that exceptionally expensive transfers increasingly influenced average market cost, while the fee for a typical paid transfer rose more moderately. The market reached its observed high point in 2019, when the median fee was €5.00M and the mean fee was €10.54M. Both measures declined in 2020 and again in 2021. The evidence therefore supports **long-run fee inflation with material seasonal volatility**, rather than uninterrupted annual growth.

The log-linear time model fit slightly better than the level model, with an adjusted \(R^2\) of 0.0431 compared with 0.0326. It estimates an average increase of approximately **8.75% per season** in transfer fees over the sample period. Season alone explains a modest share of individual fee variation, so this estimate should be interpreted as an aggregate market trend rather than a complete explanation of any individual transaction.

### The Premier League paid a persistent premium

The Premier League had the highest fee levels in the sample. Its estimated mean paid fee was **€11.75M**, and its median fee was **€6.75M**. In a league-based OLS model using the Premier League as the reference category, every other league had a statistically significant lower estimated mean fee (\(p < .001\) for all comparisons).

Relative to the Premier League, estimated mean fees were €3.68M lower in La Liga, €6.39M lower in Ligue 1, €6.58M lower in the Bundesliga, €6.58M lower in Serie A, €8.56M lower in Primeira Liga, and €9.80M lower in the Eredivisie. The Premier League premium is therefore evident in both mean-based regression estimates and the descriptive median comparisons.

This pattern should not be interpreted as proof that league membership alone causes higher fees. The model does not control for player quality, contract duration, wages, club revenue, buyer urgency, or negotiation conditions. It is best interpreted as a historical market benchmark showing that comparable fee expectations differ substantially by league.

### Transfer fees peak near prime age

The direct linear relationship between player age and transfer fee was not statistically significant (\(r = 0.0090\), \(p = 0.443\)). However, the quadratic age model fit significantly better than the linear-only model, \(F(1, 7200) = 65.46\), \(p < .001\). The fitted curve indicates an inverted-U relationship, with predicted transfer fees peaking at approximately **24.9 years of age**.

This result suggests that clubs pay the highest broad-market prices for players near their prime years, when they may offer a combination of current performance, experience, and remaining resale potential. Age alone explains only a small portion of transfer-fee variation, so this finding should complement—not replace—individual player evaluation.

### Forwards and midfielders command higher fees

Position-group results show clear differences in typical transfer cost. Forwards had the highest median fee, **€3.40M**, followed by midfielders at **€3.00M**, defenders at **€2.50M**, and goalkeepers at **€1.95M**. The same ranking appears in average fees: forwards averaged €7.83M, midfielders €6.58M, defenders €5.53M, and goalkeepers €4.13M.

This pattern supports position-aware recruitment budgets. Attacking roles—particularly forwards and midfielders—should generally be evaluated against higher expected fee ranges than defensive or goalkeeper targets, while still accounting for player-specific performance and contract context.

## Recommendations

The results support the following actions for recruitment and financial-planning teams:

1. **Use league-specific benchmarks.** A transfer price should be compared with the historical range for the buyer's league and relevant source market, rather than with a single Europe-wide average.
2. **Use both median and mean fee measures.** Median fees describe a typical paid transfer, while mean fees reveal the financial influence of high-value transactions. Both are needed to avoid overreacting to headline deals.
3. **Budget by position.** Build higher expected acquisition ranges for forwards and midfielders than for defenders and goalkeepers.
4. **Account for age-price dynamics.** Assess whether a target is approaching, within, or past the broad peak-fee range near age 25, while considering performance, injury risk, contract length, and resale potential.
5. **Inflation-adjust historical comparisons.** Update historical fee benchmarks for market-wide price movement before using them in current budget or valuation discussions.

## Dashboard and reproducibility

The accompanying Tableau dashboard allows users to explore total expenditure, transfer volume, mean or median fees, and the most-transferred position through filters for season, league, position group, and aggregation method. It includes fee trends by league, position-group comparisons, and age-based fee patterns.

The project is reproducible through a Quarto analysis file that generates two Tableau-ready datasets: a cleaned transfer-level file and a season-level inflation index. The repository also includes the Tableau packaged workbook (`.twbx`), a dashboard preview, and exported R figures that document the central analytical results.

## Limitations

The data cover seven European leagues from 2009 to 2021 and do not directly account for player performance, contract length, wages, release clauses, agent effects, club finances, bargaining power, or tactical needs. The sample intentionally excludes free transfers, loans, loan-end records, retirements, missing-fee transactions, and fees above €222M. The results describe patterns among comparable paid incoming transfers, not all player movement.

Transfer fees are highly right-skewed, and individual transaction prices remain influenced by many factors that are outside the model. The findings should therefore be used as market context and decision support, alongside player-level valuation models and current scouting information.

---

### Project links

- [Reproducible R/Quarto analysis](notebooks/transfer_market_analysis.qmd)
- [Tableau dashboard documentation](tableau/tableau_dashboard_link.md)
- [Dashboard preview](tableau/dashboard_preview.jpg)