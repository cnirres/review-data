# Inputs and how to obtain them

The CSV is built from the sources below. None is redistributed here.

| Source | Version used | Enters | How to obtain |
|---|---|---|---|
| UN Comtrade | retrieved February 2026 | `ed_x`, `ed_m`, `da_x`, `da_m`, `hhi_src` | [comtradeplus.un.org](https://comtradeplus.un.org/), free registration. Annual goods trade, all commodities, by partner, 2010–2023: each state's imports, and China's imports and exports |
| CEPII BACI, HS92 | release V202601 | `ed_x` (denominator), `hhi_dest` | [cepii.fr BACI page](https://www.cepii.fr/DATA_DOWNLOAD/baci/doc/baci_webpage.html), free (Etalab Open Licence 2.0) |
| AidData, China's Global Loans and Grants Dataset | version 1.0 | `loan_stock_gdp`, `finance_stock_gdp`, `cfs`; `debt_exports` for four states | [aiddata.org](https://www.aiddata.org/data/chinas-global-loans-and-grants-dataset-1-0), free |
| OECD Creditor Reporting System | release v20261006 | `cfs` (other official lenders) | [OECD Data Explorer](https://data-explorer.oecd.org/), free (dataflow `DSD_CRS@DF_CRS`) |
| World Bank, International Debt Statistics | retrieved December 2025 (debt to China) and March 2026 (all bilateral creditors) | `debt_exports`, `ccs` | [worldbank.org IDS](https://www.worldbank.org/en/programs/debt-statistics/ids), free (CC BY 4.0). Series `DT.DOD.BLAT.CD`, counterpart China (numerator) and World (`ccs` denominator) |
| World Bank, World Development Indicators | retrieved January–February 2026 | GDP, exports | [WDI DataBank](https://databank.worldbank.org/source/world-development-indicators), free (CC BY 4.0). Series `NY.GDP.MKTP.KD`, `NE.EXP.GNFS.CD`, `NY.GDP.DEFL.ZS` |
| CEIC Global Database | retrieved January 2026 | exports of Myanmar (all years) and Laos (2017–2023) | [ceicdata.com](https://www.ceicdata.com), subscription |

The dependence shares take each flow from the importer's record: each state's own imports, and China's imports from each state, converted from CIF to FOB by dividing by 1.10. Export destinations are read from partners' records as reconciled in BACI.
