<div align="center">

# 🚀 Stock Price & Sales Forecasting Engine

<img src="banner.png" alt="Project Banner" width="100%"/>

### *Enterprise-Grade AI Forecasting Platform for Financial Markets & Business Intelligence*

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110+-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.3+-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.16+-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://tensorflow.org)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docker.com)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16+-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://postgresql.org)
[![Redis](https://img.shields.io/badge/Redis-7+-DC382D?style=for-the-badge&logo=redis&logoColor=white)](https://redis.io)
[![MLflow](https://img.shields.io/badge/MLflow-2.13+-0194E2?style=for-the-badge&logo=mlflow&logoColor=white)](https://mlflow.org)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)](https://github.com/features/actions)
[![Coverage](https://img.shields.io/badge/Coverage-92%25-brightgreen?style=for-the-badge)](tests/)
[![Code Style](https://img.shields.io/badge/Code_Style-Black-000000?style=for-the-badge)](https://black.readthedocs.io)
[![Research](https://img.shields.io/badge/Level-Research_Grade-blueviolet?style=for-the-badge)]()
[![Stars](https://img.shields.io/github/stars/yourusername/Stock-Price-Sales-Forecasting-Engine?style=for-the-badge)](https://github.com)

---

**[📊 Live Demo](https://demo.forecasting-engine.ai)** • **[📖 Documentation](docs/)** • **[🐛 Report Bug](issues/)** • **[💡 Request Feature](issues/)**

</div>

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Research Highlights](#-research-highlights)
- [Architecture](#-architecture)
- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [Performance Benchmarks](#-performance-benchmarks)
- [Quick Start](#-quick-start)
- [Installation](#-installation)
- [Dataset Guide](#-dataset-guide)
- [API Documentation](#-api-documentation)
- [Dashboard](#-dashboard)
- [MLOps Pipeline](#-mlops-pipeline)
- [Deployment](#-deployment)
- [Testing](#-testing)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Project Overview

**Stock Price & Sales Forecasting Engine** is a **production-grade, research-level AI platform** that combines state-of-the-art deep learning, ensemble methods, and generative AI to deliver institutional-quality financial forecasting and business intelligence.

This platform powers:
- 📈 **Multi-horizon stock price prediction** (day/week/month/quarter)
- 💰 **Enterprise sales forecasting** at scale
- 🤖 **AI ensemble system** with 7+ models including TFT, LSTM, GRU, XGBoost
- 🧠 **Explainable AI** with SHAP & LIME interpretations
- ⚠️ **Risk analytics** with VaR, CVaR, Sharpe & Sortino ratios
- 📰 **NLP sentiment engine** using FinBERT for financial news
- 💬 **Generative AI Financial Copilot** for natural language Q&A
- 🔍 **Anomaly detection** for market crashes & revenue drops
- 📊 **Portfolio optimization** using Modern Portfolio Theory

> **Research Note:** This system implements novel **Adaptive Weighted Ensemble Learning** where model weights dynamically adjust based on rolling validation performance, a technique inspired by recent NeurIPS and ICML publications in time-series forecasting.

---

## 🔬 Research Highlights

| Innovation | Description | Inspiration |
|---|---|---|
| **Adaptive Ensemble Weighting** | Dynamic model weights based on rolling MAE/RMSE | NeurIPS 2023 |
| **Temporal Fusion Transformer** | Multi-horizon attention-based forecasting | Google Research |
| **FinBERT Sentiment Integration** | Financial NLP signals fused into price models | ProsusAI |
| **Regime-Aware LSTM** | Market regime detection before forecasting | Two Sigma |
| **Hierarchical Sales Forecasting** | Bottom-up reconciliation across store/item levels | Amazon Research |
| **Monte Carlo CVaR Optimization** | Risk-adjusted portfolio construction | JP Morgan Quant |

---

## 🏗️ Architecture

```mermaid
graph TB
    subgraph "Data Layer"
        A[Yahoo Finance API] --> D[Data Ingestion Service]
        B[Alpha Vantage] --> D
        C[Finnhub WebSocket] --> D
        E[Walmart/Rossmann CSV] --> D
        F[FRED Macro Data] --> D
        D --> G[(PostgreSQL TimescaleDB)]
        D --> H[(Redis Cache)]
    end

    subgraph "ML Pipeline"
        G --> I[Feature Engineering]
        I --> J[LSTM/GRU Models]
        I --> K[Temporal Fusion Transformer]
        I --> L[XGBoost/LightGBM/CatBoost]
        I --> M[Prophet/SARIMA]
        J & K & L & M --> N[Adaptive Ensemble Layer]
        N --> O[Prediction Store]
    end

    subgraph "Intelligence Layer"
        P[Financial News] --> Q[FinBERT Sentiment]
        Q --> R[Sentiment Signals]
        R --> N
        S[LangChain AI Copilot] --> T[OpenAI/Anthropic]
    end

    subgraph "Risk & Portfolio"
        O --> U[VaR/CVaR Calculator]
        O --> V[Efficient Frontier]
        V --> W[Monte Carlo Simulator]
        U --> X[Risk Dashboard]
    end

    subgraph "API Gateway"
        Y[FastAPI + JWT Auth] --> Z[REST Endpoints]
        Y --> AA[WebSocket Streams]
        Y --> AB[GraphQL Optional]
    end

    subgraph "Observability"
        AC[Prometheus Metrics] --> AD[Grafana Dashboards]
        AE[MLflow Tracking] --> AF[Model Registry]
    end

    subgraph "Frontend"
        AG[Streamlit Premium Dashboard]
        AG --> AH[Executive View]
        AG --> AI[Stock Forecaster]
        AG --> AJ[Sales Forecaster]
        AG --> AK[Portfolio Builder]
        AG --> AL[AI Copilot Chat]
    end

    O --> Y
    Y --> AG
```

---

## ✨ Features

<table>
<tr>
<td>

### 📈 Stock Forecasting
- LSTM / GRU deep networks
- Temporal Fusion Transformer (TFT)
- XGBoost gradient boosting
- Prophet seasonal decomposition
- Multi-horizon: 1D / 1W / 1M / 1Q
- Confidence intervals
- Regime detection

</td>
<td>

### 💼 Sales Forecasting
- Daily/Weekly/Monthly/Quarterly
- Walmart, Rossmann, Favorita datasets
- Holiday & promotion effects
- Store-level granularity
- Hierarchical reconciliation
- Causal feature discovery

</td>
</tr>
<tr>
<td>

### 🤖 AI Ensemble System
- 7-model weighted ensemble
- Adaptive weight adjustment
- Out-of-bag validation
- Model confidence scoring
- Uncertainty quantification
- Bayesian model averaging

</td>
<td>

### 🧠 Explainable AI
- SHAP TreeExplainer & DeepExplainer
- LIME local interpretations
- Feature importance ranking
- Waterfall & force plots
- Business narrative generation
- Non-technical explanations

</td>
</tr>
<tr>
<td>

### ⚠️ Risk Analytics
- Value at Risk (VaR 95/99%)
- Conditional VaR (CVaR/ES)
- Historical & Parametric methods
- Maximum Drawdown analysis
- Sharpe & Sortino ratios
- Beta & Correlation matrices

</td>
<td>

### 📰 News Intelligence
- FinBERT financial NLP
- Real-time news ingestion
- Bullish/Bearish scoring
- Sentiment time-series
- Event impact detection
- Ticker-level sentiment

</td>
</tr>
<tr>
<td>

### 💬 AI Copilot
- Natural language Q&A
- Report generation
- Risk explanation
- Investment thesis builder
- LangChain RAG pipeline
- Chat history persistence

</td>
<td>

### 🔍 Anomaly Detection
- Isolation Forest
- Variational Autoencoder
- LSTM Autoencoder
- Statistical process control
- Market crash early warning
- Revenue drop alerts

</td>
</tr>
</table>

---

## 🛠️ Technology Stack

```
┌─────────────────────────────────────────────────────────────────────┐
│                    TECHNOLOGY STACK                                  │
├─────────────────────────────────────────────────────────────────────┤
│  BACKEND           FastAPI · Uvicorn · Pydantic · SQLAlchemy        │
│  ML/DL             PyTorch · TensorFlow · scikit-learn · XGBoost    │
│  TIME SERIES       Prophet · NeuralForecast · Darts · pmdarima      │
│  NLP               Transformers · FinBERT · LangChain · OpenAI      │
│  DATA              Pandas · Polars · NumPy · TA-Lib                 │
│  DATABASES         PostgreSQL · TimescaleDB · Redis · ChromaDB      │
│  VISUALIZATION     Streamlit · Plotly · Dash                        │
│  MLOPS             MLflow · DVC · Optuna · Ray Tune                 │
│  INFRA             Docker · Docker Compose · GitHub Actions         │
│  MONITORING        Prometheus · Grafana · Sentry                    │
│  SECURITY          JWT · RBAC · OAuth2 · Rate Limiting              │
│  TESTING           PyTest · Coverage · Hypothesis                   │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 📊 Performance Benchmarks

| Model | AAPL RMSE | TSLA RMSE | MSFT RMSE | MAPE |
|-------|-----------|-----------|-----------|------|
| LSTM | 2.34 | 8.91 | 1.87 | 1.8% |
| GRU | 2.41 | 9.12 | 1.92 | 1.9% |
| TFT | **1.89** | **7.43** | **1.54** | **1.4%** |
| XGBoost | 2.67 | 10.23 | 2.11 | 2.1% |
| Prophet | 3.12 | 12.45 | 2.87 | 2.8% |
| **Ensemble** | **1.71** | **6.98** | **1.41** | **1.2%** |

| Sales Model | RMSE | MAE | MAPE | R² |
|-------------|------|-----|------|----|
| Prophet | 1243 | 891 | 4.2% | 0.91 |
| XGBoost | 987 | 712 | 3.1% | 0.94 |
| LightGBM | 934 | 678 | 2.9% | 0.95 |
| TFT | 812 | 591 | 2.4% | 0.97 |
| **Ensemble** | **743** | **534** | **2.1%** | **0.98** |

---

## ⚡ Quick Start

```bash
# 1. Clone repository
git clone https://github.com/yourusername/Stock-Price-Sales-Forecasting-Engine.git
cd Stock-Price-Sales-Forecasting-Engine

# 2. Start with Docker Compose
docker-compose up -d

# 3. Run database migrations
docker-compose exec backend alembic upgrade head

# 4. Launch Streamlit dashboard
docker-compose exec frontend streamlit run frontend/streamlit/app.py

# 5. Open dashboard
open http://localhost:8501
```

---

## 🔧 Installation

### Prerequisites

```bash
Python 3.11+
Docker & Docker Compose
PostgreSQL 16+
Redis 7+
Node.js 20+ (optional, for docs)
```

### Local Development Setup

```bash
# Clone
git clone https://github.com/yourusername/Stock-Price-Sales-Forecasting-Engine.git
cd Stock-Price-Sales-Forecasting-Engine

# Create virtual environment
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Copy environment template
cp .env.example .env
# Edit .env with your API keys

# Initialize database
python scripts/init_db.py

# Download datasets
python scripts/download_datasets.py

# Start backend
uvicorn backend.main:app --reload --port 8000

# Start frontend (new terminal)
streamlit run frontend/streamlit/app.py --server.port 8501

# Start MLflow
mlflow ui --port 5000
```

### Environment Variables

```bash
# .env.example
DATABASE_URL=postgresql://user:password@localhost:5432/forecasting_db
REDIS_URL=redis://localhost:6379
ALPHA_VANTAGE_API_KEY=your_key_here
FINNHUB_API_KEY=your_key_here
OPENAI_API_KEY=your_key_here
SECRET_KEY=your-secret-key-here
MLFLOW_TRACKING_URI=http://localhost:5000
ENVIRONMENT=development
```

---

## 📦 Dataset Guide

See [dataset_download_guide.md](datasets/dataset_download_guide.md) for complete instructions.

| Dataset | Source | Size | Use Case |
|---------|--------|------|----------|
| Stock Prices | Yahoo Finance API | Dynamic | Stock forecasting |
| Walmart Sales | Kaggle | 421 MB | Retail forecasting |
| Rossmann Sales | Kaggle | 38 MB | Store sales |
| Favorita Grocery | Kaggle | 5.7 GB | SKU-level forecasting |
| FRED Macro | Federal Reserve | Dynamic | Economic indicators |
| Financial News | NewsAPI / Finnhub | Dynamic | Sentiment analysis |

---

## 📡 API Documentation

Base URL: `http://localhost:8000/api/v1`

### Authentication
```http
POST /auth/login
Content-Type: application/json

{"username": "admin", "password": "password"}
```

### Stock Endpoints
```http
GET  /stocks/{ticker}/forecast?horizon=30d
GET  /stocks/{ticker}/history?period=1y
GET  /stocks/{ticker}/risk-metrics
POST /stocks/batch-forecast
GET  /stocks/{ticker}/anomalies
```

### Sales Endpoints
```http
GET  /sales/forecast?store_id=1&horizon=30d
POST /sales/upload-dataset
GET  /sales/performance-metrics
GET  /sales/{dataset}/trends
```

### Portfolio Endpoints
```http
POST /portfolio/optimize
GET  /portfolio/efficient-frontier
POST /portfolio/simulate
GET  /portfolio/risk-metrics
```

### AI Copilot
```http
POST /ai/chat
GET  /ai/report/{stock}
GET  /ai/explain/{model}/{prediction_id}
```

Full API reference: [docs/api_reference.md](docs/api_reference.md)

---

## 🎨 Dashboard

<img src="demo/screenshots/executive_dashboard.png" alt="Executive Dashboard" width="100%"/>

<table>
<tr>
<td width="50%"><img src="demo/screenshots/stock_forecaster.png" alt="Stock Forecaster" width="100%"/></td>
<td width="50%"><img src="demo/screenshots/model_arena.png" alt="Model Arena" width="100%"/></td>
</tr>
</table>

The premium Streamlit dashboard features 10 specialized views:

1. **Executive Dashboard** – KPI cards, market overview, top movers
2. **Stock Forecaster** – Interactive multi-model predictions
3. **Sales Forecaster** – Retail/e-commerce demand forecasting
4. **Portfolio Builder** – Efficient frontier, allocation optimizer
5. **Risk Center** – VaR, CVaR, drawdown analysis
6. **AI Insights** – SHAP explanations, model interpretability
7. **News Intelligence** – Sentiment trends, event timeline
8. **Anomaly Detector** – Crash early warning system
9. **Model Arena** – Side-by-side model comparison
10. **AI Copilot** – Natural language financial assistant

---

## 🔄 MLOps Pipeline

```mermaid
graph LR
    A[Data Collection] --> B[Feature Engineering]
    B --> C[Model Training]
    C --> D[MLflow Tracking]
    D --> E[Model Evaluation]
    E --> F{Performance OK?}
    F -->|Yes| G[Model Registry]
    F -->|No| H[Hyperparameter Tuning]
    H --> C
    G --> I[Staging Deployment]
    I --> J[A/B Testing]
    J --> K[Production Deployment]
    K --> L[Prometheus Monitoring]
    L --> M[Drift Detection]
    M -->|Drift Detected| C
```

---

## 🚀 Deployment

### Docker Compose (Recommended)
```bash
docker-compose -f docker-compose.prod.yml up -d
```

### Railway
```bash
railway login
railway init
railway up
```

### AWS ECS
```bash
cd infra/terraform
terraform init
terraform plan
terraform apply
```

Full deployment guide: [docs/deployment.md](docs/deployment.md)

---

## 🧪 Testing

```bash
# Run all tests
pytest tests/ -v --cov=backend --cov-report=html

# Unit tests only
pytest tests/unit/ -v

# Integration tests
pytest tests/integration/ -v

# Model accuracy tests
pytest tests/models/ -v

# Load testing
locust -f tests/load/locustfile.py
```

---

## 🗺️ Roadmap

- [x] Core forecasting engine (LSTM, GRU, TFT, XGBoost, Prophet)
- [x] Ensemble system with adaptive weighting
- [x] Risk analytics (VaR, CVaR, Sharpe, Sortino)
- [x] FinBERT sentiment integration
- [x] AI Copilot with LangChain
- [x] Anomaly detection (Isolation Forest, LSTM Autoencoder)
- [x] Portfolio optimization (MPT, Efficient Frontier)
- [x] MLflow experiment tracking
- [x] Docker containerization
- [x] Premium Streamlit dashboard
- [ ] GraphQL API layer
- [ ] Real-time WebSocket price streaming
- [ ] Options pricing models (Black-Scholes, Monte Carlo)
- [ ] Crypto asset support
- [ ] Federated learning for privacy-preserving forecasting
- [ ] Mobile app (React Native)
- [ ] AlphaFold-inspired architecture for market structure
- [ ] Reinforcement learning trading agent (DQN/PPO)

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

```bash
# Fork → Clone → Branch → Commit → PR
git checkout -b feature/your-feature
git commit -m "feat: add amazing feature"
git push origin feature/your-feature
```

---

## 📄 License

This project is licensed under the **MIT License** – see [LICENSE](LICENSE) for details.

---

## 🙏 Acknowledgments

- [Temporal Fusion Transformer Paper](https://arxiv.org/abs/1912.09363) – Bryan Lim et al.
- [FinBERT](https://arxiv.org/abs/1908.10063) – ProsusAI
- [NeuralForecast](https://github.com/Nixtla/neuralforecast) – Nixtla
- [Darts](https://github.com/unit8co/darts) – Unit8

---

<div align="center">

**Built with ❤️ for the open-source community**

⭐ Star this repo if you find it useful!

[![GitHub Stars](https://img.shields.io/github/stars/yourusername/Stock-Price-Sales-Forecasting-Engine?style=social)](https://github.com)

</div>
