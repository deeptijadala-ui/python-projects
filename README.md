1. Introduction
This project is a desktop-based ATM (Automated Teller Machine) simulator developed using Python's Tkinter library. The goal was to replicate the core functionality of a real ATM system in a software environment, helping understand GUI programming, file I/O, and basic application logic in Python.
The application lets a user log in using a card number and PIN, check their account balance, deposit or withdraw money, and view a mini statement of recent transactions — just like a real ATM would.
2. Objectives
Build a functional GUI application using Python and Tkinter
Implement basic banking operations: login, deposit, withdrawal, balance check, transaction history
Store account data persistently using a JSON file (simulating a database)
Practice real-world concepts like input validation, error handling, and session management
3. Technologies Used
TechnologyPurposePython 3.xCore programming languageTkinterGUI framework (built into Python)JSONFile-based data storageos, datetimeFile handling and timestamps
No external libraries or pip packages are required. Everything used is part of Python's standard library.
4. Features
Login System

Users enter a card number and a 4-digit PIN
Login is validated against stored account records
Error messages shown for wrong card or wrong PIN

Balance Inquiry

Displays the account holder's name and available balance
Balance updates in real-time after any transaction

Deposit

Enter any amount to deposit (up to ₹1,00,000 per transaction)
Quick-fill buttons for common amounts (₹500, ₹1000, ₹2000, ₹5000)
Transaction is recorded with a timestamp

Withdrawal

Enter amount to withdraw (multiples of ₹100 only, max ₹25,000)
Balance is checked before allowing the transaction
Quick-fill buttons included

Transaction History (Mini Statement)

Shows the last 10 transactions
Credits shown in green, debits in red
Displays date, type, and amount for each transaction

Logout

Secure logout clears session data
Confirmation dialog before logging out

5. Project Structure

ATM_Simulator/
│
├── atm_simulator.py      ← Main application file (all code is here)
├── accounts.json         ← Auto-created on first run (stores account data)
└── README.md             ← This documentation file


6. How to Run
Step 1: Make sure Python 3 is installed on your system.
You can check by running:
python --version
Step 2: Navigate to the project folder.
Step 3: Run the application:
Step 4: Use the demo accounts to test:
Card Number	PIN	Account Holder
1234	1111	Rahul Sharma
5678	2222	Priya Mehta
7. Application Flow
   Start
  ↓
Login Screen (Card No. + PIN)
  ↓ (valid credentials)
Main Menu
  ├── Balance Inquiry → View balance → Back
  ├── Deposit → Enter amount → Confirm → Back
  ├── Withdraw → Enter amount → Confirm → Back
  ├── Transaction History → View last 10 → Back
  └── Logout → Confirmation → Login Screen
8. Data Storage Format
Account data is stored in accounts.json. When the app runs for the first time, this file is created automatically with two default accounts.
The format looks like this:
json
{
    "1234": {
        "pin": "1111",
        "name": "Rahul Sharma",
        "balance": 15000.00,
        "transactions": [
            {
                "type": "Credit",
                "amount": 2000.0,
                "date": "03-06-2025 10:45",
                "balance_after": 17000.0
            }
        ]
    }
}
Each transaction stores the type (Credit/Debit), amount, date-time, and balance after the transaction.
9. Input Validation
The application handles these error cases:

Invalid card number or wrong PIN at login
Non-numeric or empty amount in deposit/withdrawal fields
Deposit amount greater than ₹1,00,000
Withdrawal amount not a multiple of ₹100
Withdrawal amount greater than ₹25,000

10. Limitations and Future Scope
Current limitations:

PIN change feature not included
No account creation from the UI (must be added manually to JSON)
No network/server connectivity — purely local
Only one user can be logged in at a time (single-session)

Future improvements that could be added:

Change PIN functionality
Transfer money between accounts
Admin panel for adding new accounts
Receipt printing or saving to a text file
Password encryption instead of plain-text PIN storage
SQLite database instead of JSON for better scalability
11.Conclusion
This project helped in understanding how GUI-based applications work in Python using Tkinter. 
It also gave hands-on experience with file I/O using JSON, form validation, and structuring a multi-screen desktop application. 
The project simulates a real-world system in a simplified form and covers many fundamental programming concepts taught during the course.

