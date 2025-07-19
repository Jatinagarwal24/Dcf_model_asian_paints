# 📊 Discounted Cash Flow (DCF) Valuation Model for Asian Paints Ltd.

This repository contains a detailed **Discounted Cash Flow (DCF)** valuation model built in **Excel** to estimate the intrinsic value of **Asian Paints Ltd.** The model uses multi-year financial data collected from **Screener.in**, follows a bottom-up approach to forecast future **Free Cash Flow to the Firm (FCFF)**, and discounts it back to the present day to arrive at a **per-share intrinsic value**.

---

## 📈 Model Overview

The valuation is based on a **two-stage DCF model**:

-   **High-Growth Period (Years 1–5):** A 5-year explicit forecast period where cash flows are projected based on specific assumptions about revenue growth, margins, and reinvestment.
-   **Terminal Period:** A stable growth phase where the company is assumed to grow at a constant, perpetual rate, which is conservatively based on **India's long-term GDP growth rate**.

🔍 The final output of the model is an **intrinsic value per share**, which can be compared to the current market price to assess whether the stock is **overvalued**, **undervalued**, or **fairly valued**.

---

## 🗂️ Excel Model Structure

The workbook is organized into several sheets, each with a specific function:

-   **`Data Sheet` & `RAW FS`:** Contains historical financial statement data for Asian Paints – Profit & Loss, Balance Sheet, and Cash Flow statements.

-   **`WACC`:** Calculates the **Weighted Average Cost of Capital (WACC)** used as the discount rate:
    -   Cost of Equity via the **Capital Asset Pricing Model (CAPM)**.
    -   Bottom-up **Levered Beta** derived from a regression of stock returns vs. the **Nifty 50 index** for the top 5 listed industry peers (Berger Paints, Kansai Nerolac, Akzo Nobel, Indigo Paints).
    -   Cost of Debt, adjusted for the company's capital structure.

-   **`Intrinsic Growth`:** Calculates the company’s **fundamental growth rate** based on `ROIC * Reinvestment Rate`.

-   **`DCF`:** Core valuation sheet that projects future FCFF, discounts them, calculates the Terminal Value, and arrives at the **Intrinsic Value per Share**.

-   **`Peer Comp Sheets`:** Individual sheets for calculating **raw regression betas** of comparable companies against the Nifty 50 index using 2 years of weekly return data.

-   **`Rm`:** Calculates the **historical Equity Risk Premium (ERP)** for the Indian market.

---

## ⚙️ Valuation Methodology

The intrinsic value is determined using the following steps:

#### 1. Calculate Free Cash Flow to the Firm (FCFF)
```text
FCFF = EBIT * (1 - Tax Rate) - Reinvestment
```
#### 2. Calculate Discount Rate (WACC)
Using the market value of equity & debt, with the Cost of Equity derived from:
```text
Cost of Equity = Risk-Free Rate + (Levered Beta * Equity Risk Premium)
```
#### 3. Calculate Terminal Value (Gordon Growth Model)
```text
Terminal Value = [FCFF_final * (1 + Terminal Growth Rate)] / (WACC - Terminal Growth Rate)
```
#### 4. Calculate Intrinsic Value Per Share
```text
Enterprise Value = PV of projected FCFF + PV of Terminal Value
Equity Value = Enterprise Value - Debt + Cash
Intrinsic Value Per Share = Equity Value / Shares Outstanding
```
---
## 🔑 Key Assumptions & Inputs

The valuation is highly sensitive to these inputs, which are defined in the `DCF` and `WACC` sheets:

-   **Revenue Growth Rate:** Expected YoY increase in sales.
-   **NOPAT (EBIT * (1-Tax Rate)):** Operating margin after tax.
-   **Reinvestment Rate:** % of after-tax income reinvested.
-   **Risk-Free Rate (Rf):** Based on the 10-year Indian government bond yield.
-   **Equity Risk Premium (ERP):** Expected market return above the risk-free rate.
-   **Terminal Growth Rate (g):** Long-term perpetual growth rate, conservatively assumed based on India's GDP growth prospects.

---

## 🚀 How to Use the Model

1.  Review the **`Data Sheet`** and **`RAW FS`** for historical financials.
2.  Examine the **`WACC`** sheet to understand how the discount rate is derived.
3.  Analyze the **`Intrinsic Growth`** sheet for ROIC & reinvestment assumptions.
4.  Go to the **`DCF`** sheet for the main valuation summary.
5.  To run sensitivity analysis, adjust key inputs like growth rates and the discount rate to see how the intrinsic value responds to changes.

---

### 📌 Disclaimer
This model is for educational and illustrative purposes only and should not be considered as financial or investment advice. Please conduct your own research before making any investment decisions.
