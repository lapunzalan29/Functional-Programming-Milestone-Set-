# Functional Programming (Milestone Set)


```python
def add_income(income, total):
    return total + income
def subtract_expense(expense, total):
    return total - expense
def calculate_balance(income, expense):
    return income - expense
```


```python
def display_options(previous_action=None):
    print("\nWhat do you want to do next?")
    if previous_action == "add_income":
        print("(1) Add to my wallet again")
    else:
        print("(1) Add to my wallet")
    
    if previous_action == "track_expense":
        print("(2) Track expenses again")
    else:
        print("(2) Track expenses")
    
    print("(3) Check Balance")
    print("(4) Exit")
```


```python
def main_prog():
    total_income = 0
    total_expense = 0
    
    print("\nWelcome to your personal finance manager!")
    print("How can I help you today?")
    print("(1) Add to my wallet")
    print("(2) Track expenses")
    print("(3) Check Balance")
    print("(4) Exit")
    
    while True:
        try:
            user = int(input("Select an option: "))
            
            if user == 1:
                i = float(input("Please input your income: "))
                total_income = add_income(i, total_income)
                print(f"Your total balance is: PHP {calculate_balance(total_income, total_expense)}")
                display_options()
                continue
            
            elif user == 2:
                e = float(input("Please input your expenses: "))
                if e > calculate_balance(total_income, total_expense):
                    total_expense += e
                    print("Oh no! You have spent more than you have!")
                else:
                    total_expense += e
                    print(f"You've spent PHP {total_expense}")
                    print(f"Your remaining balance is: PHP {calculate_balance(total_income, total_expense)}")
                    print("You still have money. Good job!")
                display_options()
                continue
            
            elif user == 3:
                print(f"You currently have PHP {calculate_balance(total_income, total_expense)}")
                display_options()
                continue
            
            elif user == 4:
                print("Goodbye!")
                break
            
            else:
                print("Woopsie! You made an oopsie! Please enter a valid option.")
                display_options()
                continue
        
        except ValueError:
            print("Woopsie! You made an oopsie! Please enter a number.")
            display_options()
            continue

main_prog()
```

    
    Welcome to your personal finance manager!
    How can I help you today?
    (1) Add to my wallet
    (2) Track expenses
    (3) Check Balance
    (4) Exit
    

    Select an option:  1
    Please input your income:  10000
    

    Your total balance is: PHP 10000.0
    
    What do you want to do next?
    (1) Add to my wallet
    (2) Track expenses
    (3) Check Balance
    (4) Exit
    

    Select an option:  2
    Please input your expenses:  2000
    

    You've spent PHP 2000.0
    Your remaining balance is: PHP 8000.0
    You still have money. Good job!
    
    What do you want to do next?
    (1) Add to my wallet
    (2) Track expenses
    (3) Check Balance
    (4) Exit
    

    Select an option:  3
    

    You currently have PHP 8000.0
    
    What do you want to do next?
    (1) Add to my wallet
    (2) Track expenses
    (3) Check Balance
    (4) Exit
    

    Select an option:  4
    

    Goodbye!
    


```python

```
