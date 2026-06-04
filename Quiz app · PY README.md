 1. Project Overview
 
This is a multiple-choice quiz application built using Python and the Tkinter GUI library. The app was
developed as part of an internship project to demonstrate understanding of GUI programming, basic Python
logic, and file handling. The application presents 10 questions one at a time, checks answers
immediately after submission, tracks the user's score, and saves the final result to a text file.

  2. Features
 
- Name input screen before the quiz begins
- 10 multiple-choice questions (4 options each)
- Answer validation with instant feedback (green = correct, red = wrong)
- Live score counter visible throughout the quiz
- Final result screen showing score, percentage, and grade
- Results are automatically saved to a file called quiz_results.txt
- View History button to see all past attempts
- Play Again option without closing the application
  
 3. Technologies Used
 
| Technology | Purpose |
|------------|---------|
| Python 3.x | Core programming language |
| Tkinter | GUI (comes built-in with Python) |
| datetime module | To timestamp saved results |
| os module | To check if the results file exists |
| File Handling (open/write/read) | Saving and viewing quiz results |
 
No third-party libraries or pip installs are required.

4. How to Run the Application
 
Step 1 - Make sure Python 3 is installed on your computer.
         You can check by typing in terminal/cmd: python --version
 
Step 2 - Save the file quiz_app.py anywhere on your computer.
 
Step 3 - Open terminal or command prompt and navigate to that folder:
         cd path/to/your/folder
 
Step 4 - Run the application:
         python quiz_app.py
 
Step 5 - The app window will open automatically.
 
Note: Tkinter is included with standard Python on Windows and macOS.
      On Ubuntu/Linux you may need to run: sudo apt-get install python3-tk
5. Application Flow
 
                +------------------+
                |   Welcome Screen  |
                |  (Enter Name)     |
                +--------+---------+
                         |
                   Click "Start Quiz"
                         |
                +--------v---------+
                |  Question Screen  |
                |  (Q1 to Q10)      |
                |  Submit -> Next   |
                +--------+---------+
                         |
                  After Q10 answered
                         |
                +--------v---------+
                |   Result Screen   |
                |  Score/% /Grade   |
                |  Saved to file    |
                +-------------------+
  6. Code Structure Explanation
 Global Variables
- questions     : A list of 10 dictionaries, each holding the question text, 4 options, and correct answer index
- current_q     : Integer to track which question is currently displayed (starts at 0)
- score         : Integer to count how many correct answers the user has given
- user_name     : Stores the name entered on the welcome screen
- answered      : Boolean flag to prevent the user from submitting the same question twice
 
 Frames (Screens)
- name_frame    : The welcome screen where the user types their name
- quiz_frame    : The main quiz screen with question, options, submit and next buttons
- result_frame  : The final screen showing the score and grade

   Key Functions
 
start_quiz()
  - Reads the name from the entry field
  - Validates that it is not empty
  - Resets score and question counter
  - Switches to the quiz screen and loads Q1
 
load_question()
  - Resets radio buttons and feedback text
  - Displays the current question and its 4 options
  - Disables the Next button until the user submits
 
check_answer()
  - Gets the selected radio button value
  - Compares it to the correct answer index
  - Highlights correct option in green and wrong in red
  - Updates score and enables the Next button
 
next_question()
  - Increments current_q
  - Calls load_question() if more questions remain
  - Calls show_result() after the last question
 
get_grade(percent)
  - Takes the percentage as input
  - Returns a grade string based on standard grading:
    90 and above  -> A+
    75 to 89      -> A
    60 to 74      -> B
    45 to 59      -> C
    33 to 44      -> D
    Below 33      -> F
 
save_result(name, score, total, percent, grade)
  - Opens quiz_results.txt in append mode
  - Writes a single line with timestamp, name, score, percentage, and grade
  - Creates the file automatically if it doesn't exist
 
show_result()
  - Clears and rebuilds the result frame dynamically
  - Calls save_result() to store the result
  - Displays Play Again, View History, and Exit buttons
 
view_history() (defined inside show_result)
  - Opens quiz_results.txt and reads all lines
  - Shows them in a scrollable popup window using a Text widget
 8. Grading System
 
| Percentage     | Grade |
|----------------|-------|
| 90% and above  |  A+   |
| 75% - 89%      |  A    |
| 60% - 74%      |  B    |
| 45% - 59%      |  C    |
| 33% - 44%      |  D    |
| Below 33%      |  F    |

 9. Possible Errors and Fixes
 
Problem: App doesn't open / tkinter not found
Fix    : Install tkinter using -> sudo apt-get install python3-tk (Linux only)
 
Problem: quiz_results.txt not found when clicking View History
Fix    : This means no quiz has been completed yet. Complete at least one quiz first.
 
Problem: Name field shows error even after typing
Fix    : Make sure you are not entering only spaces. The name is stripped of whitespace.
 
Problem: Next button is clickable but I haven't answered yet
Fix    : The code shows a warning popup in this case. You must submit before moving forward.

 10. Scope for Future Improvement
 
- Add a timer per question (countdown from 30 seconds)
- Add more categories like Science, History, Sports
- Allow the user to select number of questions
- Store results in a CSV or SQLite database instead of plain text
- Add a leaderboard screen sorted by score
- Add sound effects for correct/wrong answers

  11. Project Information
 
Developer  : Internship Student Project
Language   : Python 3
GUI        : Tkinter (Standard Library)
File I/O   : Plain text file (quiz_results.txt)
Lines      : ~160 lines approximately
Tested On  : Windows 10, Python 3.10

 
