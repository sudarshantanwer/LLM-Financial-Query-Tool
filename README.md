# GenAI-Powered Financial Query Assistant

A GenAI-driven system that answers financial questions strictly from structured data (CSV files) and safely refuses to answer when data is missing — no hallucinations, no internet guessing.

---

## 🔍 What This Project Does

This project lets you ask natural language questions like:

* Which fund has the highest market value?
* Which securities are causing losses?
* Which fund trades the most but earns the least?
* How did funds perform year-wise?

The system:

1. Uses GenAI to understand your question
2. Converts it into a structured data query
3. Executes it on real financial CSV data
4. Returns an answer only if the data supports it
5. Otherwise replies:

   > “Sorry can not find the answer”

---

## 🧠 Architecture

```
User Question
   ↓
LLM converts question to Pandas query
   ↓
Query runs on CSV data
   ↓
If result exists → Explain in English
If not → Safe refusal
```

LLM is used for language understanding, not for truth.

---

## 📂 Data Sources

* `holdings.csv` → Portfolio holdings and P&L
* `trades.csv` → Trade and transaction data

These files are the only source of truth.

---

## ⚙️ Tech Stack

* Python
* Pandas
* OpenAI API
* Google Colab / Jupyter Notebook

---

## 🚀 How to Run

### 1. Upload Files

Upload these files in your notebook:

* `holdings.csv`
* `trades.csv`

### 2. Set API Key

In Google Colab:

* Click 🔑 Secrets panel
* Add key: `OPENAI_API_KEY`

Or locally:

```bash
export OPENAI_API_KEY="your_key_here"
```

### 3. Install Dependencies

```bash
pip install pandas openai
```

### 4. Run Notebook

Run all cells from top to bottom.

---

## 🧪 Example Questions

```text
Which fund has the highest market value?
Which securities have negative year-to-date P&L?
What are the top 5 securities by market value?
Which fund trades the most but earns the least?
How did funds perform in 2022?
Who is the CEO of Google?
```

Last question will return:

> Sorry can not find the answer

---

## 🛡️ Why No Hallucination

* LLM never answers directly
* LLM only generates queries
* Pandas executes real data
* Guardrail blocks empty or invalid results

---

## 📽️ Demo

A short demo video is included showing:

* Data-backed answers
* Complex financial queries
* Safe refusal on unknown questions

---

## 🎯 Use Cases

* Financial analytics tools
* Enterprise data chatbots
* Portfolio analysis systems
* Decision support systems

---

## 🧩 Project Type

This is not classic RAG.

It is:

> LLM-Orchestrated Structured Data Retrieval System

LLM handles language, Pandas handles truth.

---

## 📌 License

MIT License (or your choice)

---

## 🤝 Contributing

Pull requests and ideas welcome!
