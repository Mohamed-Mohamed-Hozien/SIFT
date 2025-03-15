Introduction

This report analyzes how different parameters affect image retrieval performance using the Bag of Visual Words (BoVW) model. The experiments evaluate:

The impact of varying the number of images used for clustering.

The effect of different numbers of centroids.

A comparison between TF-IDF and Bag of Words (BoW) for feature representation.

Methodology

We used a dataset of grayscale images and extracted SIFT features. The features were clustered using K-Means to form a visual vocabulary. Image retrieval was conducted using cosine similarity between feature representations.

Experiments & Results

1. Varying the Number of Images Used for Clustering

We tested three different sample sizes (500, 1000, and 1500 images) while keeping the number of centroids fixed at 250. The retrieval performance was evaluated using cosine similarity.

Results:

Smaller sample sizes resulted in lower retrieval accuracy due to insufficient cluster representations.

Increasing the sample size improved feature differentiation, leading to better retrieval results.

2. Varying the Number of Centroids

We tested different numbers of centroids (100, 250, and 500) using a fixed sample size of 1000 images.

Results:

With fewer centroids (k=100), retrieval accuracy was lower due to less discriminative clustering.

Increasing centroids to 250 improved results significantly.

At k=500, retrieval performance plateaued, indicating diminishing returns.

3. Comparison of TF-IDF vs. BoW

We compared BoW (basic frequency vectors) against TF-IDF, which normalizes frequency based on inverse document frequency.

Results:

TF-IDF provided more accurate retrieval as it downweighted frequently occurring features, emphasizing discriminative keypoints.

BoW performed worse, retrieving less relevant images due to overemphasis on common features.

Final Selection of Best Parameters

Based on the experiments, the optimal parameters for retrieval accuracy were:

Number of images for clustering: 1500

Number of centroids: 250

Feature representation: TF-IDF

Conclusion

This analysis highlights the importance of selecting appropriate parameters for image retrieval. Increasing sample size and centroids improves performance up to a limit, while TF-IDF significantly enhances retrieval accuracy over BoW.

The final Jupyter Notebook includes the best-selected parameters for optimal image retrieval.

