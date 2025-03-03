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
    Please input your income:  1000
    

    Your total balance is: PHP 1000.0
    
    What do you want to do next?
    (1) Add to my wallet
    (2) Track expenses
    (3) Check Balance
    (4) Exit
    

    Select an option:  2
    Please input your expenses:  500
    

    You've spent PHP 500.0
    Your remaining balance is: PHP 500.0
    You still have money. Good job!
    
    What do you want to do next?
    (1) Add to my wallet
    (2) Track expenses
    (3) Check Balance
    (4) Exit
    


    ---------------------------------------------------------------------------

    KeyboardInterrupt                         Traceback (most recent call last)

    Cell In[21], line 55
         52             display_options()
         53             continue
    ---> 55 main_prog()
    

    Cell In[21], line 14, in main_prog()
         12 while True:
         13     try:
    ---> 14         user = int(input("Select an option: "))
         16         if user == 1:
         17             i = float(input("Please input your income: "))
    

    File ~\anaconda3\Lib\site-packages\ipykernel\kernelbase.py:1262, in Kernel.raw_input(self, prompt)
       1260     msg = "raw_input was called, but this frontend does not support input requests."
       1261     raise StdinNotImplementedError(msg)
    -> 1262 return self._input_request(
       1263     str(prompt),
       1264     self._parent_ident["shell"],
       1265     self.get_parent("shell"),
       1266     password=False,
       1267 )
    

    File ~\anaconda3\Lib\site-packages\ipykernel\kernelbase.py:1305, in Kernel._input_request(self, prompt, ident, parent, password)
       1302 except KeyboardInterrupt:
       1303     # re-raise KeyboardInterrupt, to truncate traceback
       1304     msg = "Interrupted by user"
    -> 1305     raise KeyboardInterrupt(msg) from None
       1306 except Exception:
       1307     self.log.warning("Invalid Message:", exc_info=True)
    

    KeyboardInterrupt: Interrupted by user



```python

```
