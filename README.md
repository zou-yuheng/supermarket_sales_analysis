# Supermarket Sales Analysis & Forecasting

Based on real-world supermarket transaction data, this project addresses one core business question — *why do sales fluctuate so violently, and how can we allocate promotional, staffing, and inventory resources more precisely?* — through a complete analytical pipeline spanning data exploration, visual insight mining, and time-series forecasting, culminating in directly actionable operational recommendations.

> For the full narrative, slides, and chart-by-chart business commentary, see the presentation: `Course_presentation(Chinese_version).pdf` in the repository root.

## I · Issue — Business Problem

Weekly sales can swing from 1,000 to 7,000+, while undifferentiated promotions (sitewide sales year-round) create a "rush hours get more crowded, off-peak hours stay cold" pattern. This report answers: what drives the volatility, and how can promotion, staffing, and inventory deployment become more precise?

## M · Methodology — Core Approach

The core analytical model is the **ARIMA time-series forecasting** model, used to project the future sales trajectory. It is supported by three analysis paths:

- **Multi-dimensional statistical comparison**: sales structure broken down by city, product line, customer type (Member/Normal), and payment method (Cash/E-wallet/Credit card);
- **Time-trend decomposition**: daily and hourly sales trends to locate peak/off-peak windows and anomalous spikes;
- **Satisfaction distribution analysis**: rating frequency distribution, density plots, and box plots to quantify experience gaps across customer segments and payment methods.

## P · Product — Deliverables

- A Chinese-language business insight report for management (24-page slide deck + full analysis report PDF);
- 7 core analysis charts (city sales, daily/hourly trends, product lines, customer types, payment methods, satisfaction distribution, ARIMA forecast);
- Reproducible Python analysis code (Jupyter Notebook + scripts, dependencies managed with uv);
- An ARIMA-based future sales forecasting model with an assessment of its limitations.

## A · Actionable Insight — Recommendations

1. **Precision-matched promotions**: during off-peak windows, run "low-price traffic driving" (discounts, flash sales) to attract price-sensitive customers; during peak hours, focus on "value uplift" (bundle deals, premium product recommendations) to unlock spending power — replacing undifferentiated promotions.
2. **Dynamic resource allocation**: at the 13:00 and 19:00 peaks, restock hot items in advance and add customer-service/cashier staffing; during the 12:00 and 16:00–17:00 troughs, schedule rotations and training to optimize labor costs.
3. **Tiered category operations**: for leading categories (Food & Beverages, Electronic/Fashion Accessories), shift from scale-driven to "profit + stickiness" — exclusive supply-chain items and personalization; for mid-tier categories (Sports & Travel, Home & Lifestyle), activate dormant demand via cross-brand co-branded gift boxes and in-store experiential zones; for the trailing category (Health & Beauty), prune slow movers and lower the trial barrier with a "9.9-yuan sample box".
4. **Membership tiering and conversion**: member sales barely exceed normal customers' — tier members by spend/frequency with differentiated benefits to stimulate upgrade purchases; convert high-spending normal customers quickly via "spend X to earn membership" and first-order discounts for new customers.
5. **Satisfaction monitoring loop**: monthly ratings oscillate sharply between 6.0 and 8.6, indicating inconsistent experiences — attribute high/low rating episodes to underlying events and build a real-time satisfaction monitoring system with rapid response (proactive callbacks, compensation) at low points.
6. **Payment channel strategy**: cash is the most-used method, so keep traditional counters to serve the existing customer base; credit card users show the highest satisfaction (notably denser at 8–9 ratings), an advantage that can be amplified through co-branded bank benefits.

## C · Commercial Impact — Business Value

- **Revenue side**: normal-customer sales are nearly on par with members', signaling large low-cost conversion headroom — converting normal customers into members with bound-in benefits directly lifts repurchase rates;
- **Cost side**: concentrating resources on the two peak windows (13:00/19:00) instead of all-day coverage reduces stockout losses during peaks and idle labor during troughs;
- **Category side**: shifting leading categories from scale-driven to profit-driven lifts gross margin, while low-barrier trial products unlock dormant demand in trailing categories;
- **Decision side**: the ARIMA forecast's mild upward trend provides a baseline for long-term procurement and inventory planning, while the historical volatility (1,000 to 7,000+ within a single week) is identified as the top operating risk — pointing to the need for seasonal and exogenous variables to sharpen future forecasts;
- Concrete monetary quantification (e.g., uplift in average ticket size or GMV) should be validated via A/B data collection after the strategies are deployed.

---

## Data & Reproduction

- Data source: [Supermarket Sales Dataset](https://www.kaggle.com/datasets/faresashraf1001/supermarket-sales/data) by Fares Ashraf (Apache 2.0 License)
- Environment and dependencies are managed with [uv](https://docs.astral.sh/uv/): run `uv sync` to install dependencies, then execute `supermarket_analysis.py` or open `supermarket_analysis.ipynb` to reproduce the full analysis.
