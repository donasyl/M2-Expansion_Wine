🍷 Wine Similarity and Clustering Analysis

Author: Donasyl M. Aho, Casey Majewski, Noor Qureshi, Madison Troutman, Nathan Temesgen
Project Type: Network Analysis, Similarity Modeling, Unsupervised Learning
Methods: Cosine Similarity, KMeans, Hierarchical Clustering, PCA

📌 Project Overview

This project applies similarity analysis and unsupervised clustering to a large wine review dataset to understand how wines relate based on category, region, rating, alcohol content, and price. Using cosine similarity and clustering algorithms, I identify influential wine types, discover natural market segments, and visualize structural patterns within the wine space.

The expansion builds on prior exploratory analysis by introducing network-style similarity modeling, market driven clustering, and dimensionality reduction to produce interpretable consumer segments and practical insights for recommendation systems, inventory planning, and pricing strategy.

🎯 Objectives

Measure similarity between wines using mixed categorical and numeric features

Identify wines and varietals that act as strong reference points

Segment wines into meaningful consumer clusters

Compare clustering approaches and validate structure

Visualize wine relationships in reduced dimensional space

📂 Dataset

Source: Wine review dataset (CSV format)

File used: wine 2.csv

Size after cleaning: Approximately 3,600 wines

Key Variables

wine

winery

category

varietal

appellation

alcohol

price

rating

🧹 Data Cleaning and Feature Engineering

Removed rows missing varietal, category, or rating

Parsed alcohol percentage from string to numeric

Cleaned price values and converted to floats

Dropped records with missing rating, alcohol, or price for clustering

One hot encoded wine category

Expanded appellation into multi label dummy variables

Scaled numeric features for similarity and clustering

🧠 Similarity Analysis
Feature Construction

The similarity feature matrix combines:

One hot encoded wine category

Appellation indicators

Scaled numeric features including rating, alcohol percentage, and price

Similarity Metric

Cosine similarity applied to the full feature matrix

Generated a pairwise similarity matrix across all wines

Visual Diagnostics

Histogram showing the distribution of cosine similarity scores

Heatmap style visualization of the similarity matrix

These visuals confirm meaningful variation in similarity rather than random noise.

🔍 Similar Wine Retrieval

For selected varietals, the model retrieves the top 10 most similar wines based on cosine similarity.
Each result reports:

Wine name

Varietal

Similarity score

This component demonstrates practical use for recommendation systems and comparative tasting analysis.

🔗 Clustering Analysis
Numeric Feature Set

Clustering is based on:

Rating

Alcohol percentage

Price

All features are standardized prior to modeling.

KMeans Clustering

Used the elbow method to evaluate cluster counts

Selected k = 4 for interpretability and market relevance

Assigned cluster labels to each wine

Computed cluster centroids and transformed them back to original units

Hierarchical Clustering

Applied Agglomerative Clustering with cosine affinity

Used average linkage

Compared cluster distributions with KMeans output

This step provides structural validation and an alternative segmentation view.

🏷️ Cluster Interpretation

Clusters were labeled based on centroid characteristics and wine composition:

Dessert and Whites
Lower alcohol, high ratings, higher prices in select cases

Ultra Premium Reds
Highest ratings, high alcohol, and very high prices

Value and Table Wines
Moderate ratings, accessible pricing, broad category mix

Boutique Reds
Smaller cluster of mid to high priced reds with niche appeal

📉 Dimensionality Reduction and Visualization

Applied PCA with two components

Visualized wines in a two dimensional space

Colored points by cluster assignment

Used PCA to confirm separation and overlap between segments

📊 Cluster Centroids Visualization

Compared average rating, alcohol percentage, and price across clusters

Used a dual axis bar chart for interpretability

Highlighted clear tradeoffs between quality, strength, and cost

🛠️ Technologies Used

Python

Pandas and NumPy

Scikit learn

Matplotlib

PCA and clustering algorithms

⚠️ Limitations

Appellation parsing treats regions as flat labels

Similarity does not incorporate tasting notes text

Ratings may reflect reviewer bias

Clustering relies on numeric features only
