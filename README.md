# 🤖 Interview Prep Chatbot

An interactive Streamlit application that simulates a job interview and provides instant AI-generated feedback. Users describe their background, choose a target company, role, and seniority level, then go through a short mock interview conducted by an AI "HR executive." At the end, the chatbot scores the performance and gives constructive feedback.

## Features

- **Personalized setup** — enter your name, experience, and skills
- **Role targeting** — choose seniority level (Junior / Mid-level / Senior), position (Data Scientist, Data Engineer, ML Engineer, BI Analyst, Software Engineer, Financial Analyst), and company (Amazon, Meta, Udemy, 365 Company, Nestle, LinkedIn, Spotify)
- **Live mock interview** — an OpenAI-powered "HR executive" asks questions and responds in real time (streamed responses)
- **Automatic feedback** — after 5 exchanges, the interview ends and the AI scores your performance (1–10) with detailed feedback
- **Restart anytime** — reset the session and start a new interview from scratch

## Tech Stack

- [Streamlit](https://streamlit.io/) — web app framework
- [OpenAI API](https://platform.openai.com/) (`gpt-4o`) — powers both the interviewer and the feedback engine
- [streamlit-js-eval](https://pypi.org/project/streamlit-js-eval/) — used to reload the page on restart

## Getting Started

### Prerequisites

- Python 3.9+
- An OpenAI API key

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Touseefurrehman/Intreview-Tool-ChatBot-Interview-Prep-.git
   cd Intreview-Tool-ChatBot-Interview-Prep-
   ```

2. Install the dependencies:
   ```bash
   pip install streamlit openai streamlit-js-eval
   ```

3. Add your OpenAI API key to Streamlit secrets. Create a file at `.streamlit/secrets.toml`:
   ```toml
   OPENAI_API_KEY = "your-api-key-here"
   ```

### Running the App

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`.

## How It Works

1. **Setup stage** — Fill in your personal info and target role/company, then click **Start Interview**.
2. **Interview stage** — Introduce yourself and respond to up to 5 questions from the AI interviewer.
3. **Feedback stage** — Click **Get Feedback** to receive a score out of 10 along with detailed, constructive feedback based on the conversation.
4. **Restart** — Click **Restart Interview** to reset the app and try again.

## Project Structure

```
.
├── app.py          # Main Streamlit application
├── .gitignore
└── README.md
```

## Notes

- Never commit your `secrets.toml` file or API key to version control — make sure `.streamlit/secrets.toml` is listed in `.gitignore`.
- Each user response is limited to 1000 characters, and the interview ends automatically after 5 user messages.

## License

This project is open source and available for personal or educational use.
