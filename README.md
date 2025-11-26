# TranSQLation
## Text-to-SQL Mini Engine

### 📌 Description

This project aims to build a **Text-to-SQL generator**: the user writes a natural language query such as:

> *"Donne-moi les ventes du mois dernier"*

The system automatically translates it into a valid **SQL query**.

This combines **NLP**, **machine learning**, and **database querying**.

---

### 🎯 Objectives

* Convert natural language text into SQL queries.
* Provide a simple **web interface** for user input.
* Build a small **SQLite database** for testing queries.
* Integrate an NLP model (T5 or GPT API) to generate SQL.
* Use **Flask** as the backend and API server.

---

### 🛠️ Technologies Used

* **SQLite** – lightweight local database.
* **Flask** – backend REST API.
* **T5 (Text-to-Text Transformer)** or **GPT API** – NLP model for SQL generation.
* **HTML/CSS/JS** – frontend UI.

---

### 📦 Deliverables

* A working **SQLite database** with sample tables/data.
* A simple **web interface** where the user writes natural queries.
* A **Flask API** that receives natural text and returns SQL.
* The **NLP model** (fine‑tuned T5 or API call to GPT).

---

### 📁 Project Structure (Suggested)

```
project/
│── app.py                # Flask backend
│── model/                # T5 model or GPT API logic
│── database/
│   ├── schema.sql        # DB structure
│   ├── data.sql          # Fake data
│   └── database.db       # SQLite file
│── static/
│   ├── style.css         # Frontend styling
│── templates/
│   └── index.html        # Frontend UI
│── README.md             # Documentation
```

---

### 🚀 How It Works

#### 1️⃣ User enters a natural query

Example: *"Liste les employés dont le salaire dépasse 3000".*

#### 2️⃣ The request is sent to the Flask backend

`POST /generate-sql`

#### 3️⃣ The NLP model processes the text

* Preprocessing
* Model inference (T5 or GPT)

#### 4️⃣ Flask returns the SQL query

Example: `SELECT * FROM employees WHERE salary > 3000;`

#### 5️⃣ (Optional) Execute the SQL on SQLite and return the results.

---

### ▶️ How to Run the Project

#### **1. Install dependencies**

```bash
pip install flask transformers sqlite3
```

#### **2. Initialize the database**

```bash
sqlite3 database/database.db < database/schema.sql
sqlite3 database/database.db < database/data.sql
```

#### **3. Start the Flask server**

```bash
python app.py
```

#### **4. Open the interface**

Go to: `http://localhost:5000`

---

### 🔬 NLP Model Options

#### **Option A: Use a pre-trained T5 model**

* Fine‑tune on the "Spider" dataset (optional)
* Or use zero‑shot prompting

#### **Option B: Use GPT API**

Example prompt:

```
Convert this natural language to SQL:
"Donne-moi les ventes du mois dernier"
```

---

### 📝 Example Queries

| Natural Language                   | SQL Output                                                                               |
| ---------------------------------- | ---------------------------------------------------------------------------------------- |
| Ventes du mois dernier             | `SELECT * FROM sales WHERE date >= '2024-10-01';`                                        |
| Nombre d'employés par département  | `SELECT department, COUNT(*) FROM employees GROUP BY department;`                        |
| Liste des produits les plus vendus | `SELECT product, SUM(quantity) FROM sales GROUP BY product ORDER BY SUM(quantity) DESC;` |

---

### 🔮 Possible Improvements

* Add authentication
* Improve SQL validation
* Support multiple databases (MySQL, PostgreSQL)
* Add auto‑execution of queries and display results

---

### 👥 Team Workflow Suggestions

* **Person 1:** Flask API
* **Person 2:** Database + SQL
* **Person 3:** NLP model
* **Person 4:** Frontend

---

### 📚 License

This project is free to use for educational purposes.

---
### 📞 Contact
If you have any questions or suggestions, feel free to contact me:

**Name:Aymen El Makhlouk**

**Email:aymenelmakhlouk@gmail.com**

**LinkedIn:https://www.linkedin.com/in/aymen-e-899a00288/**
