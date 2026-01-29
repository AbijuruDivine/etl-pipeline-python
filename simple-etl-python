import pandas as pd
import sqlite3

# Extract
data = pd.read_csv("transactions.csv")

# Transform
data["amount"] = data["amount"].astype(float)
data = data[data["amount"] > 0]

# Load
conn = sqlite3.connect("transactions.db")
data.to_sql("transactions", conn, if_exists="replace", index=False)

conn.close()
print("ETL process completed.")
