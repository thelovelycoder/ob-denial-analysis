## 📊 Executive Summary

This project analyzes OB denial patterns to identify risk trends, coding inconsistencies, and opportunities for revenue cycle improvement.

Using Python, I evaluated denial risk levels and created a visual breakdown to highlight where organizations may be losing revenue due to preventable issues.

**Focus Areas:**
- Denial risk distribution
- Data consistency issues
- Revenue cycle improvement opportunities

**Outcome:**
Actionable insights to reduce denials, improve coding accuracy, and support financial performance.
## 📊 Key Insight
## 📈 Denial Risk Distribution

![Denial Risk Chart](denial_risk_chart.png)
The majority of denials fall within specific risk categories, indicating patterns that may be driven by documentation gaps, coding inconsistencies, or payer-specific rules.

This visualization highlights where intervention efforts should be focused to reduce revenue leakage.
```python
import pandas as pd
import matplotlib.pyplot as plt

# File path
file_path = "OB Denial Tool.xlsx"

# Load data
df = pd.read_excel(file_path)

# Clean column (important to avoid duplicates like 'High ' vs 'High')
df["Denial_Risk_Level"] = df["Denial_Risk_Level"].astype(str).str.strip()

# Create chart
df["Denial_Risk_Level"].value_counts().plot(kind="bar")

plt.title("Denial Risk Level Distribution")
plt.xlabel("Risk Level")
plt.ylabel("Count")

plt.tight_layout()

# 🔥 SAVE IMAGE (this is the key part)
plt.savefig("denial_risk_chart.png")

# Show chart
plt.show()
```
