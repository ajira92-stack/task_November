import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

def load_data():
    # Load built-in restaurant tips dataset
    df = sns.load_dataset("tips")
    return df

def basic_summary(df):
    print("Dataset Shape:", df.shape)
    print("\nMissing Values:\n", df.isnull().sum())
    print("\nSummary Statistics:\n", df.describe())

def analyze_tipping(df):
    # Calculate tip percentage
    df["tip_pct"] = (df["tip"] / df["total_bill"]) * 100
    avg_tip_by_day = df.groupby("day", observed=False)["tip_pct"].mean()
    print("\nAverage Tip % by Day:\n", avg_tip_by_day)

def plot_distributions(df):
    plt.figure(figsize=(8, 5))
    sns.scatterplot(data=df, x="total_bill", y="tip", hue="time")
    plt.title("Total Bill vs Tip by Meal Time")
    plt.savefig("bill_vs_tip.png")
    plt.close()

if __name__ == "__main__":
    data = load_data()
    basic_summary(data)
    analyze_tipping(data)
    plot_distributions(data)
