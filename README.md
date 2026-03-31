# Gross Profitability Factor Replication (Novy-Marx, 2013)

## Overview
This project replicates the Gross Profitability (GP/A) factor introduced in Novy-Marx (2013), "The Other Side of Value: The Gross Profitability Premium".

The objective is to evaluate whether firms with higher gross profitability relative to total assets generate superior stock returns.

---

## Business Context
Profitability-based signals are widely used in quantitative investing and asset pricing.

- Gross profitability is less affected by accounting distortions  
- It captures a firm’s core operating efficiency  
- It helps identify high-quality firms for portfolio construction  

Understanding this factor can improve risk-adjusted returns and investment strategies.

---

## Data
- Compustat Annual (fundamental data)
- CRSP Monthly (stock returns)
- CCM Link Table (merging datasets)

**Universe:**
- NYSE / AMEX / NASDAQ common stocks (shrcd 10, 11)
- Excluding financial firms (SIC 6000–6999)

**Sample Period:**
- July 1963 – December 2010

---

## Methodology

### Signal Construction
GP/A = (REVT - COGS) / AT

- REVT: Revenue  
- COGS: Cost of Goods Sold  
- AT: Total Assets  

---

### Portfolio Construction
- Annual rebalancing at end of June
- Use prior fiscal year accounting data (6-month lag)
- NYSE breakpoints for quintile sorting
- Construct:
  - Equal-weighted (EW)
  - Value-weighted (VW)
- Include delisting returns to avoid survivorship bias

---

## Results

### Return Patterns
- High GP/A firms (Q5) consistently outperform low GP/A firms (Q1)
- Stronger effect observed in equal-weighted portfolios
- Profitability premium becomes more pronounced after the 1990s

---

### Risk-Adjusted Performance

- HML_GP (Q5 − Q1) generates:
  - 3.61% annual return (VW)
  - 4.62% annual return (EW)

- Q5 portfolio achieves the highest Sharpe ratio

---

## Key Insights

- Profitability premium exists and is statistically significant  
- High GP firms outperform due to strong Q5 performance  
- Effect is stronger among smaller firms (EW > VW)  
- High GP firms behave like growth stocks (negative HML loading)  
- Replication closely matches original paper results  

---

## Validation & Robustness

- High correlation (~0.93) with WRDS signal  
- Consistent mean and distribution  
- Results robust across:
  - FF3 regression
  - B/M benchmark comparison  

---

## Extension: Portfolio Optimization

- Mean-variance optimization allocates 100% to Q5
- Sharpe ratio improves significantly vs equal-weighted portfolio

---

## Tools & Skills
- Python
- WRDS (SQL queries)
- Pandas / NumPy
- Financial econometrics
- Factor investing & backtesting

---

## Next Steps
- Extend analysis to post-2010 data  
- Combine GP/A with other factors (momentum, value)  
- Improve portfolio construction (transaction costs, turnover)  
