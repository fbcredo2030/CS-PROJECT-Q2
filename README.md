# 💰 PyBudget – Personal Finance Tracker
**CS Project – 3rd Quarter Submission**
**Group 3: Credo, Barrientos, Illustrisimo**

## 📌 Project Overview
**PyBudget** is a command-line personal finance tracking system developed in Python.
The program allows users to record income and expenses, monitor financial summaries, and track savings goals.

## 🚀 Features
* Add income transactions
* Add expense transactions
* Categorize transactions (e.g., food, salary, transport)
* View all recorded transactions
* View financial summary (total income, expenses, and balance)
* Set savings goal
* Check savings progress

## 🗂 File Structure

```
PyBudget/
│
├── main.py
└── README.md
```

* **main.py** – Contains the main menu, transaction handling, savings logic, and overall program execution
* **README.md** – Project documentation

## ⚙️ Methodology

### Core Implementation

Transactions are stored in a list of dictionaries:

```python
{
    "type": "income" or "expense",
    "amount": float,
    "category": string
}
```

Financial summaries are calculated using Python list comprehensions:

```python
income = sum(t["amount"] for t in transactions if t["type"] == "income")
expenses = sum(t["amount"] for t in transactions if t["type"] == "expense")
```

Savings progress is computed as:

```
Current Savings = Total Income − Total Expenses
```

The program compares the current savings with the user’s savings goal and provides feedback.

## 💻 Technologies Used

| Technology | Purpose                   |
| ---------- | ------------------------- |
| Python     | Main programming language |
| Git        | Version control           |
| GitHub     | Repository hosting        |

Python was selected because it is readable, beginner-friendly, and suitable for logic-based applications.

## 🖥 System Design
This project is a **Command-Line Interface (CLI)** application.

* Backend logic and user interaction exist within the same Python environment.
* No external database is used.
* Data is stored temporarily during runtime.
* Future improvements may include persistent storage or a graphical interface.

## 📥 Installation & Usage

### 1. Clone the repository

```
git clone https://github.com/fbcredo2030/CS-PROJECT-Q2.git
```

### 2. Navigate to the project folder

```
cd pybudget
```

### 3. Run the program

```
python main.py
```

## 📊 Current Project Status

✅ Core functionality complete
✅ Documentation updated
✅ Repository organized
✅ Ethical reflection included
🔄 Future improvements planned (data persistence, GUI integration)

## 🧠 Programming & Computing Ethics
This project follows ethical programming standards aligned with the
Association for Computing Machinery Code of Ethics (2018).

### Ethical Considerations

**1. Respect for Intellectual Property**
* All code is original.
* External references are properly cited.

**2. User Privacy**
* No personal identifying information is collected.
* No external data transmission occurs.
* Financial data is not permanently stored.

**3. Accessibility & Inclusion**
* Clear prompts and readable formatting.
* Simple interface for ease of use.

**4. Professional Responsibility**
In accordance with the ACM Code of Ethics, developers must:

* Contribute to society and human well-being
* Avoid harm
* Be honest and trustworthy

PyBudget promotes responsible financial management and ethical software development.

## 📚 Reference (APA Format)
Association for Computing Machinery. (2018). *ACM Code of Ethics and Professional Conduct*. [https://www.acm.org/code-of-ethics](https://www.acm.org/code-of-ethics)

## 👥 Contributors
* Credo
* Barrientos
* Illustrisimo
