# 💳 Aave Credit Scoring

A machine learning-based credit scoring system for wallets interacting with the Aave V2 protocol. This tool analyzes 100K+ DeFi transaction records and generates credit scores (0–1000) that reflect responsible vs. risky on-chain user behavior.

## 📌 Problem Statement

Given raw transaction logs from Aave V2 (e.g., deposit, borrow, repay, redeem, liquidation), build a one-step ML pipeline to assign a credit score (0–1000) to each wallet.

## 📂 Project Structure
aave-credit-scoring/
│
├── data/ # Input & output data files
│ └── user_transactions.json
│
├── src/ # Source code for feature extraction & scoring
│ ├── score_wallets.py # Entry script for scoring
│ ├── feature_engineering.py
│ └── scoring_model.py # Scoring logic (basic rule-based or ML)
│
├── analysis.md # Score distribution + insights
├── README.md # Project overview
└── requirements.txt # Python dependencies

---

## ⚙️ How to Run This Project

### 🔧 Prerequisites

- Python 3.8+
- `pip` installed
- Recommended: Create a virtual environment

### 🧪 Step-by-step Instructions

1. **Clone the repo**
   ```bash
   git clone https://github.com/your-username/aave-credit-scoring.git
   cd aave-credit-scoring

### install dependencies
pip install -r requirements.txt 

###  run using this script:
python src/score_wallets.py --input data/user_transactions.json --output data/scored_wallets.csv
