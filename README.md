# Sentiment Analysis on Social Media Data

This project implements a data engineering pipeline for performing sentiment analysis on social media data at scale.

## Overview

This system ingests social media posts from various platforms, processes them through a sentiment analysis model, and stores the results for further analysis and visualization.

## Architecture

1. Data Ingestion: Apache Kafka
2. Data Processing: Apache Spark
3. Sentiment Analysis: NLTK / TextBlob
4. Data Storage: Apache Cassandra
5. Visualization: Tableau

## Setup

### Prerequisites

- Docker
- Docker Compose
- Python 3.8+

### Installation

1. Clone this repository: https://github.com/princemsd007/Sentiment-Analysis-on-Social-Media-Data.git
  cd sentiment-analysis-social-media

2. Build and start the Docker containers: docker-compose up -d

## Usage

1. Configure social media API credentials in `config.yml`.
2. Start the data ingestion process: python src/ingest_data.py

3. Run the Spark job for sentiment analysis: spark-submit src/analyze_sentiment.py


4. Query results from Cassandra using `src/query_results.py`.

## Data Model

The processed data is stored in Cassandra with the following schema:

```sql
CREATE TABLE sentiment_results (
 post_id UUID PRIMARY KEY,
 platform TEXT,
 user_id TEXT,
 post_text TEXT,
 sentiment_score FLOAT,
 sentiment_label TEXT,
 timestamp TIMESTAMP
);
```
Contributing
Please read CONTRIBUTING.md for details on our code of conduct and the process for submitting pull requests.

License
This project is licensed under the MIT License - see the LICENSE.md file for details.


Would you like me to explain or elaborate on any part of this README?
