# Flask_task1

---

# ✅ Simple Flask Task Manager App

A lightweight, web-based Task Manager application built with **Flask**. This project demonstrates the fundamentals of session management, user authentication, and CRUD operations in a Python web framework.

---

## 🚀 Features

- **User Authentication:** Secure login and logout functionality using Flask sessions.
- **Task Management:** 
  - Add new tasks via a simple web form.
  - View the current list of tasks.
  - Delete selected tasks from the list.
- **Session-Based Access Control:** All task management operations are restricted to authenticated users.
- **Flash Messaging:** Provides instant feedback on actions like login errors, successful logout, or invalid operations.
- **Clean and Simple Routing:** Organized route structure for easy navigation and extensibility.
- **Modular Template System:** Uses **Jinja2** templating for clean and reusable HTML views.

---

## 📦 Tech Stack

- **Backend:** Python 3, Flask
- **Frontend:** HTML5, Jinja2 (templating)
- **Session Management:** Flask’s built-in session handling
- *(Optional enhancement ready)* CSS/Bootstrap for UI improvements

---

## 📂 Project Structure

```
├── app.py                 # Main Flask application file
├── templates/
│   ├── index.html         # Homepage displaying task list
│   ├── login.html         # Login form
│   ├── add_task.html      # Form to add a new task
│   └── delete_task.html   # Form to delete a task
└── static/                # (Optional) Directory for CSS and static assets
```

---

## 📝 How to Run

1. **Install required dependencies**:
   ```bash
   pip install flask
   ```

2. **Run the application**:
   ```bash
   python app.py
   ```

3. **Access the app**:
   Open your web browser and navigate to [http://127.0.0.1:5000](http://127.0.0.1:5000)

---

## 🔒 Default Credentials

- **Username:** `drj`
- **Password:** `drj`

---

## 🎯 Learning Highlights

- Basics of web development with Flask.
- Implementing session-based authentication.
- Performing CRUD operations on in-memory data structures.
- Structuring a small Flask project with templates and routes.
- Flash messaging for user interaction feedback.

---

## 📌 Future Improvements

- Replace hardcoded credentials with a user database and hashed passwords.
- Persist tasks using a database like SQLite or PostgreSQL.
- Add task editing, deadlines, and task status tracking.
- Enhance user interface with CSS frameworks like Bootstrap or Tailwind CSS.
- Implement user-specific task lists.
- Deploy the application to a cloud platform like Heroku or Render.

---

## 📬 Contact

For questions, suggestions, or collaborations — feel free to reach out!

---

