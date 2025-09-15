# 🌦️ Weather-RAG: Weather Retrieval & Real-Time Comparison

Weather-RAG is a machine learning project that uses Retrieval-Augmented Generation (RAG) to perform semantic search on historical weather data. It combines sentence-transformer embeddings with FAISS indexing for natural language queries and features a real-time weather comparison tool using the OpenWeatherMap API.

---

## 📌 Features

- **🔍 Natural Language Querying:** –  Ask questions like, "What was the temperature on July 1st, 2013?" 
- **⚡ No API Key for RAG:** – The core semantic search system works locally without any external API key. 
- **📊 Real-Time Comparison:** – Compare today's live weather with the historical data from the same day in 2009.  
- **🌐 Gradio Web Interface:** – Provide natural, human-like speech responses via **ElevenLabs** or Deepgram TTS  
- **🧩 Efficient Retrieval:** – Easily adaptable to different languages  
- **🔄 Adaptable:** – Suitable for high-volume call centers and multi-channel support

---

## 🛠️ Technologies Used

|      Component       |      Tool / Library    |                        Purpose                         |
| ---------------------| -----------------------| -------------------------------------------------------|
| **Embedding**        | `SentenceTransformers` | Encodes text into vectors for semantic search.         |
| **Vector Database**  | `FAISS`                | Provides efficient vector indexing for fast retrieval. |
| **Data Handling**    | `Pandas`               | Used for manipulating and filtering the dataset.       | 
| **User Interface**   | `Gradio`               | Creates an interactive web UI.                         |
| **API Integration**  | `Requests`             | Fetches real-time data from the OpenWeatherMap API.    |

---


## 📄 How It Works
## Semantic Search (RAG) Workflow
1. The system loads a historical weather dataset (2009–2016).
2. Each row is converted into a readable text passage and embedded into a vector using a sentence-transformer model.
3. These vectors are then indexed with FAISS for fast similarity search.
4. When a user inputs a query, the system finds the most semantically similar passages from the dataset.

## Real-Time Weather Comparison
1. The application uses the OpenWeatherMap API to fetch the current weather for a specified city.
2. It filters the historical dataset to find the weather from the same date in 2009.
3. The two sets of data are displayed side-by-side in the Gradio UI for easy comparison.
 
**Architecture Diagram Placeholder**  
![Building LLM application using RAG - by Sagar Gandhi](https://github.com/user-attachments/assets/ed66e623-e3d4-4d7f-8d90-971f29771dfe)
---

## Interactive Modules
Weather-RAG offers two interfaces for exploring and comparing weather data.

## 🌤️ Section 1: Ask the Past
This module uses RAG to answer natural language questions about the Jena Climate Dataset from 2009.
Example Queries:
1. "What was the average temperature in July 2009?"
2. "How much did it rain on March 15th, 2009?"
3. "Was it sunny in Jena on June 5th, 2009?"

## 🌡️ Section 2: Past vs Present
This module compares real-time weather with the historical data from the same date in 2009.
Example Queries:
1. "Compare today's temperature with 2009."
2. "Is it warmer today in [City] than on this day in 2009?"
3. "How does today’s humidity compare with 2009 in Jena?"

---

## 📦 Setup Instructions

### **Prerequisites**
- Python 3.9+  
- An OpenWeatherMap API key for real-time weather comparisons. 
 
### **Installation Steps**
```bash
# 1. Clone this repository
git clone https://github.com/YeshwanthMotivity/Weather-RAG.git
cd Weather-RAG

# 2. Install dependencies
pip install faiss-cpu gradio transformers sentence-transformers pandas tqdm numpy requests

# 3. Launch the notebook:
Open Preedict__Weather_using_RAG.ipynb in Google Colab or Jupyter Notebook and follow the step-by-step instructions.
```
---
###  Future Scope
1. Data Visualization: Add visual plots to compare temperature and other metrics over time.
2. Summarization: Integrate LLM-based summarization for richer query responses.
3. Expand Dataset: Support multiple years or other cities.
4. Production Deployment: Deploy the application with frameworks like Flask or FastAPI to create real-time APIs.
5. 
---

## 📬 Contact
For any questions or collaboration, feel free to reach out:

Email: yeshwanth.mudimala@motivitylabs.com

---
