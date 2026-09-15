# Solution Overview

## What We Built

We built an AI-powered pharmacovigilance and regulatory support platform with two main modes:

1. *Signal Detection* – analyzes adverse event reports to identify potential emerging drug safety signals.
   The solution helps pharmacovigilance and regulatory teams analyze safety data faster, prioritize important signals, and identify submission gaps.

## How It Works

 Signal Detection

1. The user uploads adverse event report data.
2. The system reads and organizes the reports using drug, adverse event, SOC/PT, and demographic information.
3. Similar adverse events are clustered together.
4. The system calculates Proportional Reporting Ratio (PRR), chi-squared values, and case counts.
5. The signals are evaluated using predefined criteria to identify weak, moderate, or strong safety signals.
6. The dashboard displays ranked safety signals with supporting statistics and a plain-language explanation.

## Architecture Diagram

> See [`architecture.md`](architecture.md) for the detailed diagram.

User
  ↓
Frontend / Dashboard
  ↓
Data Upload & Preprocessing
  ↓
Adverse Event Reports
  ↓
AE Clustering (SOC/PT)
  ↓
PRR + Chi-square + Case Counts
  ↓
Signal Evaluation
  ↓
Ranked Safety Signals
  ↓
Dashboard + AI Explanation
## Key Design Decisions

| Decision | Rationale |
|---|---|
| Use IBM watsonx.ai for AI-based anomaly detection | Pre-trained AI models reduce development time and help classify potential safety signals efficiently. |
| Combine AI with PRR and Chi-square analysis | Statistical methods provide transparent evidence, while AI helps interpret and explain the results. |
| Rank and explain detected signals | Helps analysts quickly focus on important signals and understand why they were flagged. |

## IBM Technologies Used

- *IBM watsonx.ai:* Used as the AI layer for analyzing adverse-event data and identifying potential anomaly/safety-signal types.
- *IBM Granite Model:* Used to classify and interpret adverse-event text and support safety-signal analysis.
- *Python SDK:* Used to connect the application with watsonx.ai and send adverse-event data for AI processing.
