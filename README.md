# CS-PROJECT-Q2
Carnation Group 3: Credo, Barrientos, Illustrisimo

Code:

# -------------------------------
# Simple PyBudget Program
# -------------------------------

transactions = []  
savings_goal = None

def add_transaction():
    print("\n--- Add Transaction ---")
    t_type = input("Type (income/expense): ").lower()

    if t_type not in ["income", "expense"]:
        print("Invalid type. Must be 'income' or 'expense'.")
        return

    amount = float(input("Amount: "))
    category = input("Category (e.g., food, salary, transport): ")

    transactions.append({
        "type": t_type,
        "amount": amount,
        "category": category
    })

    print("Transaction added!")

def view_transactions():
    print("\n--- All Transactions ---")
    if not transactions:
        print("No transactions yet.")
        return
    
    for i, t in enumerate(transactions, start=1):
        print(f"{i}. {t['type'].title()} - ₱{t['amount']} ({t['category']})")

def summary():
    print("\n--- Summary ---")
    income = sum(t["amount"] for t in transactions if t["type"] == "income")
    expenses = sum(t["amount"] for t in transactions if t["type"] == "expense")
    balance = income - expenses

    print(f"Total Income: ₱{income}")
    print(f"Total Expenses: ₱{expenses}")
    print(f"Balance: ₱{balance}")

def set_savings_goal():
    global savings_goal
    print("\n--- Savings Goal ---")
    savings_goal = float(input("Enter savings goal amount: "))
    print(f"Goal set to ₱{savings_goal}")

def check_savings_progress():
    if savings_goal is None:
        print("\nNo savings goal set yet.")
        return

    income = sum(t["amount"] for t in transactions if t["type"] == "income")
    expenses = sum(t["amount"] for t in transactions if t["type"] == "expense")
    current_savings = income - expenses

    print("\n--- Savings Progress ---")
    print(f"Goal: ₱{savings_goal}")
    print(f"Current Savings: ₱{current_savings}")

    if current_savings >= savings_goal:
        print("🎉 You reached your savings goal!")
    else:
        print(f"You need ₱{savings_goal - current_savings} more.")

def menu():
    while True:
        print("\n===== PyBudget Menu =====")
        print("1. Add Transaction")
        print("2. View Transactions")
        print("3. View Summary")
        print("4. Set Savings Goal")
        print("5. Check Savings Progress")
        print("6. Exit")

        choice = input("Choose an option (1-6): ")

        if choice == "1":
            add_transaction()
        elif choice == "2":
            view_transactions()
        elif choice == "3":
            summary()
        elif choice == "4":
            set_savings_goal()
        elif choice == "5":
            check_savings_progress()
        elif choice == "6":
            print("Goodbye!")
            break
        else:
            print("Invalid choice, try again.")

# start program
menu()
