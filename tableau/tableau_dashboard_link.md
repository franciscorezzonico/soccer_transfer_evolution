# Tableau Dashboard

## Soccer Transfer Evolution

**Project:** European Football Transfer Market Analysis  
**Dashboard:** Soccer Transfer Evolution  
**Coverage:** Seven European leagues, 2009–2021  
**Data:** 7,203 paid incoming player transfers after cleaning  
**Tools:** Tableau, R, and Quarto

## Interactive dashboard

[Open the interactive Tableau dashboard](https://public.tableau.com/views/SoccerTransferEvolution/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

The interactive dashboard supports filtering by:

- Aggregation method: median or mean transfer fee
- Season
- League
- Position group

It includes key performance indicators for total transfer expenditure, transfer fee, transaction volume, and the most-transferred position. The visual views show transfer-fee patterns by league and season, position group, and player age.

## Dashboard preview

![Dashboard preview](dashboard_preview.png)

*Dashboard preview shown with median aggregation, 2010 selected, all leagues, and all position groups.*

## Workbook file

The packaged Tableau workbook is available in this repository:

[`european_transfer_market_dashboard.twbx`](european_transfer_market_dashboard.twbx)

To explore or modify the workbook locally:

1. Download the `.twbx` file.
2. Open it in Tableau Desktop or Tableau Public.
3. If necessary, update the data source to the repository’s processed files:
   - `../data/processed/paid_incoming_transfers_clean.csv`
   - `../data/processed/transfer_fee_inflation_index.csv`

## Notes for visitors

This dashboard is part of a broader portfolio project that uses R and Quarto for data preparation and statistical analysis. The results describe historical patterns in paid incoming transfers and should be interpreted as market benchmarks, not as a complete causal player-valuation model.

For the full project context, see the repository [README](../README.md) and [executive summary](../EXECUTIVE_SUMMARY.md).