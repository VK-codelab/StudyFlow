#***studyFlow*** - Project Plan

**##1. Project Overview**

*###WHAT IS STUDY FLOW?*

StudyFlow is a web application that brings study planning, task management, notes, focus sessions, and progress tracking into one place for students.


## 2. Problem Statement

*###WHAT PROBLEM ARE WE TRYING TO SOLVE?*

Students often manage different parts of their academic life separately. Tasks, study schedules, notes, and progress can become scattered across different apps or notebooks, making it harder to see their overall workload and progress.


**##3. Project Goals**

*###WHAT DO WE WANT TO ACCOMPLISH?*

- Build one organized workspace for academic activities.
- Allow students to track tasks, study sessions, notes, and progress.
- Create a clean and easy-to-use interface.
- Build the application as a complete full-stack project.
- Deploy a working version that can be used and tested.


## 4. Target Users

StudyFlow is mainly designed for students who want a simple way to organize their academic work and keep track of their study habits.

The main users will be school, college, and university students. The first version will focus on individual students rather than teachers, parents, or educational institutions.


## 5. User Requirements

A user should be able to:

- Create, edit, complete, and delete tasks.
- Organize tasks based on subjects.
- Create, edit, and delete notes.
- Create and manage subjects.
- Start and record study sessions using a focus timer.
- View their study time and academic progress.
- See important tasks, progress, and study information from the dashboard.
- View and manage their personal study data in one place.


  ## 6. Features

### 6.1 Dashboard

The dashboard will give the user a quick overview of their academic activity.

- Show today's tasks.
- Show pending and completed tasks.
- Show total study time.
- Show subject progress.
- Show current study streak.
- Display useful study insights.
- Provide quick access to the main features.

### 6.2 Task Management

Users will be able to manage their academic tasks.

- Create a task.
- Add a task title and description.
- Set a due date.
- Set a priority.
- Assign a task to a subject.
- Mark a task as completed.
- Edit a task.
- Delete a task.
- Filter tasks based on their status or priority.

### 6.3 Subject Management

Users will be able to organize their academic work by subject.

- Create a subject.
- Edit a subject.
- Delete a subject.
- Set a progress level for a subject.
- View tasks related to a subject.
- View study sessions related to a subject.

### 6.4 Focus Sessions

Users will be able to use a built-in timer to focus on their studies.

- Start a focus session.
- Pause and resume the timer.
- Reset the timer.
- Select a subject for the session.
- Choose a study duration.
- Record completed study sessions.
- Track the total time spent studying.

### 6.5 Notes

Users will be able to create and organize their study notes.

- Create a note.
- Add a title and content.
- Assign a note to a subject.
- Edit a note.
- Delete a note.
- Search notes.

### 6.6 Progress Tracking

Users will be able to see how their study habits change over time.

- Track total study time.
- Track completed tasks.
- View subject-wise progress.
- View weekly study activity.
- Track study streaks.
- Display progress using charts and statistics.

### 6.7 Study Insights

StudyFlow will analyze the user's existing activity and provide simple insights about their study habits.

Examples include:

- Most studied subject.
- Total study time for the week.
- Number of completed tasks.
- Comparison between current and previous study activity.

The first version will use normal application logic to generate these insights. AI-based insights may be considered for a future version.


## 7. MVP Scope

The first version of StudyFlow will focus on the core features needed to make the application useful as a student productivity tool.

### Features included in Version 1

- Dashboard
- Task management
- Subject management
- Focus sessions with a study timer
- Study session tracking
- Notes
- Basic progress tracking
- Basic study insights
- Responsive design for desktop and mobile screens

### Features not included in Version 1

The following features will be considered for future versions:

- User registration and login
- Cloud synchronization
- AI study assistant
- AI-generated study plans
- Calendar integration
- Notifications and reminders
- Advanced analytics
- Mobile application
- Social or collaborative features

The MVP will be completed and tested before any of the future features are added.


## 8. Technology Stack

StudyFlow will be developed as a full-stack web application. The technologies will be chosen to keep the project simple enough to learn from while still following a real-world application structure.

### Frontend

- HTML — Used to create the structure of the web pages.
- CSS — Used for styling, layouts, responsiveness, and animations.
- JavaScript — Used to add interactivity and communicate with the backend.

### Backend

- Python — Used for the server-side application logic.
- Flask — A lightweight Python web framework that will be used to build the backend and API.

### Database

- SQLite — Used to store tasks, subjects, notes, study sessions, and other application data.

### Data Visualization

- Chart.js — Used to display study statistics and progress through charts.

### Development Tools

- Visual Studio Code — Main code editor.
- Git — Used to track changes throughout development.
- GitHub — Used to store the source code and document the project.

### Deployment

The application will be deployed online after development and testing are completed. The deployment platform will be selected during the deployment phase.


## 9. System Architecture

StudyFlow will use a simple client-server architecture where the frontend, backend, and database work together.

### Main Components

**Frontend**

The frontend is the part of StudyFlow that the user interacts with. It will be built using HTML, CSS, and JavaScript.

It will handle:

- Displaying pages and information.
- Accepting user input.
- Updating the interface.
- Sending requests to the backend.
- Displaying data received from the backend.

**Backend**

The backend will be built using Python and Flask. It will handle the application's main logic and act as the connection between the frontend and database.

It will handle:

- Processing requests from the frontend.
- Validating user input.
- Performing application logic.
- Reading and updating database data.
- Sending responses back to the frontend.

**Database**

SQLite will store the application's data.

The database will contain information such as:

- Subjects
- Tasks
- Notes
- Study sessions
- Progress-related data

### Communication Flow

The basic flow of the application will be:

User → Frontend → API → Flask Backend → Database

The response will then travel back through the same layers:

Database → Flask Backend → API → Frontend → User

### Simplified Architecture

    User
      ↓
    Frontend
    HTML / CSS / JavaScript
      ↓
    API Requests
      ↓
    Flask Backend
    Python
      ↓
    SQLite Database

The frontend will not directly access the database. All database operations will be handled by the backend.


## 10. Database Design

StudyFlow will use SQLite as its database. The database will store the information needed to manage tasks, subjects, notes, and study sessions.

### Main Tables

#### Subjects

Stores information about the subjects created by the user.

Possible fields:

- id
- name
- description
- progress
- created_at

#### Tasks

Stores academic tasks created by the user.

Possible fields:

- id
- title
- description
- subject_id
- priority
- due_date
- completed
- created_at

#### Notes

Stores notes created by the user.

Possible fields:

- id
- title
- content
- subject_id
- created_at
- updated_at

#### Study Sessions

Stores information about completed study sessions.

Possible fields:

- id
- subject_id
- duration
- session_date
- created_at

### Relationships

The tables will be connected where necessary.

- One subject can have many tasks.
- One subject can have many notes.
- One subject can have many study sessions.
- Each task, note, and study session can be associated with a subject.

The exact database structure and relationships will be finalized before implementation.


## 11. API Design

StudyFlow will use a REST-style API to allow the frontend and backend to communicate.

The frontend will send HTTP requests to the Flask backend, and the backend will process those requests and return the required data.

### HTTP Methods

The main HTTP methods used will be:

- GET — Retrieve data.
- POST — Create new data.
- PUT — Update existing data.
- DELETE — Remove data.

### Task Endpoints

- GET `/api/tasks` — Get all tasks.
- GET `/api/tasks/<id>` — Get a specific task.
- POST `/api/tasks` — Create a new task.
- PUT `/api/tasks/<id>` — Update a task.
- DELETE `/api/tasks/<id>` — Delete a task.

### Subject Endpoints

- GET `/api/subjects` — Get all subjects.
- GET `/api/subjects/<id>` — Get a specific subject.
- POST `/api/subjects` — Create a new subject.
- PUT `/api/subjects/<id>` — Update a subject.
- DELETE `/api/subjects/<id>` — Delete a subject.

### Note Endpoints

- GET `/api/notes` — Get all notes.
- GET `/api/notes/<id>` — Get a specific note.
- POST `/api/notes` — Create a new note.
- PUT `/api/notes/<id>` — Update a note.
- DELETE `/api/notes/<id>` — Delete a note.

### Study Session Endpoints

- GET `/api/study-sessions` — Get recorded study sessions.
- POST `/api/study-sessions` — Record a completed study session.
- DELETE `/api/study-sessions/<id>` — Delete a study session.

### API Response Format

The backend will return data in JSON format so that the JavaScript frontend can easily process and display it.

Example:

{
  "id": 1,
  "title": "Complete DBMS assignment",
  "priority": "high",
  "completed": false
}

The API structure may be adjusted during development if a better approach is found.


## 12. Development Phases

StudyFlow will be developed in several phases so that each part of the application can be built, tested, and understood before moving to the next stage.

### Phase 1 — Planning and Requirements

- Define the purpose of StudyFlow.
- Identify the target users.
- Define user requirements.
- Decide the core features.
- Define the MVP scope.
- Plan the technology stack.
- Plan the system architecture.

### Phase 2 — UI/UX Design

- Plan the layout of each page.
- Create basic wireframes.
- Decide the navigation structure.
- Choose typography, spacing, colors, and other visual elements.
- Plan responsive layouts for different screen sizes.

### Phase 3 — Frontend Development

- Create the basic HTML structure.
- Build the navigation and page layouts.
- Style the application using CSS.
- Add responsive design.
- Add interactive functionality using JavaScript.
- Build the dashboard, task, subject, focus, notes, and progress pages.

### Phase 4 — Database Development

- Set up SQLite.
- Create the required database tables.
- Define relationships between tables.
- Test database operations.
- Connect the database to the backend.

### Phase 5 — Backend Development

- Set up the Flask application.
- Create backend routes.
- Implement application logic.
- Add input validation.
- Connect Flask to the SQLite database.
- Handle errors and API responses.

### Phase 6 — API Development and Integration

- Implement the planned API endpoints.
- Connect the frontend to the backend using JavaScript.
- Send and receive JSON data.
- Connect tasks, subjects, notes, and study sessions to the database.
- Make sure changes made in the frontend are saved correctly.

### Phase 7 — Feature Development

- Complete task management.
- Complete subject management.
- Implement the focus timer.
- Implement study session tracking.
- Complete the notes system.
- Implement progress tracking.
- Add study insights.

### Phase 8 — Testing and Debugging

- Test individual features.
- Test API endpoints.
- Test database operations.
- Test different user inputs and edge cases.
- Fix bugs and errors.
- Test the application on different screen sizes and browsers.

### Phase 9 — Deployment

- Prepare the application for production.
- Configure the deployment environment.
- Deploy the application.
- Test the deployed version.
- Fix any issues that occur after deployment.

### Phase 10 — Documentation and Portfolio

- Complete the GitHub README.
- Add screenshots of the application.
- Document the technologies used.
- Explain the project structure and architecture.
- Add the live project link.
- Add the project to the personal portfolio.


## 13. Testing Strategy

Testing will be done throughout development instead of waiting until the end of the project.

### Functional Testing

Each feature will be tested to make sure it behaves as expected.

Examples:

- Creating a task should save it correctly.
- Editing a task should update the existing information.
- Completing a task should change its status.
- Deleting a task should remove it.
- Creating a subject should make it available when assigning tasks and notes.
- Completed study sessions should be recorded correctly.
- Notes should be saved and displayed correctly.

### Input and Validation Testing

The application will be tested with different types of input, including:

- Empty fields.
- Invalid values.
- Very long text.
- Missing information.
- Incorrect dates or durations.

The application should handle invalid input without crashing.

### API Testing

Each API endpoint will be tested to make sure it:

- Accepts the correct request.
- Returns the expected response.
- Handles invalid requests properly.
- Returns appropriate error messages.

### Database Testing

Database operations will be tested to make sure data can be:

- Created.
- Retrieved.
- Updated.
- Deleted.

Relationships between subjects, tasks, notes, and study sessions will also be checked.

### Responsive Testing

The interface will be tested on:

- Mobile screens.
- Tablet screens.
- Laptop screens.
- Larger desktop screens.

### Browser Testing

The application will be tested on commonly used browsers, including Chrome and Edge.

### Bug Tracking

Bugs discovered during development will be documented, investigated, fixed, and tested again to make sure the issue has been resolved.


## 14. Deployment Plan

StudyFlow will be deployed after the main features have been developed and tested locally.

The deployment process will include:

- Prepare the application for production.
- Configure the Flask backend for deployment.
- Set up the required environment variables and configuration.
- Deploy the application using a suitable hosting platform.
- Test the live application after deployment.
- Fix any issues found in the deployed version.
- Add the live application link to the GitHub repository and portfolio.

The deployment platform will be selected based on the requirements of the final application and the free options available at the time of deployment.


## 15. Future Improvements

After the MVP is completed and stable, StudyFlow may be expanded with additional features.

Possible future improvements include:

- User registration and login.
- Cloud-based data storage and synchronization.
- AI-powered study insights.
- AI-generated study plans.
- Calendar integration.
- Notifications and reminders.
- More advanced progress analytics.
- Goal setting and tracking.
- Exporting study reports.
- Dark and light themes.
- Mobile application.
- Collaboration and study groups.

These features will only be considered after the core version of StudyFlow has been completed, tested, and deployed.
