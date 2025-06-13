# Heavy Drinking Detection Using Smartphone Accelerometer Data

## Overview

**Word** is developing a mobile application that leverages smartphone accelerometer data to detect instances of heavy drinking. The core objective is to create a user-friendly and reliable tool capable of accurately identifying movement patterns associated with heavy alcohol consumption. By analyzing motion data using advanced machine learning techniques, the app aims to provide meaningful feedback to users about their drinking behavior, promote responsible alcohol consumption, and enable early intervention for alcohol-related risks. Privacy and data security are foundational principles in the application’s development.

---

## Project Objectives

1. **Accurate Detection of Heavy Drinking:**  
   Build models that analyze accelerometer readings to identify anomalies and motion patterns indicative of excessive drinking.

2. **Data-Driven Insights:**  
   Use advanced algorithms—including permutation entropy and complexity metrics—to reliably distinguish between heavy drinking and sober cases.

3. **User Privacy:**  
   Ensure all processing of sensitive motion and behavioral data is handled securely and confidentially.

4. **Awareness and Intervention:**  
   Equip users with insights into their drinking habits and provide tools for early intervention if risky patterns are detected.

---

## Data Source

- **Dataset:** [Bar Crawl: Detecting Heavy Drinking](https://archive.ics.uci.edu/dataset/515/bar+crawl+detecting+heavy+drinking)
- **Description:**  
  The dataset includes:
  - **Accelerometer Data:** Acceleration in x, y, z directions with timestamps.
  - **TAC Data:** Transdermal Alcohol Concentration (TAC) readings with timestamps.
  - **Multiple Participants:** Each participant (PID) has unique data streams.

---

## Data Processing & Analysis

### 1. Data Exploration

- **Accelerometer Dataset:**  
  - 4 features: x, y, z acceleration, and timestamp.
- **TAC Dataset:**  
  - 2 features: TAC value and timestamp.
- **Preprocessing:**  
  - Timestamps converted from milliseconds to seconds.
  - Accelerometer data scaled to correct sampling mismatches.
  - All TAC files concatenated, with a `pid` column added for participant identification.
  - Merged accelerometer and TAC data on timestamp and PID.

### 2. Visualization

- **Time Series Plots:**  
  Show acceleration (x, y, z) and corresponding TAC levels for each participant.
- **Entropy & Complexity Analysis:**  
  - Entropy and complexity metrics computed for different TAC levels.
  - Box plots reveal that sober cases generally have higher entropy and lower complexity, while drunk cases show the opposite.
- **Trend, Seasonality, Residual Decomposition:**  
  - Seasonal components often fluctuate more in drunk states, suggesting increased instability or movement changes due to intoxication.

### 3. Key Findings

- **Permutation Entropy & Complexity:**  
  - Lower TAC (sober) readings tend to have higher entropy, lower complexity.
  - Higher TAC (drunk) readings see reduced entropy and increased complexity.
  - Clear statistical differences between sober and drunk cases, supporting the use of these metrics for differentiation.
- **Behavioral Insights:**  
  - Motion patterns change noticeably with higher TAC values.
  - Individuals exhibit different responses, but significant deviations from baseline patterns are potential indicators of intoxication.

---

## Getting Started

### Prerequisites

- Python 3.x
- Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`

### Quick Start

1. Clone the repository and open `Bar_Crawl_Project.ipynb`.
2. Follow the notebook to:
   - Load and preprocess the data.
   - Visualize and analyze patterns.
   - Compute entropy and complexity.
3. Review the results and charts for insights into heavy drinking detection.

---

## Methodology

- **Machine Learning Approach:**  
  - Focus on feature engineering from time-series accelerometer data.
  - Use permutation entropy and complexity to quantify behavioral regularity and unpredictability.
- **Evaluation:**  
  - Statistical testing and visual inspection to differentiate between sober and intoxicated states.

---

## Privacy and Ethics

- All personal and sensor data are handled according to strict privacy and security protocols.
- The goal is to empower users with their own behavioral data, not to penalize or surveil.

---

## Future Work

- Integrate real-time detection into a mobile app.
- Expand to different sensor types for improved accuracy.
- Collaborate with health professionals for intervention features.

---

## References

- [Bar Crawl Dataset - UCI ML Repository](https://archive.ics.uci.edu/dataset/515/bar+crawl+detecting+heavy+drinking)
- [Permutation Entropy and Complexity - Literature](https://en.wikipedia.org/wiki/Permutation_entropy)

