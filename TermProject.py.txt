import json

DATA_FILE = "budget_data.json"

def get_valid_float(prompt):
while True:
try:
value = float(input(prompt))
if value < 0:
raise ValueError
return value
except ValueError:
print("Please enter a valid positive number.")

def add_income(data):
amount = get_valid_float("Enter income amount: ")
data["income"] += amount
print("Income added successfully.")

def add_expense(data):
category = input("Enter expense category: ")
amount = get_valid_float("Enter expense amount: ")
data["expenses"].append({"category": category, "amount": amount})
print("Expense added successfully.")

def view_summary(data):
total_expenses = sum(expense["amount"] for expense in data["expenses"])
balance = data["income"] - total_expenses

print("\n----- Budget Summary -----")
print(f"Total Income: ${data['income']:.2f}")
print(f"Total Expenses: ${total_expenses:.2f}")
print(f"Remaining Balance: ${balance:.2f}")

def save_data(data):
with open(DATA_FILE, "w") as file:
json.dump(data, file)
print("Data saved successfully.")

def load_data():
try:
with open(DATA_FILE, "r") as file:
return json.load(file)
except FileNotFoundError:
return {"income": 0, "expenses": []}

def main():
data = load_data()

while True:
print("\n1. Add Income")
print("2. Add Expense")
print("3. View Summary")
print("4. Save & Exit")

choice = input("Choose an option: ")

if choice == "1":
add_income(data)
elif choice == "2":
add_expense(data)
elif choice == "3":
view_summary(data)
elif choice == "4":
save_data(data)
print("Goodbye!")
break
else:
print("Invalid option. Please try again.")

if __name__ == "__main__":
main()