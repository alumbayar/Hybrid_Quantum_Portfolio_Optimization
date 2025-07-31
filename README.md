
# 🧠 Hybrid Quantum Portfolio Optimization with VQE-CVaR and Soft Sector Preferences

This project demonstrates a hybrid quantum-classical workflow for portfolio optimization, integrating the **Variational Quantum Eigensolver (VQE)** with **Conditional Value at Risk (CVaR)** and soft sector preferences. Using simulated asset data and realistic constraints such as minimum holding periods, the model showcases how quantum-inspired solvers can enhance financial decision-making.

---

## 🧩 Key Features

- **Hybrid VQE-CVaR Optimization**  
  A Variational Quantum Eigensolver is used to sample portfolio candidates under a CVaR-based risk objective.

- **QUBO Formulation with Constraints**  
  Portfolio encoding uses 18 qubits (2 bundle bits + 1 selector bit per asset) with terms representing:
  - Risk (covariance penalty)
  - Budget constraints (linear & quadratic)
  - OR-link logic for selector enforcement
  - Utility scoring (sector soft preferences)

- **Post-Selection with Sharpe and Holding Periods**  
  Classical post-processing filters candidates:
  - Must have high Sharpe ratio
  - Must respect minimum 5-day holding periods

- **Realistic Simulation Setup**  
  - 6 synthetic assets across 3 sectors
  - Data generated using ChatGPT to simulate 2 years of GEM-like prices
  - Time window: Jan–April 2025 (83 business days)

---

## 📈 Visualizations

- **Risk-Return Scatter Plots**  
  Showcases performance across different γ risk weights

- **Portfolio Composition Over Time**  
  Dynamic rebalancing visualized using stacked bar charts

---

## 📁 Repository Structure

```
Hybrid_Quantum_Portfolio_Optimization/
│
├── Hybrid_Quantum_Portfolio_Optimization_VQE_CVaR.ipynb  # Main notebook
├── strategy_weights_soft_sector.csv                      # Sample output portfolio weights
├── 5_strategy_weights.csv                                # Results (γ = 0.05)
├── 10_strategy_weights.csv                               # Results (γ = 0.10)
├── 15_strategy_weights.csv                               # Results (γ = 0.15)
├── 20_strategy_weights.csv                               # Results (γ = 0.20)
├── 40_strategy_weights.csv                               # Results (γ = 0.40)
├── 60_strategy_weights.csv                               # Results (γ = 0.60)
├── 80_strategy_weights.csv                               # Results (γ = 0.80)
├── 100_strategy_weights.csv                              # Results (γ = 1.00)
├── qubo_perf.csv                                         # Volatility and Profit for Quantum Simulated
├── random_perf.csv                                       # Volatility and Profit for Random Simulated
├── Two-Year_Synthetic_Asset_Price_Data.csv               # ChatGPT-generated market data
├── ansatz.svg                                            # Circuit diagram (SVG)
├── README.md                                              
```

---

## ⚙️ Dependencies

- `cirq`
- `scipy`
- `pandas`, `numpy`, `matplotlib`
- `tqdm`

---

## 🧪 How to Run

1. Open the notebook in Google Colab.
2. Run the full workflow:
   - Data generation
   - QUBO construction
   - VQE optimization
   - Post-selection
   - Plotting

---

## 🧠 Citation & Background

- [1] H. Markowitz, “Portfolio selection,” The Journal of Finance, vol. 7, no. 1, p. 77, Mar. 1952. doi:10.2307/2975974
- [2] W. F. Sharpe, “Capital asset prices: A theory of market equilibrium under conditions of risk,” The Journal of Finance, vol. 19, no. 3, pp. 425–442, Sep. 1964. doi:10.1111/j.1540-6261.1964.tb02865.x
- [3] G. Buonaiuto, F. Gargiulo, G. De Pietro, M. Esposito, and M. Pota, “Best practices for portfolio optimization by Quantum Computing, experimented on real quantum devices,” Scientific Reports, vol. 13, no. 1, Nov. 2023. doi:10.1038/s41598-023-45392-w
- [4] R. T. Rockafellar and S. Uryasev, “Optimization of conditional value-at-risk,” The Journal of Risk, vol. 2, no. 3, pp. 21–41, 2000. doi:10.21314/jor.2000.038
- [5] S. Mugel et al., “Hybrid quantum investment optimization with minimal holding period,” Scientific Reports, vol. 11, no. 1, Oct. 2021. doi:10.1038/s41598-021-98297-x

AI-generated data and writing support via ChatGPT. All models, experiments, and conclusions by the author.

