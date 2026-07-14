# 🌍 AI Travel Planner Agentic Application



An AI-powered travel planning assistant built using FastAPI, Streamlit, and LangChain, integrating multiple tools like weather forecasting, expense calculation, place search, and currency conversion to generate personalized trip plans.

---

## 🚀 Features

- Automated Travel Planning — Generates detailed itineraries based on natural language input.
- Weather Integration — Fetches live weather data and forecasts using OpenWeatherMap API.
- Expense Calculation — Calculates hotel costs, total trip expenses, and daily budgets.
- Currency Conversion — Converts between currencies in real time.
- Place Information Search — Suggests attractions, restaurants, and activities using Google Places & Tavily APIs.
- Trip Report Generation — Exports the AI-generated itinerary as a Markdown document.

---

## 🧩 Project Structure

📦 ai-travel-planner
├── agent/
│   └── agentic_workflow.py
├── utils/
│   ├── currency_converter.py
│   ├── expense_calculator.py
│   ├── weather_info.py
│   ├── save_to_document.py
│   ├── config_loader.py
├── weather_info_tool.py
├── expense_calculator.py
├── currency_conversion.py
├── place_info_search.py
├── model_loader.py
├── main.py
├── streamlit_app.py
├── requirements.txt
└── README.md

---

## ⚙️ Installation

1️⃣ Clone the Repository
git clone https://github.com/yourusername/ai-travel-planner.git
cd ai-travel-planner

2️⃣ Create a Virtual Environment
python -m venv venv
source venv/bin/activate    # On macOS/Linux
venv\Scripts\activate       # On Windows

3️⃣ Install Dependencies
pip install -r requirements.txt

---

## 🔑 Environment Variables

Create a .env file in the project root and add your API keys:

OPENWEATHERMAP_API_KEY=your_openweathermap_api_key
GROQ_API_KEY=your_groq_api_key
OPENAI_API_KEY=your_openai_api_key
GOOGLE_API_KEY=your_google_places_api_key

---

## 🧠 How It Works

1. User enters a travel-related query in the Streamlit app (e.g., “Plan a 5-day trip to Goa with a budget of ₹40,000.”)  
2. Query is sent to the FastAPI backend (main.py), which triggers the Agentic Graph built via LangChain.  
3. The graph coordinates multiple tools:  
   - Fetches weather info (WeatherInfoTool)  
   - Searches attractions & restaurants (PlaceInfoSearchTool)  
   - Converts currencies (CurrencyConverter)  
   - Calculates total trip cost (ExpenseCalculatorTool)  
4. The LLM (Groq or OpenAI) processes the information and generates a structured travel plan.  
5. The plan is saved as a Markdown file via save_to_document.py.  
6. The Streamlit frontend displays the formatted response.  

---

## 🧪 Running the Application

Start the FastAPI backend:
uvicorn main:app --reload

Launch the Streamlit frontend:
streamlit run streamlit_app.py

Open your browser and go to: http://localhost:8501

---


## 📦 Output Files

All generated travel plans are stored as Markdown files in the output/ directory.

Example: output/AI_Trip_Planner_2025-11-08_14-30-00.md

---

## 🧰 Tech Stack

Backend: FastAPI  
Frontend: Streamlit  
AI Engine: LangChain + Groq/OpenAI  
Weather Data: OpenWeatherMap API  
Place Search: Google Places API / Tavily Search  
File Export: Markdown (UTF-8)  
Environment: Python 3.10+

---

## 📜 License

MIT License

---

## 👨‍💻 Author

Developed by: Atriyo  
GitHub: https://github.com/yourusername  
Email: your.email@example.com

---

## 🧠 Future Improvements

- Add flight booking APIs  
- Integrate live hotel booking systems  
- Add user login for saving past trips  
- Support multiple LLM backends dynamically  
- Incorporate real-time travel advisories
