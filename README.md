# Human Activity Recognition with Hidden Markov Models

Formative 2 — Machine Learning Techniques II
Individual submission — Henriette Utatsineza

## Overview

This project builds a Hidden Markov Model (HMM) to recognize four human activities
(standing, walking, jumping, still) from smartphone accelerometer and gyroscope data,
collected using the Sensor Logger app at 50 Hz.

The pipeline covers: data loading and preprocessing, windowing, time/frequency-domain
feature extraction, HMM training (Baum-Welch with supervised initialization), a
from-scratch Viterbi implementation (cross-checked against `hmmlearn`), and evaluation
on unseen data.

## Repository Structure

```
.
├── README.md                          # This file
├── HMM_Report.pdf                     # Full written report (5 pages)
├── HMM_Activity_Recognition.ipynb     # Main notebook (run this)
└── data/
    ├── standing/
    │   ├── standing_1/
    │   │   ├── Accelerometer.csv
    │   │   ├── Gyroscope.csv
    │   │   └── Metadata.csv
    │   ├── standing_2/
    │   └── ...
    ├── walking/
    ├── jumping/
    └── still/
```

## Data Collection Summary

- 40 recording sessions total: 10 per activity (standing, walking, jumping, still)
- Collected across 3 sessions spanning 2 days (see report Section 2.1 for details)
- Sensor Logger app (Android), Accelerometer + Gyroscope only, 50 Hz sampling rate
- ~10 seconds per recording session

## How to Run

1. Open `HMM_Activity_Recognition.ipynb` in Google Colab or Jupyter
2. If using Colab, mount Google Drive and point `DATA_DIR` at wherever you've placed
   the `data/` folder (see first code cells in the notebook)
3. Install dependencies if needed: `!pip install hmmlearn`
4. Run all cells top to bottom

## Key Results

- Overall accuracy on unseen test data: **90.5%**
- Custom Viterbi implementation verified identical to `hmmlearn`'s built-in decoder
- Full HMM trained via Baum-Welch with supervised initialization (see report Section 3.3
  for why this was necessary — unsupervised initialization caused state collapse)

See `HMM_Report.pdf` for full methodology, results, and discussion.

## Note on Group Structure

This project was originally assigned as group work. Following a change in group
composition, this submission was completed individually, with confirmation from
course staff.