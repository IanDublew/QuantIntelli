<div align="center">

# QuantIntelli+ ⚽️

### A Hybrid AI Agent for Quantitative Football Prediction Analysis

<p align="center">
  <img src="https://pbs.twimg.com/media/GtFKUeRWYAAVVrP?format=png&name=small"  alt="QuantIntelli+ Banner" width="700"/>
</p>

**QuantIntelli+ is not just another prediction bot. It's a sophisticated, two-stage analytical agent that fuses a battle-tested statistical model with a powerful, context-aware RAG-LLM pipeline.**

![Python](https://img.shields.io/badge/Python-3.9+-blue?style=for-the-badge&logo=python)
![Framework](https://img.shields.io/badge/Framework-Gradio-orange?style=for-the-badge)
![LLM](https://img.shields.io/badge/LLM-Google%20Gemini-4285F4?style=for-the-badge)
![Database](https://img.shields.io/badge/Database-Supabase-3ECF8E?style=for-the-badge&logo=supabase)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)

</div>

## 🔗 Quick Links
- **[Try QuantIntelli+ Live](https://iandublew.github.io/quantintelli-UI/)**
- **[View Prediction Analysis](https://iandublew.github.io/QuantIntelli-Leaderboard)**

---

## ✨ Core Features   

🧠 **Dual-Engine Analysis:**  
Combines a fast **XGBoost model** for baseline statistical predictions with a deep **Google Gemini LLM** for contextual analysis.

🌐 **Advanced RAG Pipeline:**  
Dynamically searches the web using **Tavily, Google, and DuckDuckGo** to gather real-time, relevant information like team news, injuries, form, and H2H stats.

📄 **Content Enrichment:**  
Goes beyond snippets by fetching and parsing full-text articles from top-ranking search results to provide deeper context to the LLM.

📊 **Structured Analytical Output:**  
Generates a detailed, professional-grade report with sections for **Dual Recommendation**, **Conflict Resolution**, **Market Efficiency**, and **Risk Analysis**.

💾 **Persistent Session Logging:**  
Uses **Supabase** to log every prediction and its subsequent analysis, creating a traceable record of the agent's reasoning.

🕹️ **Interactive UI:**  
Built with **Gradio** for an intuitive, easy-to-use interface that guides the user through the two-stage analysis process.

---

## 🚀 How It Works: The Analysis Pipeline

QuantIntelli+ operates a unique two-stage workflow to deliver its insights.

### 1. **🎯 Stage 1: The Statistical Prediction**
*   A user inputs match odds (e.g., `Liverpool vs Chelsea 2.1 3.4 3.8`).
*   The pre-trained **XGBoost model** instantly processes the odds and outputs a baseline prediction (Home Win, Draw, or Away Win) with probabilities.
*   This initial session is logged to **Supabase**, creating a unique ID for the match.

### 2. **🔍 Stage 2: The Deep-Dive Analysis**
*   The user toggles "Analysis Mode" and asks for a deeper dive.
*   **The RAG pipeline activates:**
    *   It generates targeted queries (`"Liverpool injury news"`, `"Chelsea recent form"`, etc.).
    *   It dispatches these queries across multiple search providers (Tavily, Google) for comprehensive coverage.
    *   Top results are "enriched" by fetching the full webpage content.
*   **The LLM synthesizes the data:**
    *   A meticulously crafted prompt is sent to **Google Gemini**, containing the statistical prediction, market odds, and all the enriched web context.
*   **The final report is generated:**
    *   Gemini returns a structured, multi-part analysis.
    *   This analysis, including the extracted contextual outcome, is logged back to the original Supabase record.

---

## 🛠️ Tech Stack

| Category         | Technologies Used |
|------------------|-------------------|
| **AI/ML**        | `XGBoost`, `Scikit-learn`, `Google Gemini API` |
| **Data & Backend** | `Python`, `Pandas`, `NumPy` |
| **Web Retrieval (RAG)** | `Tavily API`, `Google Custom Search API`, `DuckDuckGo Search`, `BeautifulSoup` |
| **Database**     | `Supabase` |
| **Frontend**     | `Gradio` |

---

## 🏁 Getting Started

### Prerequisites
- Python 3.9+
- Access to Google Gemini, Tavily, and Google Custom Search APIs
- A Supabase project

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/quantintelli.git 
cd quantintelli
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Set Up Environment Variables
Create a `.env` file in the root directory and populate it with your API keys and credentials. Use `.env.example` as a template:

```env
# Google Gemini API
GOOGLE_API_KEY="your_gemini_api_key"

# Supabase
SUPABASE_URL="your_supabase_project_url"
SUPABASE_SERVICE_KEY="your_supabase_service_key"
SUPABASE_PREDICTION_TABLE_NAME="your_table_name" # e.g., 'predictions'

# Web Search APIs (Optional, but recommended for full functionality)
TAVILY_API_KEY="your_tavily_api_key"
GOOGLE_API_KEY_CS="your_google_cloud_platform_api_key"
GOOGLE_CSE_ID="your_google_custom_search_engine_id"
```

### 4. Place Model Files
Ensure your trained model and scaler files are placed in the `model/` directory:
```
model/xgboost_model.pkl
model/scaler.pkl
```

### 5. Run the Application
```bash
python app.py
```
Navigate to the local URL provided by Gradio (e.g., `http://127.0.0.1:7860`) to start interacting with QuantIntelli+.

## ⚠️ Disclaimer
This tool is for educational and research purposes only. It is an exploration of hybrid AI systems and should not be used for actual financial betting. The predictions and analyses generated are not financial advice. Always gamble responsibly.

## 📬 Feedback & Contributions
Contributions are welcome! If you'd like to contribute, please open an issue or submit a pull request. For questions or feedback, feel free to reach out via GitHub Discussions.

