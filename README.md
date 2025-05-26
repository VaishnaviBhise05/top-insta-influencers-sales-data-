# top-insta-influencers-sales-data-
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv('top_insta_influencers_data.csv')
df

print(df.head())
print("Dataset Shape:", df.shape) 
print("\nColumn Info:\n", df.info()) 
print("\nMissing Values:\n", df.isnull().sum()) 
print("\nSample Data:\n", df.head())
print("\nStatistical Summary:\n", df.describe(include='all')) 


import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(8, 5))
sns.histplot(df['followers'], bins=50, kde=True)
plt.title("Distribution of Followers")
plt.xscale('log')  # Followers often follow a power law
plt.show()

top_countries = df['country'].value_counts().head(10)
print("Top 10 countries by influencer count:\n", top_countries)

top_countries.plot(kind='bar', title='Top 10 Countries by Influencer Count', figsize=(10, 5))
plt.ylabel("Number of Influencers")
plt.xlabel("Country")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

df.to_csv('cleaned_instagram_influencers.csv', index=False)
print("Exported cleaned dataset to CSV.")

df.to_csv('clean_influencers.csv', index=False)
print("Cleaned data saved to 'clean_influencers.csv'")


