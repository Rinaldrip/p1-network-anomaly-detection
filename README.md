# P1 - Network Anomaly Detection

**Problem:** can anomalous network traffic be detected before users report it?

**Why it matters:** early detection of traffic anomalies reduces downtime and security incidents for IT operations.

## Method
1. Clean and parse raw flow data
2. Build features per time window
3. Compare Isolation Forest, a simple autoencoder, and fixed rules
4. Evaluate precision/recall on labeled attacks and false positives per day

## Data
| Dataset | Use |
|---|---|
| CIC-IDS2017 (flow CSVs) | Main training and evaluation |
| UNSW-NB15 | Check that the model generalizes |
| Loghub (OpenSSH) | Optional system-log variant |

Raw data goes in `data/raw/` and is not versioned. See `data/raw/.gitkeep` for the expected location.

## Structure
```
data/          raw (not versioned) and processed data
notebooks/     exploration notebooks
src/           reusable code (loading, features, models)
tests/         pytest tests
reports/       figures and short report
```

## Reproduce
```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

## Deliverables
- [ ] Exploration notebook
- [ ] Reproducible pipeline (scripts + requirements)
- [ ] Short report with 3 findings
- [ ] Professional context paragraph
