# 🎧 Hustle & Heart  
### A Scalable, Heuristic-Based Spotify Playlist Recommendation System

🔗 **Live Project:**  
https://dhruvhw-10.github.io/STA9750-2025-SPRING/mp03.html  

---

## Executive Summary

This project builds a transparent, feature-driven playlist recommendation system using large-scale Spotify data.  

Rather than relying on black-box machine learning models, the system leverages interpretable heuristics across audio features, playlist co-occurrence patterns, and artist affinity to generate a cohesive 12-track playlist.

The result is a reproducible recommendation pipeline capable of scaling to tens of thousands of tracks and millions of playlist interactions.

---

## Problem Statement

Streaming platforms must balance:

- Popularity vs personalization  
- Algorithmic relevance vs editorial cohesion  
- Feature similarity vs user behavior patterns  

This project explores:

> Can we construct a production-style playlist recommendation framework using scalable data engineering + interpretable heuristics?

---

## Dataset & Scale

**Primary Sources**
- Spotify Song Feature Dataset (GitHub)
- Spotify Million Playlist Dataset (MPD)

**Data Volume**
- 50,684 unique tracks
- 9,609 unique artists
- 1M+ playlist entries
- Multi-decade temporal span (1920s–2020s)

**Audio Features Used**
- Danceability
- Energy
- Valence
- Tempo
- Loudness
- Acousticness
- Key
- Duration
- Popularity

---

## System Architecture

### 1️⃣ Data Ingestion
- Automated download of JSON playlist slices
- CSV ingestion for track-level audio features
- Defensive file handling & corruption skipping

### 2️⃣ Data Normalization
- Flattened nested playlist JSON structures
- Standardized Spotify URIs
- Rectangular track-level schema

### 3️⃣ Feature Join Strategy
- Inner joins on track_id
- Null filtering for integrity
- De-duplication across artist-song pairs

---

## Exploratory Signal Discovery

### Popularity vs Playlist Appearances
- Positive relationship with diminishing returns
- Saturation beyond high exposure thresholds
- Suggests exposure alone does not maximize popularity

### Recency Bias
- Post-2015 tracks dominate playlist ecosystems
- Platform growth strongly influences discovery trends

### Tempo vs Danceability
- Slight negative correlation (r ≈ -0.15)
- Optimal danceability cluster: 90–120 BPM
- Groove > Speed

### Structural Music Trends
- Post-1970 steady increase in danceability
- Track durations tightly cluster at 2.5–4.5 minutes
- 2010s show exponential production growth

---

## Heuristic Recommendation Engine

Instead of collaborative filtering or deep learning, this system uses a hybrid scoring framework:

### Heuristic 1 — Playlist Co-Occurrence
Identifies tracks appearing alongside anchor songs in real user playlists.

Signal type: Behavioral

---

### Heuristic 2 — Tempo & Key Matching
Filters tracks within harmonic and BPM proximity to anchor tracks.

Signal type: Musical Compatibility

---

### Heuristic 3 — Artist Affinity Expansion
Extends candidate pool within anchor artist ecosystems.

Signal type: Artist Network

---

### Heuristic 4 — Acoustic Feature Similarity
Minimizes deviation across:
- Danceability
- Energy
- Acousticness

Signal type: Feature Distance Scoring

---

### Heuristic 5 — Emotional Continuity
Filters tracks by:
- Valence proximity
- Loudness proximity

Signal type: Mood Stability

---

## Candidate Reduction

Initial heuristic candidate pool: 5,157 tracks  
Popularity threshold applied: ≥ 70  

Final curated selection: 12 tracks

Two anchor tracks manually retained to preserve thematic integrity.

---

## Final Output: Hustle & Heart

A curated playlist engineered for:

- Energy progression
- Emotional continuity
- Feature stability
- Genre cohesion
- Smooth transitions

Includes:
- Audio feature evolution visualization
- Track-order feature continuity analysis
- Embedded Spotify playback

---

## Why This Matters

This framework demonstrates:

- Scalable playlist modeling
- Interpretable recommendation logic
- Feature-based similarity scoring
- Behavioral + content hybrid filtering
- Data-to-product pipeline thinking

---

## Tradeoffs & Limitations

- No user-level personalization
- No real-time ranking optimization
- No learned similarity embeddings
- Heuristics may overweight anchor bias

Future enhancements could include:
- Cosine similarity matrices
- KNN-based feature clustering
- Matrix factorization
- Embedding generation
- Real-time scoring API

---

## Tech Stack

- R
- dplyr / tidyr
- ggplot2
- jsonlite
- DT
- GitHub Pages
- Custom Spotify CSS Theme

---

## Project Structure

├── mp03.html
├── mp03.qmd
├── styles/
│ └── spotify-style.css
├── images
│ └── Heuristic
└── README.md


---

## Author

Dhruv Sharma  
Data Analytics | Feature Engineering | Systems Thinking  

---

## Key Takeaway

This project demonstrates the ability to:

- Work with large-scale semi-structured data  
- Engineer interpretable recommendation logic  
- Extract platform-level behavioral insights  
- Convert analysis into a consumer-facing product
