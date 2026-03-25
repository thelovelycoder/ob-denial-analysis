import pandas as pd
import matplotlib.pyplot as plt

# File path
file_path = "/Users/lovelycauthen/Documents/claims_audit_engine/OB Denial Tool.xlsx"

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
