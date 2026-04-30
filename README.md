# Chat Analytics Platform with Behavioral Signal Extraction

A modular Python system for analyzing communication patterns and extracting behavioral signals from chat data. The platform is designed for research, productivity insights, and assistive (non-diagnostic) mental health exploration.

## Overview

This project processes conversational data to generate structured analytics, behavioral metrics, and linguistic insights. It combines traditional data analysis with natural language processing and machine learning techniques to provide interpretable outputs.

The system is intentionally designed as a pipeline, making it extensible for new data sources, models, and reporting layers.

## Features

### Communication Analytics

- Daily and hourly message distribution
- Per-user activity metrics
- URL and media-sharing frequency
- Conversation density and temporal trends

### Interaction Dynamics

- Response latency analysis
- Conversation initiation vs reply ratios
- Turn-taking behavior
- Participation inequality (Gini coefficient)

### Visualization

- Time-based heatmaps (hour × weekday)
- Message-type distribution charts
- Emoji usage frequency plots
- Engagement timelines

## Machine Learning Layer

- User clustering using behavioral features (K-Means, DBSCAN)
- Anomaly detection for bursts and inactivity (Isolation Forest)
- Activity peak prediction using time-series models
- Communication style classification based on engineered features

## NLP and Linguistic Analysis

### Sentiment Analysis

- Polarity scoring using rule-based or transformer models
- Temporal sentiment tracking
- Sentiment volatility and drift detection

### Linguistic Features

- Pronoun usage (self vs group focus)
- Lexical diversity (Type-Token Ratio)
- Keyword extraction (TF-IDF, KeyBERT)
- Emotion categorization using standard emotion models

## Behavioral Signal Indicators

These indicators are heuristic and intended for exploratory analysis only. They are not clinical or diagnostic tools.

- Persistent negative sentiment
- Reduced interaction frequency (withdrawal proxy)
- Late-night activity spikes (circadian disruption proxy)
- Sudden communication drop-offs
- Repetitive high-intensity language patterns

## Reporting

- Automated user-level summaries
- Time-window comparison reports
- Exportable outputs (HTML, PDF)
- Structured JSON for downstream systems

## Project Structure

```text
chatalytics/
├── ingestion/        # Chat parsing (WhatsApp, Slack, etc.)
├── preprocessing/    # Cleaning and normalization
├── analytics/        # Core metrics
├── ml/               # Clustering and anomaly detection
├── nlp/              # Sentiment and linguistic features
├── signals/          # Behavioral indicators
├── visualization/    # Charts and dashboards
├── reports/          # Output generation
└── api/              # Optional FastAPI interface
```

## Installation

```bash
git clone https://github.com/Lkag04/chatalytics.ai
cd chatalytics.ai
pip install -r requirements.txt
```

## Usage

```python
from chatalytics import ChatAnalyzer

analyzer = ChatAnalyzer("chat.txt")
report = analyzer.run_pipeline()

print(report.summary())
```

## Data Compatibility

The system can be extended to support multiple chat formats:

- WhatsApp exports
- Slack logs
- Discord message dumps
- Custom text-based chat datasets

## Limitations

- Behavioral indicators are heuristic and not clinically validated
- Model performance depends on data quality and preprocessing
- Language-specific nuances may affect NLP accuracy
- Time-series predictions require sufficient historical data

## Future Work

- Real-time analytics pipeline
- Interactive dashboard (FastAPI + frontend)
- Semantic embeddings for conversation clustering
- Privacy-preserving processing (PII masking, anonymization)
- Benchmarking and evaluation datasets

## Contributing

Contributions are welcome. Please open an issue to discuss proposed changes before submitting a pull request.

## License

This project is licensed under the MIT License.
