🛡️ SentinelRAG: Cybersecurity & Fraud Intelligence
SentinelRAG is an AI-powered assistant designed to bridge the gap between complex banking fraud regulations (CFPB/FFIEC) and real-time transaction data.

🚀 Setup Instructions for Windows
1. Clone the Repository
Open PowerShell or Command Prompt and run:

Bash
git clone https://github.com/aadinathdeepak/SentinelRAG.git
cd SentinelRAG
2. Set Up Virtual Environment
Creating a virtual environment ensures that the project libraries don't conflict with other Python apps.

Bash
python -m venv venv
.\venv\Scripts\activate
Note: If you get an error in PowerShell about scripts being disabled, run:

Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

3. Install Dependencies
Install all required modules, including LangChain, Streamlit, and Plotly.

Bash
pip install -r requirements.txt
4. Download the Dataset
The main dataset is too large for GitHub and must be downloaded manually.

Link: Kaggle Credit Card Fraud Detection.

Action: Download the creditcard.csv file.

Placement: Create a folder at data/raw/ (if it doesn't exist) and move the file into it.

5. Configure Groq API Key
You need an API key to power the AI's "brain".

Link: Groq Cloud Console.

Guide: Log in, click "Create API Key", and copy the generated key.

Action: Create a file named .env in the root folder of the project and paste the following line:

Plaintext
GROQ_API_KEY=your_key_here
6. Run the Project
You must process the documents once to build the local search database before launching the app.

Step A: Ingest Data

Bash
python src/ingest.py
Step B: Launch Chatbot

Bash
streamlit run src/app.py
📊 Presentation Highlight
Ask the Bot: "What is the CFPB rule on investigating disputed charges?".

Technical Check: "List the three factors of authentication mentioned in the FFIEC guidelines.".

Visuals: Check the "Show Dataset Analytics" box in the sidebar to see real-time fraud trends from the CSV.

Simulate: Click "Simulate Fraud Alert" to pull a real fraud sample from the dataset and have the AI analyze it against banking manuals.
