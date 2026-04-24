# 📝 End-to-End Text Summarizer — NLP Pipeline with FastAPI & Docker

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-Transformers-yellow?style=for-the-badge&logo=huggingface&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-Web%20App-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Containerised-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Project Overview

This is a **production-ready, end-to-end NLP project** that builds a **Text Summarisation** system using a pre-trained transformer model. The project follows a clean, modular ML pipeline architecture with **FastAPI** for serving predictions and **Docker** for containerised deployment.

The pipeline covers the complete ML lifecycle — from data ingestion to model serving.

---

## 🎯 Objectives

- Build a modular, production-grade text summarisation pipeline
- Implement multi-stage pipelines: ingestion → validation → transformation → training → evaluation
- Serve the model via a **FastAPI** REST API
- Containerise the application using **Docker**

---

## 🏗️ Architecture & Workflow

The project follows a structured pipeline approach:

```
1. Update config.yaml       → Define paths and parameters
2. Update params.yaml       → Model hyperparameters
3. Update entity            → Data class definitions
4. Update configuration     → Config manager in src/config
5. Update components        → Core logic (ingestion, validation, transformation)
6. Update pipeline          → Stage-wise pipeline orchestration
7. Update main.py           → Run full pipeline
8. Update app.py            → FastAPI application server
```

### Pipeline Stages

| Stage | Module | Description |
|-------|--------|-------------|
| Stage 01 | `data_ingestion.py` | Download and extract dataset |
| Stage 02 | `data_validation.py` | Validate required files exist |
| Stage 03 | `data_transformation.py` | Tokenise and prepare data for model |

---

## 📁 Project Structure

```
text-summarizer-project/
│
├── src/textSummarizer/
│   ├── components/          # Data ingestion, validation, transformation
│   ├── pipeline/            # Stage-wise pipeline scripts
│   ├── config/              # Configuration manager
│   ├── entity/              # Data entity definitions
│   ├── utils/               # Utility functions (common.py)
│   ├── constants/           # Global constants
│   └── logging/             # Logging setup
│
├── config/config.yaml       # Project configuration
├── params.yaml              # Model parameters
├── main.py                  # Pipeline orchestrator
├── app.py                   # FastAPI application
├── setup.py                 # Package setup
├── requirements.txt         # Dependencies
├── Dockerfile               # Docker configuration
├── template.py              # Project scaffolding script
└── README.md
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.8+ | Core language |
| HuggingFace Transformers | Pre-trained summarisation model |
| FastAPI | REST API serving |
| Docker | Containerised deployment |
| PyYAML | Config file management |
| Jupyter | Research & experimentation |

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/homeshwarnelakurthi/text-summarizer-project.git
cd text-summarizer-project
```

### 2. Create a virtual environment
```bash
conda create -n textsum python=3.8 -y
conda activate textsum
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the full pipeline
```bash
python main.py
```

### 5. Start the API server
```bash
python app.py
```

### 6. Run with Docker
```bash
docker build -t text-summarizer .
docker run -p 8080:8080 text-summarizer
```

---

## 🔗 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/` | Health check |
| `POST` | `/predict` | Submit text → receive summary |
| `GET` | `/train` | Trigger training pipeline |

---

## 👨‍💻 Author

**Homeswar Rao Nelakurthi**  
[![GitHub](https://img.shields.io/badge/GitHub-homeshwarnelakurthi-181717?style=flat&logo=github)](https://github.com/homeshwarnelakurthi)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
