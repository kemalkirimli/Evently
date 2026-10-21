[evently_readme.md](https://github.com/user-attachments/files/33770087/evently_readme.md)
# Evently - University Event Discovery & Registration Platform

**Project Name:** Evently

## 1. Project Purpose and Context

University students often learn about campus events through scattered channels such as different social media accounts, student clubs, messaging groups, and various university websites. Because event information is distributed across multiple platforms, students frequently miss events that interest them, while organizers struggle with managing registrations and tracking participants.

**Evently** is a centralized, web-based university event discovery and registration platform. It aims to bring all university events together in one place, making event participation seamless for students and event management straightforward for organizers.

## 2. Main Features & User Roles

### For Students

* **Browse & Discover:** View all available university events in a clean, centralized listing.

* **Search & Filter:** Easily find events by category, date, or keyword.

* **Event Details:** Check comprehensive event descriptions, locations, dates, and real-time available capacity.

* **Registration Management:** Register for upcoming events or cancel existing registrations.

* **Student Dashboard:** View a personalized list of registered events.

### For Event Organizers

* **Event Management:** Create new events, edit existing event details, or cancel events.

* **Capacity & Details Control:** Set event dates, locations, detailed descriptions, and maximum participant capacity.

* **Organizer Dashboard:** View and track the list of registered participants for each event.

### Core System Capabilities

* **Role-Based Access Control:** Secure user registration and login with separate permissions for students and organizers.

* **Data Integrity & Validation:** Automated checks to prevent duplicate registrations by the same user and strictly block registrations from exceeding an event's maximum capacity.

### Out of Scope (Initial Version)

To keep the initial release focused and functional, the following features are explicitly excluded from the first version:

* Online ticket payments

* QR-code attendance tracking

* Email and SMS notifications

* Native mobile application

* Advanced analytics and recommendation algorithms

* Direct integration with external university systems (uses sample university event data initially)

## 3. Technology Stack

* **Backend:** Python, Flask

* **Frontend:** HTML5, CSS3, JavaScript (for optional client-side interactions)

* **Database:** SQLite

* **Testing:** pytest

* **Version Control & Collaboration:** Git, GitHub, GitHub Issues & Project Board

## 4. System Architecture & Database Design

### System Context Flow

The application operates as a browser-accessible web platform:
`Student / Organizer -> Web Browser -> Flask Application -> SQLite Database`

The browser sends requests to the Flask application, which processes the business logic, verifies authentication and role permissions, queries or updates the SQLite database, and returns the appropriate HTML views.

### Main Data Entities

* **User:** `user_id`, `name`, `email`, `password_hash`, `role` (Student or Organizer)

* **Event:** `event_id`, `title`, `description`, `date`, `location`, `organizer_id`, `capacity`

* **Registration:** `registration_id`, `user_id`, `event_id`, `registration_time`

### Quality Attributes

* **Security:** Passwords are stored as secure hashes, inputs are validated, and protected routes require authentication and proper role permissions.

* **Reliability & Data Integrity:** Database constraints and backend validation prevent duplicate registrations and capacity overflows.

* **Usability:** Clear navigation, readable event cards, and descriptive error/success messages across 5 core screens (*Event Listing, Event Detail, Login/Register, Student Dashboard, Organizer Dashboard*).

* **Maintainability:** Modular code structure supported by automated tests and setup documentation.

## 5. Installation Steps

Follow these steps to set up the project locally on your machine:

1. **Clone the repository:**

   ```
   git clone <repository-url>
   
   ```

2. **Navigate to the project directory:**

   ```
   cd evently
   
   ```

3. **Create and activate a virtual environment:**

   ```
   python -m venv venv
   
   ```

   * **On Windows:**

     ```
     venv\Scripts\activate
     
     ```

   * **On macOS / Linux:**

     ```
     source venv/bin/activate
     
     ```

4. **Install the required dependencies:**

   ```
   pip install -r requirements.txt
   
   ```

## 6. How to Run the Application

1. Ensure your virtual environment is activated.

2. Start the Flask development server:

   ```
   flask run
   
   ```

3. Open your web browser and go to:

   ```
   http://127.0.0.1:5000
   
   ```

## 7. How to Run Tests

We use **pytest** to verify core user workflows, role permissions, capacity checks, and duplicate registration rules. To run the automated test suite, execute the following command in the root directory of the project:

```
pytest

```

## 8. Collaboration & Branch Workflow

Our team follows an iterative development process using GitHub Issues and a GitHub Project Board:

* **`main` Branch:** Contains only the reviewed, tested, and stable version of the application.

* **Feature Branches:** Every task or feature is developed in its own separate branch.

* **Pull Requests (PRs):** Team members open a Pull Request when their task is complete.

* **Code Review & Testing:** At least one other team member must review the code, and all automated tests must pass before merging into `main`.

## 9. Team Members & Roles

| Team Member | Role | Main Responsibilities | 
| ----- | ----- | ----- | 
| **Kemal Kırımlı** | Frontend & User Experience | Develop HTML/CSS pages; create event listing, detail, login, and registration interfaces; ensure usability and visual consistency. | 
| **Eda Polat** | Backend Development | Implement Flask routes and application logic; develop user authentication, role-based access, and event management operations. | 
| **Yunus Yavuz** | Database & Testing | Design the SQLite database schema; implement and verify registration and capacity rules; write `pytest` suites and maintain technical documentation. | 
