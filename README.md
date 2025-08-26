# course-NLP

## Overview
This project is part of a course on Natural Language Processing (NLP) with a focus on networks, graphs, and NLP techniques. The main goal is to analyze Reddit data related to Tesla, key influencers, and comparative companies, and to extract insights using NLP and graph analysis.

## What We Did
- **Data Collection**: Used the Reddit API (via `praw`) to scrape posts and comments from selected subreddits and for specific individuals (e.g., Elon Musk, Jeff Bezos, politicians, investors).
- **NLP Processing**: Applied sentiment analysis (VADER), text normalization, and topic modeling (LSA, LDA) to posts and comments.
- **Graph Construction**: Built graphs where nodes represent entities (Tesla, influencers, companies) and edges represent co-mentions, weighted by post/comment scores and colored by sentiment.
- **Analysis & Visualization**: Calculated graph metrics (centrality, communities, clustering, etc.), visualized networks, and generated word clouds colored by sentiment.
- **Outputs**: Saved processed data, analysis results, and visualizations to the `outputs/` and `graphs_analysis/` folders.

## Repository Structure
- `reddit_scrapper.py`: Main script for scraping Reddit and running analysis.
- `analysis.ipynb`: Jupyter notebook for interactive analysis and visualization.
- `requirements.txt`: Python dependencies.
- `posts_data/`: CSV files of raw Reddit posts/comments for each individual.
- `outputs/`: Processed results (word frequencies, sentiment stats, topic models, etc.).
- `graphs_analysis/`: Graph statistics and edge sentiment analysis per time period.

## How to Use
1. **Install Dependencies**:
	```powershell
	pip install -r requirements.txt
	```
2. **Configure Reddit API Credentials**:
	- Create a `secrets_config.py` file with your Reddit API keys (see `RedditSecretsConfig` usage in code).
3. **Run Analysis**:
	- Use `reddit_scrapper.py` to fetch data and process it (uncomment `client.fetch_all_posts()` to scrape new data).
	- Or, open `analysis.ipynb` for step-by-step exploration and visualization.
4. **Explore Outputs**:
	- Check `outputs/` for CSVs with word stats, sentiment, topics, and more.
	- Check `graphs_analysis/` for graph metrics and edge sentiment CSVs.

## Main Techniques
- Sentiment analysis (VADER)
- Topic modeling (LSA, LDA)
- Graph/network analysis (NetworkX)
- Word clouds and TF-IDF

## Research Questions Explored
- How did Elon Musk’s centrality and prominence evolve across different subreddits and time periods?
- How did relationships and sentiment trends between key figures (e.g., Musk, Trump, Biden, AOC, Cramer) and companies shift over time?
- What is the significance of bridging connections between opposing or unusual figures in the network?
- Can distinct communities be identified in the networks, and how do they compare across time periods?

## Main Results
- Elon Musk remained the most central figure in all periods, consistently ranking highest in network centrality measures (degree, betweenness, closeness).
- Before 2020: Networks were smaller, dominated by political figures with generally positive sentiment; Musk was important but less politically entangled.
- 2020–2021: Musk’s prominence rose, political figures became more central, and communities formed around politics and finance.
- 2022–2023: Networks grew larger and more polarized, with more negative sentiment; figures like AOC, Trump, and Cramer bridged polarized groups.
- 2024–2025: Musk stayed dominant, bridging technology and politics, but sentiment showed sharper polarization.
- Sentiment analysis revealed cycles of optimism (innovation/support) versus negativity (criticism/anger) depending on context (elections, economic shifts).
- Topic modeling showed a shift from technology/space themes (pre-2020) to politics/economy (2020–2021), and then to polarization/social debates (2022–2025).
- Clear clusters emerged (technology, political, financial), with Musk often acting as the connector between them.

## Visualization
The project includes visualizations of entity networks, word clouds colored by sentiment, and time-evolving sentiment statistics.

---
For more details, see the code in the notebook `analysis.ipynb`.