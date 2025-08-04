# Customer_personality_cleaning
import pandas as pd
import os
from datetime import datetime

file_path = r"C:\Users\Parid\Contacts\archive\marketing_campaign.csv"

if not os.path.exists(file_path):
    print(f"❌ File not found at: {file_path}")
    exit()

df = pd.read_csv(file_path, sep='\t')
print("✅ File loaded successfully!\n")
print(df.head())


df.columns = df.columns.str.strip().str.lower().str.replace(" ", "_")
print("\n📌 Renamed columns:")
print(df.columns)


print("\n📌 Missing values before cleaning:")
print(df.isnull().sum())

df = df.dropna()  


df = df.drop_duplicates()


df['dt_customer'] = pd.to_datetime(df['dt_customer'], format="%d-%m-%Y")


df['education'] = df['education'].str.lower().str.strip()
df['marital_status'] = df['marital_status'].str.lower().str.strip()


df['customer_since_years'] = datetime.now().year - df['dt_customer'].dt.year


df['income'] = df['income'].astype(float)
df['kidhome'] = df['kidhome'].astype(int)
df['teenhome'] = df['teenhome'].astype(int)


output_path = "cleaned_marketing_campaign.csv"
df.to_csv(output_path, index=False)
print(f"\n✅ Cleaned dataset saved as: {output_path}")
