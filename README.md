# CSCN8020 Assignment 2 — Taxi Gymnasium with Q-Learning

**Student:** Liggia Elena Taboada Cruz
**Student ID:** 9085905 
**Course:** CSCN8020 — Artificial Intelligence and Machine Learning  
**GitHub:** https://github.com/liggiaelena/CSCN8020_Assignment2

---

## Project Summary

This assignment implements Q-Learning on the Taxi Gymnasium environment. The agent learns to navigate a 5×5 grid, pick up a passenger from one of four locations, and drop them off at the correct destination. The implementation uses an object-oriented architecture with six separated classes, trains across multiple hyperparameter configurations, and produces training metrics, comparison plots, and a log file.

---

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/liggiaelena/CSCN8020_Assignment2.git
cd CSCN8020_Assignment2

# 2. Create a virtual environment (recommended)
python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch Jupyter
jupyter notebook CSCN8020_Assignment2.ipynb
```

Run all cells from top to bottom. The notebook executes without errors and takes approximately 60–90 seconds.

---

## Repository Structure

| File / Folder | Description |
|---|---|
| `CSCN8020_Assignment2.ipynb` | Main Jupyter Notebook — full implementation and report |
| `training.log` | Auto-generated log file from all experiments |
| `plots/` | Generated plot images saved during training |
| `requirements.txt` | Python package dependencies |
| `README.md` | This file |
| `.gitignore` | Excludes virtual environments, cache, checkpoints |

---

## Q-Learning Implementation

The implementation follows the pseudocode from Sutton & Barto (2018), p.131, using six classes:

- **`TaxiEnvironmentManager`** — wraps the Gymnasium environment, handles reset/step/decode
- **`QLearningAgent`** — holds the Q-table, implements ε-greedy selection and the Q-Learning update rule
- **`QLearningTrainer`** — runs the episode loop connecting agent and environment
- **`MetricsLogger`** — collects per-episode metrics and writes the log file
- **`ExperimentRunner`** — orchestrates multiple named experiments for comparison
- **`PlotManager`** — generates all training and comparison plots

**Baseline hyperparameters:** α = 0.1, ε = 0.1, γ = 0.9, 2000 episodes  
**Best combination found:** α = 0.2, ε = 0.1, γ = 0.9

---

## References

Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.  
Gymnasium Documentation: https://gymnasium.farama.org/environments/toy_text/taxi/
