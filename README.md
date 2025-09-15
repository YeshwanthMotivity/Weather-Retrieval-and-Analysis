🌦️ Weather-RAG: Weather Retrieval & Real-Time Comparison
Weather-RAG is a machine learning project that uses Retrieval-Augmented Generation (RAG) to perform semantic search on historical weather data. It combines sentence-transformer embeddings with FAISS indexing for natural language queries and features a real-time weather comparison tool using the OpenWeatherMap API.

📌 Features
🔍 Natural Language Querying - Ask questions like, "What was the temperature on July 1st, 2013?"

⚡ No API Key for RAG - The core semantic search system works locally without any external API key.

📊 Real-Time Comparison - Compare today's weather (live data) with the same day in 2009.

🌐 Gradio Web Interface - A clean, interactive UI makes it easy to enter queries and get results.

🧩 Efficient Retrieval - Quick semantic search using sentence-transformer embeddings and FAISS indexing.

🔄 Adaptable - The system can be easily adapted to any tabular dataset (e.g., finance, sales, health).

🛠️ Tech Stack
Component	Tool / Library	Purpose
Embedding	SentenceTransformers	Encodes text into vectors for semantic search.
Vector Database	FAISS	Efficient vector indexing for fast retrieval.
Data Handling	Pandas	Manipulation and filtering of the dataset.
User Interface	Gradio	Creates an interactive web UI.
API Integration	Requests	Fetches real-time data from OpenWeatherMap.

Export to Sheets
🧠 Models Used
Sentence Transformer (all-MiniLM-L6-v2): Encodes user queries and dataset passages into vectors for semantic search, enabling relevant data retrieval from the historical dataset.

Google Flan-T5 Base (google/flan-t5-base): Generates human-readable answers based on the retrieved data. This model is lightweight and efficient for natural language generation.

📄 How It Works
1. Semantic Search (RAG) Workflow
Loads the historical weather dataset (2009–2016).

Converts each row into readable text and generates embeddings using all-MiniLM-L6-v2.

Indexes the embeddings with FAISS.

When a user inputs a query, the system performs a semantic search to find the top matching rows from the dataset.

2. Real-Time Weather Comparison
Uses the OpenWeatherMap API to fetch current weather data.

Filters the historical dataset to get weather on the same date in 2009.

Displays a side-by-side comparison of temperature, humidity, and wind speed using the Gradio UI.

✨ Interactive Modules
Weather-RAG provides two interfaces for exploring and comparing weather data.

🌤️ Section 1: Ask the Past
This module uses RAG to answer natural language queries about the Jena Climate Dataset from 2009.

Example Queries:

"What was the average temperature in July 2009?"

"How much did it rain on March 15th, 2009?"

"Was it sunny in Jena on June 5th, 2009?"

🌡️ Section 2: Past vs Present
This module compares real-time weather with the historical data.

Example Queries:

"Compare today's temperature with 2009."

"Is it warmer today in [City] than on this day in 2009?"

"How does today’s humidity compare with 2009 in Jena?"

💻 How to Run
Prerequisites
Python 3+

An OpenWeatherMap API key for real-time comparisons.

Installation Steps
Clone the repository:

Bash

git clone https://github.com/YeshwanthMotivity/Weather-RAG.git
cd Weather-RAG
Install dependencies:

Bash

pip install faiss-cpu gradio transformers sentence-transformers pandas tqdm numpy requests
Launch the notebook:
Open Preedict__Weather_using_RAG.ipynb in Google Colab or Jupyter Notebook and follow the step-by-step instructions.

📈 Future Scope
Data Visualization: Add visual plots to compare temperature and other metrics over time.

Summarization: Integrate LLM-based summarization for richer query responses.

Expand Dataset: Support multiple years or other cities.

Production Deployment: Deploy the application with frameworks like Flask or FastAPI for real-time APIs.

📬 Contact
For any questions or collaboration, feel free to reach out:

Email: yeshwanth.mudimala@motivitylabs.com
