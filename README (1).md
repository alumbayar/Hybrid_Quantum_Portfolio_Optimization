
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
  - Must pass a Sharpe ratio threshold
  - Must respect minimum 5-day holding periods
  - Encourages sector diversification

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
├── strategy_weights_soft_sector.csv                      # Output portfolio weights (γ = 0.8)
├── strategy_weights_soft_sector_gamma_0.6.csv            # Additional results (γ = 0.6)
├── strategy_weights_soft_sector_gamma_0.9.csv            # Additional results (γ = 0.9)
├── synthetic_asset_prices.csv                            # ChatGPT-generated market data
├── ansatz.svg                                             # Circuit diagram (SVG)
├── README.md                                              # This file
├── .gitignore                                             # Optional
├── LICENSE                                                # Optional
```

---

## ⚙️ Dependencies

- `cirq`
- `scipy`
- `pandas`, `numpy`, `matplotlib`
- `tqdm`
- `seaborn` (optional, for visuals)

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

This work builds upon:
- Mugel et al. (2021) on hybrid quantum portfolio optimization [5]
- Rockafellar & Uryasev on CVaR [4]
- Quantum best practices by Buonaiuto et al. [3]
- Foundations: Markowitz [1], Sharpe [2]

AI-generated data and writing support via ChatGPT. All models, experiments, and conclusions by the author.

---

## ✅ Optional Files

- **`.gitignore`**: Add this to exclude common junk like `.ipynb_checkpoints/`, `__pycache__/`, `.DS_Store`, or large intermediate results.
- **`LICENSE`**: Use MIT or Apache 2.0 if you plan to open source your repo.

---

## 📥 Downloads

You may download key files here (once hosted on GitHub):

- [strategy_weights_soft_sector.csv](strategy_weights_soft_sector.csv)
- [strategy_weights_soft_sector_gamma_0.6.csv](strategy_weights_soft_sector_gamma_0.6.csv)
- [strategy_weights_soft_sector_gamma_0.9.csv](strategy_weights_soft_sector_gamma_0.9.csv)
- [synthetic_asset_prices.csv](synthetic_asset_prices.csv)
