# Question

Write a Java console application named `Question3` that functions as a workout tracker for users. The program should perform the following tasks:

## 1. User Authentication:
- Prompt the user to enter their username.
- Convert the username to lowercase and create a filename in the format `"users/username_workouts.txt"`.
- Welcome the user by displaying a personalized greeting.

## 2. Main Menu:
- Display a menu with the following options:
  1. **Add Workout**
  2. **View Workouts**
  3. **Exit**
- Prompt the user to enter their choice.

## 3. Add Workout Option:
- If the user selects **Add Workout**:
  - Prompt the user to enter the name of the exercise.
  - Prompt the user to enter the number of minutes spent on the exercise.
  - Append the exercise and duration to the user's workout file in the format: `exercise duration`.
  - Confirm to the user that the workout has been saved.

## 4. View Workouts Option:
- If the user selects **View Workouts**:
  - Open the user's workout file.
  - Read and display each exercise and its corresponding duration in the format: `exercise: duration minutes`.
  - Handle the scenario where the user has no workout history gracefully.

## 5. Exit Option and Summary:
- If the user selects **Exit**:
  - Read the user's workout file and compute the following statistics:
    - **Total workouts completed**: Count the number of exercise entries.
    - **Total time across all exercises**: Sum the durations of all exercises.
    - **Highest time in one workout**: Identify the exercise with the maximum duration and its duration.
    - **Average time per workout**: Calculate the average duration per exercise.
  - Display the workout summary to the user with appropriate labels.
  - Encourage the user with a personalized message.

## 6. Program Requirements:
- Use appropriate variables and data types to store user input and computation results.
- Utilize file handling to read from and write to the user's workout file.
- Implement input validation where necessary (e.g., ensuring numerical inputs for durations).
- Include comments in your code explaining the purpose of code blocks and important variables.
- Ensure the program handles exceptions, such as file not found errors, to prevent crashes.
- Close all open resources like scanners and files properly.

## 7. Sample Interaction:

=== Workout Tracker === Enter username: JohnDoe

Welcome JohnDoe!

=== JohnDoe's Workout Tracker ===

Add Workout
View Workouts
Exit
Choice: 1 Enter exercise: Running Enter number of minutes: 30 Workout saved to your log!

=== JohnDoe's Workout Tracker ===

Add Workout
View Workouts
Exit
Choice: 2

Your Workout History: Running: 30 minutes

=== JohnDoe's Workout Tracker ===

Add Workout
View Workouts
Exit
Choice: 3

=== JohnDoe's Workout Summary === Total workouts completed: 1 Total time across all exercises: 30 minutes Highest time in one workout: 30 minutes - (Running) Average time per workout: 30.00 minutes

Keep up the good work, JohnDoe!

yaml
Copy code

---

## Instructions:
- Write the complete Java program fulfilling all the requirements mentioned above.
- Ensure your code is well-organized and follows best programming practices.
- Test your program thoroughly to handle different user inputs and scenarios.
- Submit the `.java` file containing your source code.
