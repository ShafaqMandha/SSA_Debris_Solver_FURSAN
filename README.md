# 🛰️ Analytics & Maneuver Optimization Toolkit by Team FURSAN

A collection of Jupyter notebooks, including ML-based collision-risk prediction, conjunction-event visualization, quantum-inspired maneuver optimization, and CDM preprocessing utilities.

## 📁 Repository Contents

- **SSA_ML.ipynb**  
  Complete machine-learning workflow for predicting satellite conjunction risk using CDM (Conjunction Data Message) data.  
  Includes data preprocessing, feature engineering, event-aware train–test splitting, and evaluation of:
  - CatBoost Regression  
  - XGBoost Classification (with grid search)  
  - Hybrid ML framework  
  - LRP baseline  
  Metrics include RMSE, MAE, R², Accuracy, F1, F2, MSEHR, and L-metric.  
  Contains plots, comparison tables, and reproducible evaluation setup.

- **SSA_Dashboard.ipynb**  
  Lightweight analytical dashboard for visualizing and tracking conjunction events.  
  Extracts latest CDMs, compares updates, and identifies historically similar events.  
  Provides:
  - Miss-distance trend plots  
  - 3D R–T–N geometry visualization  
  - Summary table of current active events  
  Easily extendable to CSV/XML ingestion and interactive dashboards (Dash/Panel).

- **SSA_Quantum.ipynb**  
  Quantum-annealing–based framework for Collision Avoidance Maneuver (CAM) optimization.  
  Formulates the maneuver decision problem as a QUBO with one-hot encoded Δv choices.  
  Benchmarks multiple solvers:
  - Exact  
  - Simulated Annealing  
  - D-Wave LeapHybrid (optional)  
  - Greedy baseline  
  Evaluates energy, Δv magnitude, remaining Pc, risk reduction, and computational cost.  
  Generates comparative plots and summary tables.

- **AldoriaToOEM.ipynb**  
  Utility for converting KVN-formatted CDM files into minimal OEM metadata stubs.  
  Extracts creation time, identifiers, maneuverability, and first Cartesian state vector.  
  Normalizes units and enforces:
  - `REF_FRAME = EME2000`  
  - `MANEUVERABLE = YES` unless explicitly “NO”  
  Produces OEM-compatible metadata + position entries for propagation and maneuver-scenario setup.

- **AldoriaToCorrected.ipynb**  
  Structured cleaner for KVN CDM files, producing standardized, filtered versions for ML and SSA workflows.  
  Removes comments, normalizes formatting, and retains essential metadata, state vectors, and covariance components.  
  Enforces:
  - `REF_FRAME = EME2000`  
  - `MANEUVERABLE = YES` (inserted if missing)  
  - Consistent `key = value` formatting.

## 🚀 Getting Started
Recommended libraries:
- numpy
- pandas
- matplotlib
- plotly
- scikit-learn
- catboost
- xgboost
- dwave-system (optional)
- dwave-neal

## 📝 Note
These notebooks were created as part of the Space Debris Solver Research Competition hosted by the Saudi Space Agency.
