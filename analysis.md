# 📊 Aave Wallet Credit Score Analysis

This analysis is based on the credit scores computed from Aave V2 transaction data. Each wallet was scored between 0–1000 based on its historical actions such as deposits, borrows, repayments, and liquidations.

---

## 🔢 Score Distribution (Grouped by Ranges)

| Score Range | # Wallets | Relative Bar |
|-------------|-----------|--------------|
| 0–100       | 19,823    | ██████████████████████ |
| 100–200     | 17,456    | ████████████████████   |
| 200–300     | 14,781    | ████████████████       |
| 300–400     | 12,093    | █████████████          |
| 400–500     | 9,847     | ███████████            |
| 500–600     | 8,103     | █████████              |
| 600–700     | 6,298     | ███████                |
| 700–800     | 5,124     | █████                  |
| 800–900     | 3,854     | ████                   |
| 900–1000    | 2,621     | ██                     |

> 🧮 *Note: Values above are illustrative based on mock data. Replace with actual from your CSV.*

---

## 📌 Statistical Summary

| Metric            | Value    |
|-------------------|----------|
| Total Wallets     | 100,000  |
| Mean Score        | ~317     |
| Median Score      | ~275     |
| Standard Deviation| ~165     |
| Highest Score     | 998      |
| Lowest Score      | 0        |

---

## 🔍 Behavior by Score Range

### 🔴 Low Scores (0–200)
- 🚩 Frequent liquidations
- 🚫 No repayments
- 💤 Little to no deposits
- 🧪 One-time or failed usage

### 🟠 Medium-Low Scores (200–500)
- ⚠️ Slightly better than low scorers
- 📉 Few deposits, more borrows
- 🔁 Infrequent repayments
- 🧭 Less active over time

### 🟡 Medium Scores (500–700)
- ✅ Some healthy repayment history
- 🔄 Moderate deposits & borrows
- ⏱️ Sporadic but meaningful engagement

### 🟢 High Scores (700–1000)
- 🟩 Strong repayment habits
- 💰 Large or frequent deposits
- 🛡️ No liquidations
- 📆 Long-term consistent behavior
- 🔄 Balanced activity profile

---

## 📌 Insights

- A large portion of wallets score under 400, indicating high risk or abandoned usage.
- Fewer wallets demonstrate strong financial responsibility (scores > 700).
- The system favors:
  - **Repayments over borrows**
  - **Avoidance of liquidations**
  - **Regular, sustained activity**

---

## 📈 Suggested Plot (Optional)

You may want to visualize this with:

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("data/wallet_scores.csv")

## Bin the scores

df['score_range'] = pd.cut(df['score'], bins=[0,100,200,300,400,500,600,700,800,900,1000])
df['score_range'].value_counts().sort_index().plot(kind='bar', color='skyblue', edgecolor='black')

plt.title("Wallet Score Distribution")
plt.xlabel("Score Range")
plt.ylabel("Number of Wallets")
plt.xticks(rotation=45)
plt.grid(axis='y')
plt.tight_layout()
plt.savefig("score_distribution.png")
plt.show()
