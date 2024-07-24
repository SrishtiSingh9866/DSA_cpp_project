Software Requirements Specification (SRS) for Social Media App
1. Introduction
The User and Friendship Management System is a simple C++ program designed to manage user registrations and friendships between users. It allows users to be added to the system, establishes friendships between them, and displays information about users and their friendships.

2. Functional Requirements
2.1 User Management
Add User

Description: This function allows adding a new user to the system.
Input: User's username (unique identifier), first name, last name, age, and gender.
Process:
Check if the username is already taken.
If not taken, create a new user and add it to the system.
Provide feedback on the success or failure of the operation.
Output: Success or error message indicating the result of the operation.
Display All Users

Description: This function displays all registered users in the system.
Output: A list of all users, including their usernames and full names.
2.2 Friendship Management
Make Friends

Description: This function establishes a friendship between two users.
Input: Usernames of the two users who wish to become friends.
Process:
Add each user to the other's list of friends.
Provide feedback confirming the friendship.
Output: A confirmation message indicating that the two users are now friends.
Display All Friendships

Description: This function displays all existing friendships in the system.
Output: A list showing each user and their friends.
3. System Design
3.1 Data Structures
User
Attributes: firstName, lastName, age, gender
Global Data Structures:
map<string, User> mapUserName
Maps usernames to User objects.
map<string, set<string>> Friends
Maps each username to a set of friends' usernames.
3.2 Functions
addUser(string userName, User user)
Adds a user to mapUserName if the username is not already taken.
makeThemFriend(string userName1, string userName2)
Adds each user to the other's list in the Friends map.
displayAllUsers()
Prints all users with their usernames and full names.
displayAllFriendships()
Prints each user and their list of friends.
4. Usage
Adding Users

Users "Alice" and "Bob" are created and added to the system with their respective details.
Making Friends

A friendship is established between Alice and Bob.
Displaying Information

The system prints out all registered users and their friendships.
This system is designed for simplicity and demonstration purposes. It manages user registration and friendships effectively with basic functionalities and provides feedback for user actions.


Software Requirements Specification (SRS) for To-Do List Application
1. Introduction
The To-Do List Application is a console-based program designed to manage tasks. Users can add, view, mark as completed, delete, and search tasks. The application provides a user-friendly interface and interactive functionalities to manage personal tasks effectively.

2. Functional Requirements
2.1 Task Management
Add Task

Description: This function allows users to add a new task to the to-do list.
Input: Task description (string), due date (string in YYYY-MM-DD format), and priority level (integer from 1 to 5).
Process:
Collect the task details from the user.
Create a new Task object and add it to the list of tasks.
Output: Confirmation message indicating successful addition of the task.
View Tasks

Description: This function displays all tasks currently in the to-do list.
Output: A list of tasks showing the description, due date, priority, and completion status of each task.
Mark Task as Completed

Description: This function allows users to mark a specific task as completed.
Input: Task number (integer) to be marked as completed.
Process:
Validate the task number.
Update the task's completed status to true.
Output: Confirmation message indicating the task has been marked as completed.
Delete Task

Description: This function allows users to delete a specific task from the to-do list.
Input: Task number (integer) to be deleted.
Process:
Validate the task number.
Remove the task from the list.
Output: Confirmation message indicating the task has been deleted successfully.
Search Task

Description: This function allows users to search for tasks containing a specific keyword in their description.
Input: Keyword (string) to search for.
Process:
Search through the task descriptions for the keyword.
Output: List of tasks that contain the keyword in their description, including their due date, priority, and completion status. If no tasks are found, provide a message indicating that no tasks match the keyword.
2.2 User Interface
Display Welcome Page

Description: This function displays a welcome message when the application starts.
Output: Welcome message formatted with borders. Pauses for 2 seconds before proceeding.
Display Main Menu

Description: This function displays the main menu options for the user.
Output: Menu with options to add, view, mark as completed, delete, search tasks, or exit the application.
3. System Design
3.1 Data Structures
Task

Attributes: description (string), dueDate (string), priority (integer), completed (boolean)
Global Data Structure:

vector<Task> tasks
Stores a list of all tasks in the to-do list.
3.2 Functions
displayWelcomePage()
Displays a welcome page and pauses for 2 seconds.
displayMenu()
Displays the main menu options to the user.
addTask(vector<Task>& tasks)
Adds a new task to the tasks vector.
viewTasks(const vector<Task>& tasks)
Displays all tasks from the tasks vector.
markTaskCompleted(vector<Task>& tasks)
Marks a specific task as completed based on user input.
deleteTask(vector<Task>& tasks)
Deletes a specific task from the tasks vector based on user input.
searchTask(const vector<Task>& tasks)
Searches and displays tasks containing a specific keyword.
4. Usage
Starting the Application

The application starts by displaying a welcome page.
Navigating the Menu

Users can choose from the menu options to perform various tasks such as adding, viewing, marking as completed, deleting, or searching tasks.
Interacting with Tasks

Users can interact with tasks through the provided menu options to manage their to-do list effectively.
The application aims to provide a straightforward and interactive interface for managing personal tasks. It is designed to be easy to use, with clear prompts and functionality for effective task management.





### Software Requirements Specification (SRS) for Random Number Game

#### 1. Introduction
The Random Number Game is an interactive console-based application where players guess a randomly generated number within a specified range. The game includes different difficulty levels, a hint system, and a leaderboard to track high scores.

#### 2. Functional Requirements

##### 2.1 Game Menu
1. **Display Menu**
   - **Description:** Displays the main menu with options to play the game, view the leaderboard, or exit the application.
   - **Options:**
     - Play the game.
     - View the leaderboard.
     - Exit the application.

##### 2.2 Gameplay
1. **Play Game**
   - **Description:** Initiates a new game session where players guess a randomly generated number.
   - **Inputs:**
     - Player’s name.
     - Difficulty level (Easy, Medium, Hard).
     - Player’s guesses.
   - **Processes:**
     - The player selects a difficulty level that determines the number of guesses and hints available.
     - The system generates a random number between 1 and 100.
     - The player guesses the number, and feedback is provided based on proximity to the correct number.
     - Hints are provided based on the number's properties and hints already given.
   - **Outputs:**
     - Feedback on the player’s guess (too high, too low, or correct).
     - Hints about the number’s properties (even/odd, prime, divisible by certain numbers, perfect square).
     - Game results (win or loss) with appropriate messages.

2. **Provide Hints**
   - **Description:** Offers hints to the player about the randomly generated number.
   - **Inputs:**
     - The randomly generated number.
     - Player’s guess.
   - **Processes:**
     - Provides hints based on whether the number is even or odd, prime, divisible by other numbers, or a perfect square.
     - Keeps track of hints already given to avoid repetition.
   - **Outputs:**
     - Hint about the number's properties if requested and hints are still available.

##### 2.3 Leaderboards
1. **Update Leaderboard**
   - **Description:** Updates the leaderboard with the player’s score based on their performance.
   - **Inputs:**
     - Difficulty level (determines which leaderboard to update).
     - Player’s score (calculated from remaining guesses).
   - **Processes:**
     - Adds the player’s score to the appropriate difficulty leaderboard.
   - **Outputs:**
     - Updated leaderboard.

2. **View Leaderboard**
   - **Description:** Displays the leaderboard based on the selected difficulty level.
   - **Inputs:**
     - User choice for leaderboard difficulty (Easy, Medium, Hard).
   - **Processes:**
     - Displays scores and player names for the selected difficulty level.
   - **Outputs:**
     - Leaderboard listing scores and players, or a message indicating no players if the leaderboard is empty.

##### 2.4 User Interface
1. **Display Welcome Screen**
   - **Description:** Displays a welcome message and game introduction.
   - **Output:** Welcome message in a decorative box.

2. **Display Game Status**
   - **Description:** Shows the current game status, such as remaining guesses and hints.
   - **Outputs:** Messages and game status updates in a decorative box.

3. **Display Results**
   - **Description:** Shows results of the game session (win/lose) and any associated messages.
   - **Outputs:** Results and appropriate messages in a decorative box.

4. **Print Decorative Box**
   - **Description:** Prints a box with decorative borders for various messages.
   - **Outputs:** Aesthetic formatting for game messages and menus.

#### 3. System Design

##### 3.1 Data Structures
- **`map<int, string, std::greater<int>>`**
  - **Attributes:** Stores the leaderboard with scores (keys) and player names (values), sorted in descending order.

- **Global Variables:**
  - **`easyLeaderboard`** - Leaderboard for Easy difficulty.
  - **`mediumLeaderboard`** - Leaderboard for Medium difficulty.
  - **`hardLeaderboard`** - Leaderboard for Hard difficulty.

##### 3.2 Functions
1. **`displayMenu()`**
   - Displays the main menu and processes user input to navigate to different features.

2. **`playGame()`**
   - Handles the gameplay loop, including guessing, providing hints, and updating the leaderboard.

3. **`provideHint(int randomNumber, int guess, vector<string>& hintsGiven)`**
   - Provides hints based on the properties of the randomly generated number and user’s guesses.

4. **`isPrime(int num)`**
   - Checks if a number is prime.

5. **`updateLeaderboard(int difficulty, int score)`**
   - Updates the appropriate difficulty leaderboard with the player’s score.

6. **`viewLeaderboard()`**
   - Displays the leaderboard for a chosen difficulty level.

7. **`printLeaderboard(const string& difficulty, const map<int, string, std::greater<int>>& leaderboard)`**
   - Formats and displays the leaderboard.

8. **`printBoxTop()`**
   - Prints the top border of the decorative box.

9. **`printBoxBottom()`**
   - Prints the bottom border of the decorative box.

#### 4. Usage

1. **Starting the Application**
   - The application starts by displaying the welcome screen and main menu.

2. **Navigating the Menu**
   - Users choose between playing the game, viewing the leaderboard, or exiting.

3. **Playing the Game**
   - Players enter their name, choose a difficulty level, and guess the random number while receiving hints and feedback.

4. **Viewing the Leaderboard**
   - Users can view high scores for different difficulty levels.

The Random Number Game is designed to be engaging and interactive, providing a mix of gameplay and competitive elements through leaderboards. The use of hints and varying difficulty levels aims to enhance the player experience and challenge.
