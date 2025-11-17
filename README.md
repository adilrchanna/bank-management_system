# bank-management_system
This is a simple, console-based Bank Management System written in C++ to demonstrate the core principles of Object-Oriented Programming (OOP).
The system creates a base Account class and two specialized derived classes, SavingsAccount and CurrentAccount, each with its own unique business logic for withdrawals.



### OOP Concepts Demonstrated
This project was built as a learning exercise to implement the following OOP concepts from scratch:

#### Encapsulation:
All data members (like balance and accountNumber) are protected or private. They are only accessible through public member functions (getters/setters), which protects the data from invalid states.

#### Inheritance:
SavingsAccount : public Account
CurrentAccount : public Account
The derived classes inherit all common functionality from the base Account class, reducing code duplication.

#### Polymorphism:
The withdraw() function is declared as virtual in the base Account class.
It is then overriden in SavingsAccount (to enforce a minimum balance) and CurrentAccount (to allow an overdraft).
This allows the same function call (account_ptr->withdraw()) to have different behaviors depending on the object's real type.

#### Abstraction:
The main() function uses a std::vector<Account*> to store all objects.
This "master list" treats all objects as just "Accounts," hiding the complex implementation details of which type of account it is.

#### Memory Management:
A virtual destructor is included in the base class to ensure that delete calls the correct child destructor, preventing memory leaks.



### Features
Base Account: A simple account with deposit() and a basic withdraw().
Savings Account: A specialized account that overrides withdraw() to prevent the balance from dropping below 500 PKR.
Current Account: A specialized account that overrides withdraw() to allow the balance to go negative (overdraft) up to -5,000 PKR.
Polymorphic Management: The main() function demonstrates creating a list of accounts and processing them all in a single, abstract loop.



### How to Build and Run
This program is contained in a single file (main.cpp) and can be compiled with any modern C++ compiler.

#### 1. Clone the repository:
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name

#### 2. Compile the program:
We use -std=c++11 (or newer) to support 'override' and for-each loops
g++ -std=c++11 -o bank_system main.cpp

#### 3. Run the program:
./bank_system
