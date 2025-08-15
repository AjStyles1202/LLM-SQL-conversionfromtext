#  LLM-SQL Conversion from Natural Language

**An End-to-End LLM + LangChain project that connects directly to a MySQL database and answers business queries in plain English.**

With this system, a store manager can simply type:

> *"How many white Adidas t-shirts are left in stock?"*
> and get the exact answer — powered by **Google Gemini (PaLM)**, **LangChain**, and **MySQL**.

---

## Features

* **Natural Language to SQL** – Convert user questions into syntactically correct SQL queries.
* **Database-Backed Intelligence** – Runs queries directly on a live MySQL database.
* **Few-Shot Learning** – Improves query generation accuracy using curated examples.
* **Hugging Face Embeddings + ChromaDB** – Vector store for semantic similarity search.
* **Streamlit UI** – Clean, interactive interface for non-technical users.
* **Real-World Use Case** – Designed for a retail scenario (inventory, sales, discounts).

---

##  Example Queries

* How many total t-shirts are left in stock?
* How many XS-size white Nike t-shirts are available?
* What is the total price of inventory for all S-size t-shirts?
* If we sell all small Adidas shirts today after discounts, how much revenue will we generate?

---

## Tech Stack

* **LLM:** Google Gemini (PaLM API via LangChain)
* **Framework:** LangChain
* **Embeddings:** HuggingFace `all-MiniLM-L6-v2`
* **Vector Store:** ChromaDB
* **UI:** Streamlit
* **Database:** MySQL
* **Prompting:** Few-Shot Examples

---

## Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/AjStyles1202/LLM-SQL-conversionfromtext.git
   cd LLM-SQL-conversionfromtext
   ```

2. **Create a virtual environment** (optional but recommended)

   ```bash
   python -m venv venv
   source venv/bin/activate     # Mac/Linux
   venv\Scripts\activate        # Windows
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Get your Google API key**

   * Visit [MakerSuite](https://makersuite.google.com/)
   * Create a `.env` file in the project root:

     ```env
     GOOGLE_API_KEY="your_api_key_here"
     ```

5. **Set up the database**

   * Start your MySQL server.
   * Run the SQL script:

     ```sql
     SOURCE database/db_creation_atliq_t_shirts.sql;
     ```

---

## ▶️ Usage

Run the Streamlit app:

```bash
streamlit run main.py
```

The app will open in your browser. Type your question in natural language, and the system will:

1. Convert it to SQL
2. Run the query
3. Display the result

---

## 📂 Project Structure

```
├── main.py                  # Streamlit UI
├── langchain_helper.py      # LangChain logic & query generation
├── few_shots.py             # Few-shot examples
├── requirements.txt         # Project dependencies
├── database/
│   └── db_creation_atliq_t_shirts.sql
└── .env                     # API key & environment variables
```

---

## 💡 Future Improvements

* Support for **multiple databases** (PostgreSQL, SQLite).
* Add **chart/graph visualizations** for query results.
* Integrate **user authentication** for secure access.
* Fine-tune LLM for specific domain vocabularies.
