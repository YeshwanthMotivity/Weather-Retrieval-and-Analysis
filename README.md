# Weather-Retrieval-and-Analysis
🌦️ Weather-RAG: Weather Retrieval and Analysis using RAG
Weather-RAG is a machine learning project that enables semantic search and analysis of weather data using Retrieval-Augmented Generation (RAG) techniques. It combines sentence-transformer embeddings with FAISS indexing for natural language queries over weather data, and now includes a powerful real-time weather comparison feature using the OpenWeatherMap API.

🚀 Features
🔍 Natural Language Querying – Ask weather-related questions like “What was the temperature on July 1st, 2013?” and get instant answers.
⚡ No API Key for RAG Search – Entire semantic search system works locally without any API key.
📊 Real-Time Weather Comparison – Compare today's weather (real-time) with the same day in 2009 using live data from OpenWeatherMap.
🌐 Gradio Web Interface – Clean, interactive UI for entering queries and getting comparisons without code.
🧩 Efficient Embedding & FAISS Indexing – Quick semantic retrieval using vector similarity.
🔄 Extendable – Easily adaptable to any tabular dataset like finance, sales, or health data.

🛠️ Tech Stack
Tool/Library	Purpose
SentenceTransformers	Embedding rows for semantic similarity search
FAISS	Efficient vector indexing for fast retrieval
Pandas	Data manipulation and filtering
Gradio	Interactive user interface (no frontend coding)
Requests	Fetch real-time weather data via OpenWeatherMap API


📄 How It Works
1. Semantic Search (RAG) Workflow
Load the weather dataset (2009–2016).
Convert rows into readable text.
Generate embeddings (all-MiniLM-L6-v2) and index with FAISS.
User inputs a natural language question → semantic search returns top matches.
2. Real-Time Weather Comparison
Fetch real-time weather from OpenWeatherMap using requests.
Filter dataset to get weather on today's date in 2009.
Compare temperature, humidity, and wind speed.
Display both in a side-by-side format with a Gradio UI.

📸 Architecture Diagram
![Building LLM application using RAG - by Sagar Gandhi](https://github.com/user-attachments/assets/ed66e623-e3d4-4d7f-8d90-971f29771dfe)

🧠 Models Used
🔹 1. Sentence Transformer – Semantic Search
Model: sentence-transformers/all-MiniLM-L6-v2
Purpose: Encodes user query and dataset passages into vectors for semantic similarity search.
Enables relevant data retrieval from historical dataset (RAG retrieval step).
🔹 2. Google Flan-T5 Base – Text Generation
Model: google/flan-t5-base
Purpose: Generates human-readable answers based on the retrieved 2009 data.
Lightweight, fast, and trained for natural language understanding and generation.



✨ Interactive Modules
Weather-RAG offers two powerful interfaces for exploring and comparing weather data.

🌤️ Section 1: Ask the Past – Explore Historical Weather (2009)
🔎 Semantic Search on Jena Climate Data (First 10,000 rows, 2009 only)
Use this interface to retrieve weather facts from the year 2009 using natural language. It uses Retrieval-Augmented Generation (RAG) to understand and answer your queries intelligently.
💡 Example Queries:
What was the average temperature in July 2009?
How much did it rain on March 15th, 2009?
What was the wind speed in Jena on December 1st, 2009?
Was it sunny in Jena on June 5th, 2009?

🌡️ Section 2: Past vs Present – Real-Time Weather Comparison
🌐 Compare Today’s Weather with the Same Day in 2009 (Jena Climate Dataset)
This interface allows you to fetch real-time weather data for any city and compare it with the temperature in Jena on the same date in 2009.
💡 Example Queries:
Compare today's temperature with 2009.
Is it warmer today in [City] than on this day in 2009?
What’s the weather in Hyderabad now compared to March 20th, 2009?
How does today’s humidity compare with 2009 in Jena?

📂 Dataset Info
Loaded the first 10,000 rows of the Jena Climate 2009–2016 dataset for performance and quick processing.
Filtered to only 2009 data for both modules to ensure accurate historical retrieval and comparison.

💻 How to Run
1. Clone Repository:
git clone https://github.com/YeshwanthMotivity/Weather-RAG.git
2. Install Dependencies:
pip install faiss-cpu gradio transformers sentence-transformers pandas tqdm numpy requests
3. Launch Notebook:
Open Preedict__Weather_using_RAG.ipynb in Google Colab or Jupyter Notebook.
Follow step-by-step instructions to build embeddings and launch Gradio.

🖥️ Gradio Interface – Real-Time Comparison
Enter a weather-related question.
Enter a city name to fetch real-time weather.
Get:
📅 Weather from 2009 (for today’s date)
🌍 Current weather details (temp, humidity, wind speed, description)
➕ Temperature difference between 2009 and today


🌐 OpenWeatherMap Integration
API Key Required: Add your OpenWeatherMap API key to fetch real-time data.
Privacy: API key is only used locally; no data is stored or transmitted externally.
Customization: Easily switch city or extend to multi-day forecasts.


📈 Future Scope
Add visual plots for comparison (temperature over time).
Integrate LLM-based summarization for richer query responses.
Expand dataset support (e.g., multiple years, other cities).
Deploy with Flask or FastAPI for real-time APIs.


📬 Contact
For queries or collaboration:
📧 yeshwanth.mudimala@motivitylabs.com

