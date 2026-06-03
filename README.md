#  AI Career Assistant  🤖

A conversational web application built with **Streamlit** that helps students and job seekers navigate their career journey — from skill-building and resume advice to personalized roadmaps and daily motivation.

---

##  Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the App](#running-the-app)
- [Usage Guide](#usage-guide)
- [File Reference](#file-reference)
- [Customization](#customization)
- [Future Improvements](#future-improvements)

---

## Overview

AI Career Assistant is an interactive Streamlit dashboard designed to support learners at any stage of their career. Users enter their career goal and skill level, then receive a personalized roadmap, daily learning tips, and a chatbot that answers questions about skills, resumes, jobs, and motivation — all in one clean, dark-themed interface.

---

## Features

- ** Career Roadmap Generator** — Input your goal (e.g., Data Scientist, Web Developer) and generate a step-by-step learning plan tailored to your skill level and daily availability.
- **Daily Tips** — Rotating tips to keep learners focused and consistent.
- ** Career Chatbot** — A rule-based assistant that responds to queries about:
  - Skills and learning strategies
  - Career paths and job roles
  - Resume and CV writing
  - Learning roadmaps
  - Motivation and burnout
- ** Sidebar Controls** — Set your career goal, skill level (Beginner / Intermediate / Advanced), and hours available per day.
- ** Dark Theme UI** — Custom CSS with gradient card components for a modern look.

---

## Project Structure

```
ai-career-assistant/
│
├── app.py          # Main Streamlit application — layout, sidebar, chatbot UI
├── chatbot.py      # Chatbot logic — keyword-based intent matching and responses
├── style.css       # Custom CSS — dark theme, chat bubbles, tip cards
└── README.md       # Project documentation
```

---

## Prerequisites

- Python **3.8** or higher
- pip (Python package manager)

---

## Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/ai-career-assistant.git
   cd ai-career-assistant
   ```

2. **Create and activate a virtual environment** *(recommended)*

   ```bash
   python -m venv venv

   # On macOS/Linux
   source venv/bin/activate

   # On Windows
   venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install streamlit
   ```

---

## Running the App

```bash
streamlit run app.py
```

The app will open automatically in your browser at `http://localhost:8501`.

---

## Usage Guide

1. **Set your career goal** in the sidebar (e.g., `AI Engineer`, `Data Scientist`).
2. **Select your skill level** — Beginner, Intermediate, or Advanced.
3. **Choose your daily study hours** using the slider.
4. Click **🧠 Generate AI Roadmap** to get your personalized plan.
5. Scroll down to the **Chatbot** section and type any career-related question, then click **Send**.

### Example Chatbot Queries

| You type...              | Bot responds with...                                         |
|--------------------------|--------------------------------------------------------------|
| `hello`                  | Greeting and offer to help                                   |
| `how do I learn faster`  | Tips on daily practice, projects, and fundamentals           |
| `what career suits me`   | Prompt to share interests for tailored career guidance       |
| `how to write a resume`  | Resume best practices — skills, projects, impact             |
| `I'm feeling demotivated`| Encouragement about consistency over speed                   |

---

## File Reference

### `app.py`
The entry point for the Streamlit app. Handles:
- Page configuration and CSS injection
- Sidebar inputs (career goal, skill level, hours)
- Daily tips display
- Chat session state management and message rendering

### `chatbot.py`
Contains the `get_bot_reply(user_input)` function. Uses keyword matching across intent categories:

| Intent      | Trigger Keywords                          |
|-------------|-------------------------------------------|
| Greetings   | hi, hello, hey                            |
| Skills      | skill, learn, practice                    |
| Career      | career, job, role                         |
| Resume      | resume, cv                                |
| Roadmap     | roadmap, plan                             |
| Motivation  | motivate, tired, stress, demotivated      |

### `style.css`
Custom styles applied via `st.markdown`. Defines:
- `.chat-box` — Dark gradient bubble for chat messages
- `.tip-box` — Dark gradient card for daily tips

---

## Customization

**Add new chatbot intents** — Open `chatbot.py` and add a new keyword list and `elif` block:

```python
interview = ["interview", "prepare", "questions"]

elif any(word in q for word in interview):
    return "Research the company, practice common questions, and prepare a STAR-format story."
```

**Change the color theme** — Edit gradient values in `style.css`:

```css
.chat-box {
    background: linear-gradient(135deg, #your-color-1, #your-color-2);
}
```

**Swap to an AI-powered backend** — Replace `get_bot_reply()` in `chatbot.py` with a call to an LLM API (e.g., Anthropic Claude, OpenAI GPT) for dynamic, context-aware responses.

---

## Future Improvements

- Integrate a live LLM API for intelligent, context-aware responses
- Add user authentication and saved career progress
- Generate downloadable PDF roadmaps
- Include curated resource links (courses, books, projects) per career path
- Add multi-language support

---

## License

This project is open-source and available under the [MIT License](LICENSE).

---

*Built with ❤️ using [Streamlit](https://streamlit.io)*
