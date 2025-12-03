## DONE BY

Mohammede Aitezazuddin Ahmed  
Student Number: 100829388
# ExplainIt-3X  
### Multi-Level Explanation System for Course Assignment

This project is a command-line tool that generates three levels of explanations for any topic using a Large Language Model (LLM). The goal of the assignment was to design a small but functional LLM-based system that can explain concepts clearly, handle basic safety concerns, and demonstrate evaluation using custom test cases.

---

## Project Overview

ExplainIt-3X takes a user-provided topic and produces:
- An explanation suitable for a young student  
- A general explanation for an adult  
- A more detailed explanation written at a university level  
- One simple self-check question

Along with generating explanations, the system includes:
- Basic prompt‑injection detection  
- Logging of all requests  
- An automated evaluation mode using `tests.json`

The focus of the project is on clean structure, safety considerations, and demonstrating understanding of LLM behavior.

---

## Project Structure

```
LLM-Assignment/
│
├── app.py                # Main application logic
├── tests.json            # Evaluation tests
├── requirements.txt      # Python dependencies
├── .env.example          # Example environment variable file
└── logs/
    └── requests.log      # Log file created automatically
```

---

## Setup Instructions

### 1. Clone the repository
```
git clone <your-repo-url>
cd LLM-Assignment
```

### 2. Install dependencies
```
pip install -r requirements.txt
```

### 3. Get an OpenRouter API Key
To run the application, you will need a free API key from OpenRouter.  
Create an account and generate a key here:
https://openrouter.ai/sign-in?redirect_url=https%3A%2F%2Fopenrouter.ai%2Fsettings%2Fkeys

Once logged in, go to **Settings → Keys** and create a new API key.

### 4. Create and configure the `.env` file
```
cp .env.example .env
```

Open `.env` and add your OpenRouter API key:
```
OPENROUTER_API_KEY=your-api-key-here
```

---

## Running the Application

### Generate an explanation
```
python3 app.py explain "deadlock"
```

### Run the full evaluation suite
```
python3 app.py eval
```

### View available commands
```
python3 app.py help
```

---

## Evaluation

The system uses `tests.json` to check behavior against different categories of inputs, including:
- Technical computer science topics  
- Definition-style questions  
- Attempts to bypass or manipulate system instructions  
- Inputs that should succeed or fail based on safety rules  

An example result:
```
Results: 14/15 passed (93%)
```

This score reflects both strong performance and realistic limitations.

---

## Safety Considerations

The system detects and blocks several forms of instruction manipulation, such as attempts to override the system prompt or reset rules. These checks are simple by design but demonstrate awareness of common vulnerabilities in LLM systems.

---

## Logging

All requests are logged in the `logs` directory. Each log entry includes:
- Timestamp  
- Topic  
- Latency  
- Token usage  
- Whether the request succeeded  

This allows for monitoring and further analysis of model behavior.

---

## Model Choice

The project uses the `meta-llama/llama-3.1-8b-instruct` model through the OpenRouter API. The model was chosen because it is lightweight, free to access through OpenRouter, and produces results that are appropriate.

---

## Demo Recording

A short recording demonstrating how to run the application, generate explanations, and execute the evaluation suite can be added here.

Once the video is uploaded to GitHub, replace the placeholder link below with the actual video link:

[Watch the demo]()
