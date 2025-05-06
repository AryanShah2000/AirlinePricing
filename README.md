# Dynamic Airline Pricing & Overbooking Optimization

This repository contains a dynamic programming model to optimize airline ticket pricing and overbooking decisions across a 365-day sales horizon. The project models two ticket classes—Coach and First-Class—and evaluates multiple pricing and overbooking policies to maximize expected discounted profit while managing overbooking risk.

## Files Included

| File Name                      | Description                                                                 |
|-------------------------------|-----------------------------------------------------------------------------|
| `DynamicAirlineProgramming.ipynb` | Jupyter notebook implementing the dynamic programming model (Methodology 1). |
| `Project_Report.pdf`          | Full report detailing the problem, methodology, results, and recommendations. |

## Project Summary

Airlines often overbook coach seats to compensate for customer no-shows. While this can increase revenue, it also introduces risk when more passengers show up than seats available.

This project develops a dynamic programming framework to:
- Optimize daily ticket pricing decisions for Coach and First-Class.
- Model overbooking costs when more passengers show up than expected.
- Calculate expected profits over a full year (365 days) using backward induction.
- Evaluate how different overbooking levels (0 to 15 seats) impact profitability.

## Methodology

- Two ticket classes:
  - Coach: 100 seats, with up to 5–15 allowed overbooked.
  - First-Class: 20 seats, no overbooking.
- Daily decisions: Set price for each class from two options (e.g., $300 or $350).
- Stochastic demand: Sale probabilities depend on price and availability.
- Customer behavior:
  - Coach demand increases when First-Class is sold out (+3%).
  - Show-up probabilities: 95% (Coach), 97% (First-Class).
- Cost structure:
  - Bump to First-Class: $50
  - Bump off the flight: $425
- Discounting: 17% annual rate, applied daily.

## Results

- Without overbooking: Baseline expected profit ≈ $40,654.
- With 5 overbooked coach seats: Profit increases to ≈ $41,886.
- Peak profit: Achieved at 9 overbooked coach seats (≈ $42,135).
- Overbooking too much (>9 seats): Diminishing returns due to rising bumping penalties.

## Extensions (described in the report)

- Methodology 2: Adds a third decision — the ability to not sell a coach ticket on a given day.
- Seasonality: Modifies demand probabilities over time to reflect real-world fluctuations.
- Simulations: Monte Carlo simulations assess volatility, risk of bumping, and customer impact.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name

2. Open DyanmicAirlineProgramming.ipynb
3. Run the notebook to reproduce the value function, optimal policy details and key visualizations. 
