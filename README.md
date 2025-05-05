# SHL Assessment Recommender API

![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

This is a FastAPI-based backend service that provides SHL assessment recommendations based on a given job description. It uses semantic similarity (via the `sentence-transformers` library) to find the most relevant assessments from a preloaded dataset.

## 🚀 Features

- RESTful API built with FastAPI
- CORS-enabled for frontend integration
- Semantic search using `intfloat/e5-small-v2` embedding model
- Precomputed embeddings for fast recommendations
- Supports POST `/recommend` endpoint with JSON payload

## 📦 Project Structure
shl-recommender/
├── main.py # FastAPI app with CORS and route setup
├── models.py # Pydantic models for request/response validation
├── recommender.py # Embedding-based recommendation logic
├── data/
│ └── shl_assessments.json # SHL assessment data
├── requirements.txt # Python dependencies
└── README.md # This file


## 🎯 API Endpoints

### Health Check
`GET /health`

[https://api-g7q1.onrender.com/health](https://api-g7q1.onrender.com/)

{
  "status": "ok"
}

Recommend Assessments
POST /recommend

Request:

How It Works
Data Loading: Preloads SHL assessments dataset
Embedding: Uses intfloat/e5-small-v2 model to create embeddings
Recommendation:
Embeds incoming job description
Computes cosine similarity against all assessments
Returns top matches

💻 Local Development
Prerequisites
Python 3.9+

Installation
git clone [https://github.com/amancd/shl-Recommendation-System](https://github.com/amancd/SHL-Recommendation-System/)
cd shl-recommender
pip install -r requirements.txt

Running the Server
uvicorn main:app --reload

Similary
cd frontend
npm run dev
