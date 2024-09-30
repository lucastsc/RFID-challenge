# RFID Tag Identification Challenge

## Problem Summary
In this challenge, the goal is to accurately identify RFID tags passing through a corridor equipped with four antennas. The data is segmented into three phases: **before** entering the corridor, **during** the passage, and **after** exiting. The dataset includes readings from stationary tags (background noise), tags in the user's possession, and other moving tags outside the corridor.

The objective is to classify tags as either **relevant** (passed through the corridor) or **irrelevant** (stationary or noise) using the provided data. The solution must achieve over **95% precision and recall** for both classes (valid and invalid tags).

## Dataset Structure
The dataset is divided into the following columns:

- **TIMESTAMP**: The date and time of each RFID reading.
- **TYPE**: Defines the phase of the reading:
  - `0`: Before entering the corridor
  - `1`: During passage through the corridor
  - `2`: After exiting the corridor
- **ANTENNA**: The antenna (1-4) that captured the reading.
- **RSSI**: The signal strength of the reading (higher values indicate stronger signals).
- **ID_AMOSTRA**: Identifies each passage through the corridor.
- **RESULT**: Whether the tag was held by the user (`1` for yes, `0` for no).

## Objective
Classify tags as **valid (1)** if they passed through the corridor or **invalid (0)** if they did not, with at least **95% precision and recall** for both classes.  
Present a confusion matrix to validate the final model's performance.

## Hypotheses to Consider
- **Stationary tags** will have fewer readings than moving tags.
- The **variance in RSSI** values for moving tags will be higher than for stationary tags.
- Tags seen across multiple **ID_AMOSTRA** values may indicate invalid tags (background noise).

## Requirements
- Use **Python** and any machine learning algorithm to solve the problem.
- Train the model using `amostra_02.csv` and test on `amostra_03.csv`, with the option for cross-validation.
- The final solution must include a confusion matrix for both classes.