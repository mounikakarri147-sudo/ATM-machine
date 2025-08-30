# ATM-machine
This project is a simple ATM Machine simulation in Python that allows users to perform basic banking operations such as PIN authentication, balance inquiry, cash withdrawal, deposit, and language selection. It is a beginner-friendly project that demonstrates the use of loops, conditionals, and user input handling in Python.
def ATM():
    balance=int(input("enter balance:"))
    pin="8836"
    withdraw_limit=10000

    print("    Welcome To ATM Machine    ")
    print("Select Language")
    print("1.English")
    print("2.Telugu")
    print("3.Hindi")
    lang=input("enter language:")
    if lang=="English":
        lang='English'
    elif lang=="Telugu":
        lang='Telugu'
    elif lang=="Hindi":
        lang='Hindi'
    else:
        print("invalid choice.Defaulting to English.")
        lang="English"
    print(f'selected language:{lang}')

    enter_pin=(input("enter pin number"))
    if enter_pin!=pin:
        print("you entered wrong pin.Please Try Again.")
        return
    print("---->ATM MENU<----")
    print("1.Check Balance")
    print("2.Deposit_Money")
    print("3.Withdraw_Money")
    print("4.exit")
    choice=(input('enter choice:'))
    if choice=="Check Balance":
        print(f'your account balance is {balance}')
        
    elif choice=="Deposit_Money":
        money=int(input("enter deposit money:"))
        balance+=money
        print(f'{money} is deposited to your account successfully ')
        print(f'updated account balance is {balance}')
       
    elif choice=="Withdraw_Money":
        amount=int(input("enter withdraw amount:"))
        if amount>withdraw_limit:
            print("withdraw limit exceeded!")
        elif amount>balance:
            print("Insufficient")
        else:
            print(f"{amount} withdrawn successfully")
            balance=balance-amount
            print(f"Now you have balance in ur account is {balance}")
    elif choice=="Exit":
        print("Thank You.Come And Visit Again")
ATM()
