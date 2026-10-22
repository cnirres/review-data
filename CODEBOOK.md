# Codebook: `celi_panel_2010_2023.csv`

One row per state-year, 2010–2023. Shares and ratios are fractions (0.25 = 25 percent). Columns ending `_z` are min–max normalized over all 140 state-years, z(x) = (x − min) / (max − min), so they compare across states and years. Values are rounded to six decimals.

| Column | Definition |
|---|---|
| `country`, `country_name`, `year` | ISO 3166-1 alpha-3 code, name, year |
| **Indices** | |
| `celi` | Leverage index: (`trade_lev` + `fin_debt_lev`) / 2 |
| `ceei` | Exposure index: [`trade_exp_z` + (`finance_exp_z` + `debt_exp_z`) / 2] / 2 |
| `gap` | `celi` − `ceei`; positive where coercibility raises leverage above exposure |
| **Halves and pillars of CELI** | |
| `trade_lev` | Trade half: (`asym_trade_z` + `switch_trade_z`) / 2 |
| `fin_debt_lev` | Financial-obligations pillar: (`finance_lev` + `debt_lev`) / 2 |
| `asym_trade`, `asym_trade_z` | Asymmetric dependence: (`da_x` + `da_m`) / 2, and its normalized value |
| `switch_trade`, `switch_trade_z` | Portfolio concentration (trapped exposure): (`ed_x` × `hhi_dest` + `ed_m` × `hhi_src`) / 2, and its normalized value |
| `finance_lev` | z(ln(1 + `cfs` × `loan_stock_gdp`)) |
| `debt_lev` | z(ln(1 + `ccs` × `debt_exports`)) |
| **Exposure terms of CEEI** | |
| `trade_exp_z` | z((`ed_x` + `ed_m`) / 2) |
| `finance_exp_z` | z(ln(1 + `finance_stock_gdp`)) |
| `debt_exp_z` | z(ln(1 + `debt_exports`)) |
| **Inputs and coercibility adjustments** | |
| `ed_x` | Share of the state's exports going to China |
| `ed_m` | Share of the state's imports coming from China |
| `da_x`, `da_m` | Bilateral asymmetry, exports and imports: ln(the state's dependence on China / China's dependence on the state) |
| `hhi_dest`, `hhi_src` | Herfindahl–Hirschman index of export destinations and import sources other than China, shares rescaled to sum to one |
| `neff_dest`, `neff_src` | Effective number of partners other than China: 1 / HHI |
| `cfs` | China's share of the official loan commitments a state has accumulated from all official lenders, bilateral and multilateral. Set to 0 for Brunei and Singapore, which are outside OECD official-lending records |
| `ccs` | China's share of the state's bilateral official debt outstanding. Set to 0 for Brunei and Singapore (no sovereign external debt); observed 0 for Thailand; imputed for Malaysia (0.02968, the tenth percentile of the six observed states) |
| `loan_stock_gdp` | Stock of Chinese official loan commitments relative to GDP |
| `finance_stock_gdp` | The same stock including grants |
| `debt_exports` | Debt owed to China relative to exports of goods and services |
| `debt_source` | `IDS`: debt owed to China as reported in the World Bank's International Debt Statistics. `AidData_Combined`: accumulated from AidData loan commitments, guaranteed and non-guaranteed, for the four states IDS does not cover over 2010–2023 (Brunei, Malaysia and Singapore are outside it; Thailand's series on debt to China ends in 2003) |

Stocks of commitments are accumulated by perpetual inventory from 2000 with 10 percent annual depreciation, in constant 2023 US dollars.
