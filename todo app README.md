1. Introduction
This project is a simple To-Do List desktop application built using Python and the Tkinter library. The main purpose of this project is to help users manage their daily tasks through a graphical user interface. The application allows users to add, update, delete, and mark tasks as completed. All tasks are saved in a CSV file so that data is not lost when the program is closed.
This project was made as part of an internship to practice Python programming and basic GUI development skills.
2. Objectives
•	Build a working desktop application using Python and Tkinter
•	Allow users to add new tasks through a text input
•	Let users mark tasks as done or undo them
•	Provide options to update and delete existing tasks
•	Store task data in a CSV file for persistence between sessions
•	Keep the code simple and beginner-friendly
3. Tools and Technologies Used

Technology	Purpose
Python 3	Main programming language
Tkinter	GUI library (built into Python)
CSV module	Saving and loading tasks from file
OS module	Checking if the data file exists
Any text editor / IDLE	Writing the code

4. Project Structure
The project consists of two files:
•	todo_app.py  —  the main Python source code file
•	tasks.csv  —  the data file created automatically when tasks are added
No external libraries need to be installed. Everything used is part of Python's standard library.
5. Features
5.1 Add Task
The user types a task in the input box and clicks the Add button. If the input is empty, a warning message is shown. Otherwise, the task is added to the list and saved to the CSV file.
5.2 Mark Task as Done / Undo
The user selects a task from the list and clicks Mark Done / Undo. If the task is not done, it will be marked as done and shown in gray text with a [Done] label. Clicking again will undo it back to the normal state.
5.3 Update Task
The user clicks on a task in the list. The task text automatically loads into the input box. The user edits the text and clicks Update Task to save the changes.
5.4 Delete Task
The user selects a task and clicks Delete Task. A confirmation dialog box appears before the task is permanently removed.
5.5 Data Storage
All tasks are saved in a file called tasks.csv in the same folder as the program. Each row in the file stores the task text and whether it is done (yes or no). The data is loaded automatically every time the program starts.
6. How the Code Works
The code is organized into simple functions. Here is a brief description of each:

Function	What it does
load_tasks()	Reads tasks from tasks.csv and returns them as a list
save_tasks(tasks)	Writes the current task list back to tasks.csv
refresh_list()	Clears and redraws the listbox with updated task data
add_task()	Reads input, appends a new task, saves and refreshes
delete_task()	Removes the selected task after user confirmation
mark_done()	Toggles the done status of the selected task
update_task()	Replaces the selected task text with the input box content
on_select(event)	Loads the clicked task's text into the input box

7. How to Run the Project
1.	Make sure Python 3 is installed on your computer.
2.	Save the file todo_app.py on your computer.
3.	Open a terminal or command prompt in the same folder.
4.	Run the following command:
    python todo_app.py
5.	The application window will open. No installation of extra packages is needed.
8. CSV File Format
The data is stored in a file named tasks.csv. Each line contains two values separated by a comma:
task text,yes
another task,no
The second column is either yes (task completed) or no (task not completed). This file is created automatically and does not need to be created manually.
9. Limitations
•	There is no login system or user accounts
•	Tasks cannot be sorted or filtered by category
•	The application does not have due dates or reminders
•	Only works on desktop; no mobile version
•	All users share the same CSV file on the same computer
10. Possible Improvements
•	Add a due date field for each task
•	Allow tasks to be sorted by status or alphabetically
•	Use a database like SQLite instead of a CSV file
•	Add task categories or priority levels
•	Add a search box to filter tasks
11. Conclusion
This project helped in learning how to build a basic GUI application using Python. It covers important topics like reading and writing files, using functions, handling events in Tkinter, and managing a simple data structure. The project is small in scope but covers all the basic CRUD operations: Create, Read, Update, and Delete.
It was a good learning experience and helped in understanding how a real application manages data and interacts with the user.
