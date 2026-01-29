# 🎵 Unsupervised ML – Music Clustering with K-Means

## Data Detectives: Cracking the Playlist Case with Audio Clues

This project explores how unsupervised machine learning can uncover hidden patterns in music. By analyzing Spotify audio features and applying K-Means clustering, we group songs with similar sound profiles and generate cohesive, human-intuitive playlists all without using genre labels.

# 📌 Project Overview
Modern music libraries contain millions of tracks. Manually curating playlists based on mood or sound is time-consuming and subjective. This project demonstrates how Spotify audio features combined with unsupervised ML can:
- Detect musical similarity
- Cluster songs by shared audio characteristics
- Generate thematic playlists
- Align algorithmic results with human perception

Project Title: Unsupervised ML

Dataset Size: ~5,000 songs

Core Technique: K-Means Clustering


# 🎯 Key Question

Can algorithms match human intuition when grouping music by similarity?

Answer: Yes. Human review confirmed a very high degree of perceptual similarity within clusters produced by K-Means.


# 🧠 Methodology

# 1️⃣ Load the Evidence
	•	Songs were loaded from a CSV file containing Spotify audio features.

# 2️⃣ Feature Selection

Kept Features (Numeric Only):
- Danceability
- Energy
- Valence
- Loudness
- Acousticness
- Instrumentalness
- Speechiness

Dropped Features:
- Non-numeric metadata (e.g., song titles, artist names)

Only numerical features were used to ensure unbiased, sound-based clustering.

# 3️⃣ Feature Scaling

To ensure no single feature dominated the analysis:
- Min-Max Scaling was applied
- All features were normalized to the range [0, 1]

# 4️⃣ Clustering
- Algorithm: K-Means
- Number of Clusters: k = 25
- Random State: 42 (ensures reproducibility)

This approach aligns perfectly with Unsupervised ML principles:
- No labeled data required
- Fast and scalable
- Easy to interpret
- Effective for large datasets

# 5️⃣ Choosing the Optimal k

The number of clusters was determined using:
- Silhouette Score
- Elbow Method

Both methods supported k = 25 as a strong balance between cohesion and separation.

# 📊 Exploratory Data Insights

Correlation Highlights

Positive Correlations:
- Loudness ↔ Energy
- Danceability ↔ Valence

Negative Correlations:
- Acousticness ↔ Energy
- Acousticness ↔ Loudness
- Instrumentalness ↔ Danceability

Key Observations
- Energetic tracks tend to be louder
- Acoustic and instrumental tracks are generally quieter and less energetic

# 🧭 Visualization
- PCA (Principal Component Analysis) reduced feature space to 2D
- Each point represents a song
- Colors indicate cluster membership
- Large “X” markers represent centroids

### Result:
- Clearly separated clusters
- Distant clusters represent distinct musical styles (e.g., Metal vs. Classic Pop & Rock)

# 🎼 Thematic Playlist Creation

Clusters were transformed into playlists using a two-step approach:

1) Artist Profiling with ChatGPT to infer cluster themes
2) Manual Genre Validation to ensure accuracy

## Sample Playlists
- Classic Pop & Rock
- Hip-Hop & Pop-Rock Fusion
- Urban Pop & Soft Rock
- Latin Pop & Reggaeton

Each playlist reflects its cluster centroid’s dominant audio characteristics.

# ✅ Prototype Effectiveness
- Two songs sampled per playlist
- Strong cohesion observed within each cluster
- Songs shared consistent mood, energy, and sound texture
	
 This validated the clustering quality and playlist logic.

# 🚀 Spotify Integration
- Generated playlists were uploaded directly to Spotify using the Spotify API
- Demonstrates real-world applicability of the model

# 🔮 Conclusion & Next Steps

## What We Learned
- Spotify audio features reliably capture musical similarity
- K-Means is a strong baseline for playlist generation
- Unsupervised ML can align closely with human musical perception

### Future Improvements
- Incorporate real-time user feedback:
- Skip rate
- Listening duration
- Time of day
- Geolocation
- Build personalized playlists per user profile
- Explore advanced models for smoother musical transitions

# 🛠 Tech Stack
	•	Programming Language: Python
	•	Data Processing: pandas, NumPy
	•	Machine Learning: scikit-learn
	•	Dimensionality Reduction: PCA (scikit-learn)
	•	Visualization: matplotlib, seaborn
	•	API Integration: Spotify Web API
	•	Environment: Jupyter Notebooks

# ⚙️ Installation & Usage

## 1. Clone the Repository
```
git clone https://github.com/your-username/unsupervised-ml-music-clustering.git
cd unsupervised-ml-music-clustering 
```
## 2. Install Dependencies
```
pip install -r requirements.txt
```
## 3. Run the Analysis
	•	Explore data preprocessing and clustering in /notebooks
	•	Core logic lives in /src
	•	Results and visualizations are generated within notebooks


# 📂 Repository Structure & Module READMEs

```
Moosic_UnsupervisedML/
├── data/
│   ├── raw/
│   │   └── spotify_tracks_raw.csv        # Original dataset
│   ├── processed/
│   │   └── spotify_tracks_scaled.csv     # Cleaned & scaled data
│   └── README.md                         # Data documentation
│
├── notebooks/
│   ├── Moosic_Clustering_Full_Analysis.ipynb
│   └── README.md                         # Analysis & experiments
│
├── src/
│   ├── preprocessing.py                 # Feature selection & scaling
│   ├── clustering.py                    # K-Means logic
│   ├── visualization.py                 # PCA & plotting
│   ├── spotify_upload.py                # Spotify API integration
│   └── README.md                        # Source code overview
│
├── assets/
│   └── figures/
│       ├── elbow_method.png
│       ├── silhouette_score.png
│       └── pca_clusters.png
│
├── Moosic.pdf                            # Presentation slides
├── requirements.txt                     # Python dependencies
└── README.md                             # Project overview
```
# 🎓 Academic Framing

This project investigates the effectiveness of unsupervised learning techniques for identifying latent musical structures. By leveraging Spotify audio features and K-Means clustering, the study demonstrates that sound-based numerical representations can produce perceptually meaningful groupings without reliance on genre labels.


# 🚀 Startup / Product Framing

Moosic is a prototype playlist-generation engine that transforms raw audio features into mood-consistent, human-aligned playlists. The system scales efficiently, integrates directly with Spotify, and provides a foundation for personalized, feedback-driven music discovery.


# 💼 Portfolio Framing

This project showcases practical experience in unsupervised machine learning, clustering evaluation, feature engineering, and real-world API integration. It highlights the ability to translate ML outputs into user-facing products.


🙌 Acknowledgments

Thanks for listening and happy clustering 🎧
