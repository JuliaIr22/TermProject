# Personal Budget & Expense Tracker

## Video Demo


## Description
The Personal Budget & Expense Tracker is a console-based Python application designed to help users manage their personal finances in a simple and organized way. The program allows users to track income, record expenses by category, view a financial summary, and save their data for future use. This project was created as a final course project to demonstrate core Python programming concepts, including functions, error handling, file input/output, and control structures.

The program begins by loading previously saved budget data from a file. If no file exists, the program creates a new budget with zero income and no expenses. Users interact with the application through a menu-driven interface, where they can choose options such as adding income, recording an expense, viewing a summary, or saving and exiting the program.

One of the main goals of this project is usability. The menu options are clearly labeled, and user input is validated to prevent program crashes. For example, when the user enters a numeric value, the program ensures that the input is a valid positive number. This improves the reliability of the program and provides a better user experience.

## How the Program Works
The user begins by selecting options from a menu displayed in the console. When adding income, the user enters an amount that is added to the total income stored in the program. When adding an expense, the user enters both a category and an amount, which is saved in a list of expense records. The program calculates total expenses by summing all recorded expense amounts and then displays the remaining balance.

Data persistence is handled using a JSON file. When the user chooses to save and exit, the program writes the current budget data to a file. This allows the program to restore the data the next time it is run, making it more functional than a temporary, session-only program.

## Files in This Project
- **TermProject.py**: The main Python file that contains all program logic, including functions, error handling, and the menu system.
- **requirements.txt**: Lists the libraries required to run the project. This project uses the built-in `json` module.
- **README.md**: Provides documentation explaining the project, how it works, and design decisions.

## Key Design Decisions
One major design decision was using functions to separate different responsibilities in the program. Each function performs a single task, such as adding income or saving data. This improves readability and makes the code easier to maintain and expand.

Another important decision was implementing error handling using `try` and `except` blocks. This ensures that invalid user input does not cause the program to crash. Instead, the user is prompted to enter valid data.

Using a JSON file for data storage was also intentional. JSON is lightweight, human-readable, and well-supported in Python. This choice makes the program efficient while keeping the code simple and understandable.

## Future Improvements
Possible improvements include adding monthly reports, visual charts, multiple users, or a graphical user interface. These enhancements would make the program more powerful and user-friendly.

Overall, this project demonstrates the practical application of Python programming concepts learned throughout the course and provides a useful real-world tool for personal finance management.
