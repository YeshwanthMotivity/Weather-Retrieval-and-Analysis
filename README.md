# Weather Retrieval and Analysis

A comprehensive toolkit for weather analysis, prediction, and retrieval-augmented generation (RAG) using Machine Learning and Large Language Models.

This repository contains notebooks that demonstrate how to:
1.  **Retrieve & Analyze Weather Data**: Using OpenWeatherMap API and historical datasets.
2.  **Predict Future Weather**: Using Random Forest Regression on historical climate data.
3.  **RAG Weather Assistant**: A conversational assistant that uses semantic search (FAISS) and LLMs (Gemini, Groq/Llama) to answer weather-related questions based on retrieved data.

## Project Structure

```
Weather-Retrieval-and-Analysis/
├── DataSet/
│   ├── jena_climate_2009_2016.csv       # Historical weather dataset
│   ├── OpenWeatherMap_API_Parameters.pdf # API documentation ref
│   └── country_codes.pdf                # Country codes ref
├── Weather_Prediction_Rag.ipynb         # RAG Assistant (OpenWeatherMap + Gemini)
├── Random_forest_Weather_and_Retrieval.ipynb # RF Prediction + Groq Analysis
├── Weather-Retrieval-and-Analysis.ipynb # Data Analysis & Local RAG experiments
├── requirements.txt                     # Python dependencies
└── README.md                            # Project documentation
```

## Notebook Overview & Comparison

This project includes three distinct notebooks, each serving a specific purpose in the weather analysis workflow:

| Notebook File | Primary Purpose | Key Technologies | Data Source |
| :--- | :--- | :--- | :--- |
| **`Weather_Prediction_Rag.ipynb`** | **Live RAG Assistant** <br> A user-facing app that answers questions about *current* and *forecasted* weather. | • OpenWeatherMap API <br> • Gemini-2.5 Flash <br> • FAISS & Sentence-Transformers <br> • Gradio (Enhanced UI) | Live API Data |
| **`Random_forest_Weather_and_Retrieval.ipynb`** | **ML Prediction & Advisory** <br> Predicts temperature for a specific future date using historical patterns and gives specific advice. | • Random Forest Regressor <br> • Groq (Llama 3.1) <br> • Gradio | `jena_climate_2009_2016.csv` (Historical) |
| **`Weather-Retrieval-and-Analysis.ipynb`** | **Core Analysis & Experimentation** <br> The foundational notebook for exploring data, generating embeddings, and testing local LLMs. | • Pandas Data Analysis <br> • FAISS (Deep Dive) <br> • Local LLM (`google/flan-t5-base`) | `jena_climate_2009_2016.csv` (Historical) |

### Detailed Breakdown

#### 1. `Weather_Prediction_Rag.ipynb` (The Assistant)
This is the main **conversational interface**. It does not train a model on historical CSV data. Instead, it hits the **OpenWeatherMap API** to get real-time 5-day forecasts, indexes that data on-the-fly using FAISS, and uses **Google Gemini** to answer natural language questions (e.g., "Will it rain on Friday?").

#### 2. `Random_forest_Weather_and_Retrieval.ipynb` (The Forecaster)
This notebook focuses on **predictive modeling**. It trains a **Random Forest** model on the historical Jena Climate dataset to predict the temperature for any given date (past or future) based on day/month/year features. It then uses **Groq** to interpret that numerical prediction into friendly advice.

#### 3. `Weather-Retrieval-and-Analysis.ipynb` (The Lab)
This is the **experimental backend**. It demonstrates the underlying mechanics of:
*   Loading and preprocessing the massive Jena Climate dataset.
*   Generating vector embeddings for thousands of row entries.
*   Setting up a FAISS index manually.
*   Using a locally downloaded LLM (`flan-t5-base`) for retrieval-augmented generation without external API calls.


---
 
**Architecture Diagram**  
![Building LLM application using RAG - by Sagar Gandhi](https://github.com/user-attachments/assets/ed66e623-e3d4-4d7f-8d90-971f29771dfe)

---

## Setup & Installation

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/Yeshwanth2124/Weather-Retrieval-and-Analysis.git
    cd Weather-Retrieval-and-Analysis
    ```

2.  **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3.  **Environment Variables**:
    These notebooks use various APIs. It is recommended to set them as environment variables or input them when prompted. **Do not hardcode keys in the notebooks.**

    *   `WEATHER_API_KEY`: OpenWeatherMap API Key
    *   `GEMINI_API_KEY`: Google Gemini API Key
    *   `GROQ_API_KEY`: Groq API Key

## Usage

You can run the notebooks using Jupyter Lab, Jupyter Notebook, or VS Code.

*   **For the Live Weather Assistant**: Run `Weather_Prediction_Rag.ipynb`.
*   **For ML Prediction**: Run `Random_forest_Weather_and_Retrieval.ipynb`.

---

## 📬  About the Team
• Mentor / Manager: Mr. Venkata Ramana Sudhakar Polavarapu

• Team Members: Yeshwanth Goud Mudimala
                Sai Dinesh Bejjanki 
                Uma Venkata Karthik Vallabhaneni
                Pushpaja Udayagiri
                Sai Seetu Reddy Bommareddy

---

### 📬 Contact
For any questions, feel free to reach out at:

**Email 📧:** yeshwanth.mudimala@motivitylabs.com
