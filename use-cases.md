# List of actors/users of the app

- Non-registered user.
- Registered and non-logged user.
- Registered and logged user.
- "The System": a code entity representing all that is evil.

# General list of requirements

- A non-registered user should be able to sign up.
- A registered user should be able to login.
- A registered user should be able to logout.
- A non-registered user should be able to reset his/her forgotten password.
- A registered and logged user should be able to create/read/update/delete a task at any time.
- A registered and logged user should be able to mark a task as completed/done (not active).
- A registered and logged user should be able to mark a completed task as incomplete (active).
- A registered and logged user should be able to update his/her own account.
- A registered and logged user should be able to delete his/her own account.
- A user should be able to change the app's language.
- A user will have the following properties:
    - Login
    - Email
    - Password
- A task will have the following properties:
    - Title
    - Active (information defined by the system, default: true)
    - [Optional] Description (default: '')
    - [Optional] Due date: datetime (default: null)

# Use cases

- **Sign up**
    - **Brief Description**: the user wants to sign up to the system.
    - **Actors**: Non-registered user
    - **Basic Flow**:
        1. The user indicates he wants to sign up to the system.
        2. The system presents a form asking for information about the user.
        3. The user inputs the information.
        4. The user submits the information.
        5. The system sends a validation email to the user.
        6. The system informs the user that it sent him/her a confirmation email WITH AN EXPIRATION DATE.
        7. The user validates the email by clicking on the link he/she received on his/her email.
        8. The system validates the user's email.
        9. The system creates a new user.
        10. The system indicates to the user that the signing up was successful.
        11. The system redirects the user to his list (still empty) of tasks.
    - **Exception Flows**:
        - 4.1. One or more of the informations sent by the user is invalid.
        - 4.2. The system indicates to the user why it couldn't create his/her account, and asks for new information.
        - 4.3. Go back to step 3.
        - 7.1. The user confirms the deletion by clicking on the email PAST THE EXPIRATION DATE.
        - 7.2. The system indicates that the confirmation is no longer valid.
    - **Post Conditions**: the user was successfully signed up to the system.

- **Login**
    - **Brief Description**: the user wants to login into the system.
    - **Actors**: Registered and non-logged user.
    - **Basic Flow**: .
        1. The user indicates he wants to login into the system.
        2. Tye system presents a form asking for information about the user to be logged.
        3. The user inputs the information.
        4. The user submits the information.
        5. The system validates the information.
        6. The system allows the user to login.
        7. The system indicates to the user that he/she was logged in.
        8. The system redirects the user to his/her list of tasks.
    - **Exception Flows**: .
        - 5.1. One or more of the informations sent by the user is invalid.
        - 5.2. The system indicates to the user why it couldn't login him/her, and asks for new information.
        - 5.3. Go back to step 3.
    - **Post Conditions**: the user is logged in.

- **Logout**
    - **Brief Description**: the user wants to logout of the system.
    - **Actors**: Registered and logged user.
    - **Basic Flow**: .
        1. The user indicates he/she wants to logout of the system.
        2. The system logs out the user.
    - **Post Conditions**: the user is logged out.

- **Reset password**
    - **Brief Description**: the user wants to reset his/her password.
    - **Actors**: Non-registered user.
    - **Basic Flow**:
        1. The user indicates that he/she forgot his/her password.
        2. The system asks the user for his/her email.
        3. The user inputs his/her email.
        4. The system sends the user an email for him/her to reset his/her password WITH AN EXPIRATION DATE.
        5. The system informs the user that he/she received an email.
        6. The user clicks on the email.
        7. The system presents the user with a form to input his/her new password.
        8. The user inputs his/her new password.
        9. The system validates the information.
        10. The system redirects the user to the home page.
    - **Alternate Flows**:
    - **Exception Flows**:
        - 3.1. The email the user informed doesn't exist in the system.
        - 3.2. The system informs the user that he/she received the email.
        - 6.1. The user tries to reset his/her password by clicking on the email PAST THE EXPIRATION DATE.
        - 6.2. The system indicates that the email is no longer valid.
    - **Post Conditions**: the user reseted his/her password and is logged in.

- **Create task**
    - **Brief Description**: the user wants to create a new TODO task.
    - **Actors**: Registered and logged user.
    - **Preconditions**: .
    - **Basic Flow**:
        1. The user indicates that he/she wants to create a new task.
        2. The system presents a form asking the user for information about the task.
        3. The user inputs the information.
        4. The user submits the information.
        5. The system creates the task.
        6. The system indicates to the user that the task has been created.
    - **Post Conditions**: the task has been created.

- **Read task**
    - **Brief Description**: the user wants to read/look at one of his tasks.
    - **Actors**: Registered and logged user.
    - **Preconditions**: the user has at least one previously created task.
    - **Basic Flow**:
        1. The user sees a list of all the tasks he has created before.
        2. The user indicates he wants to read one specific task in detail.
        3. The system shows the user the task in detail.
    - **Post Conditions**: the user has seen a task in detail.

- **Update task**
    - **Brief Description**: the user wants to update one of his tasks.
    - **Actors**: Registered and logged user.
    - **Preconditions**: the user has at least one task.
    - **Basic Flow**:
        1. The user **reads a task**.
        2. The user indicates he wants to update the current task.
        3. The system makes the current task editable.
        4. The user changes whatever information he wants (respecting the mandatory fields).
        5. The user submits the new information about the task.
        6. The system updates the task.
        7. The system indicates to the user that the task has been updated.
    - **Alternate Flows**:
        - 6.1. If the task being updated is non-active (completed), the system toggles the task to active and then updates it.
    - **Post Conditions**: the user has updated a task.

- **Delete task**
    - **Brief Description**: the user wants to delete one of his tasks.
    - **Actors**: Registered and logged user.
    - **Preconditions**: the user has at least one task.
    - **Basic Flow**:
        1. The user **reads a task**.
        2. The user indicates he wants to delete the current task.
        3. The system asks the user for confirmation.
        4. The user confirms he wants to delete the task.
        5. The system deletes the task.
        6. The system indicates to the user that the task has been properly deleted.
    - **Post Conditions**: the user has deleted a task.

- **Mark task as completed**
    - **Brief Description**: the user wants to mark one of his tasks as completed.
    - **Actors**: Registered and logged user.
    - **Preconditions**: the user has at least one task.
    - **Basic Flow**:
        1. The user **reads a task** OR sees a list of his tasks.
        2. The user indicates he wants to complete the current task or one in the list.
        5. The system marks the task as completed.
        6. The system indicates to the user that the task has been marked as completed.
    - **Post Conditions**: the user has completed a task.

- **Mark task as incomplete**
    - **Brief Description**: the user wants to mark one of his completed tasks as incomplete.
    - **Actors**: Registered and logged user.
    - **Preconditions**: the user has at least one completed task.
    - **Basic Flow**:
        1. The user sees a list of his tasks.
        2. The user indicates he wants to mark a complete task from the list as incomplete.
        5. The system marks the task as incomplete.
        6. The system indicates to the user that the task has been marked as incomplete.
    - **Post Conditions**: the user has marked a completed task as incomplete.

- **Update account**
    - **Brief Description**: the user wants to update his/her own account.
    - **Actors**: Registered and logged user.
    - **Preconditions**:
    - **Basic Flow**:
        1. The user indicates he/she wants to update his/her own account
        2. The system makes his/her account editable.
        4. The user changes whatever information he wants (respecting the mandatory fields).
        5. The user submits the new information.
        6. The system updates his/her account.
        7. The system indicates to the user that his/her account has been updated.
    - **Post Conditions**: the user's account has been updated.

- **Delete account**
    - **Brief Description**: the user wants to delete his/her own account.
    - **Actors**: Registered and logged user.
    - **Basic Flow**:
        1. The user indicates he/she wants to delete his/her own account.
        2. The system sends a confirmation email to the user.
        3. The system informs the user that it sent him/her a confirmation email WITH AN EXPIRATION DATE.
        4. The user confirms the deletion by clicking on the email.
        5. The system deletes the user's account.
        6. The system logs out the user.
        7. The system indicates to the user that it has deleted his/her account.
    - **Exception Flows**:
        - 4.1. The user confirms the deletion by clicking on the email PAST THE EXPIRATION DATE.
        - 4.2. The system indicates that the confirmation is no longer valid.
    - **Post Conditions**: the user delete his/her own account.

- **Change app's language**
    - **Brief Description**: the user wants to change the app's language.
    - **Actors**: every user.
    - **Basic Flow**:
        1. The user indicates he/she wants to change the app's language.
        2. The system presents the user with a list of the available languages.
        3. The user selects one of the languages.
        4. The system translates the app into the chosen language.
        5. The system redirects the user to the same page he/she was already in.
    - **Post Conditions**: the app is translated to the new language.