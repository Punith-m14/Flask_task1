### DAY ☀️ : Creating a Task Management System in Flask (Level-9 with Animation, Marquee Text, and Motivation Line)

```
Created by:
Name: Dhiraj Kr.
Profession: Data Scientist & GenAI Developer
```

---

### Introduction:

In **Level-9**, we will add some visual enhancements such as **CSS animations** for a smoother experience, a **marquee text** below the navbar with a motivational line, and style improvements using **Bootstrap**. These changes will make the task management system more engaging and visually appealing.

---

### Folder Structure:

```
task_manager/
│
├── app.py               # Main Flask application
├── templates/           # Folder containing HTML files
│   ├── base.html        # Base template with navbar, footer, and animations
│   ├── index.html       # Homepage showing tasks in card format
│   ├── add_task.html    # Page to add new tasks
│   ├── delete_task.html # Page to delete tasks
│   ├── login.html       # Login page
└── static/              # Folder for static files like CSS, JS
    └── styles.css       # Custom CSS for animations and styles
```

---

### 1. **Custom CSS File (styles.css)**

In the `static` folder, create a new file called **`styles.css`** to add custom animations and styles.

```css
/* Custom CSS for Animations */
@keyframes fadeIn {
    0% { opacity: 0; }
    100% { opacity: 1; }
}

.card {
    animation: fadeIn 1.5s ease-in;
}

.marquee {
    width: 100%;
    overflow: hidden;
    white-space: nowrap;
    box-sizing: border-box;
    animation: marquee 15s linear infinite;
}

@keyframes marquee {
    0% { transform: translateX(100%); }
    100% { transform: translateX(-100%); }
}

.marquee p {
    display: inline-block;
    padding-left: 100%;
    font-size: 18px;
    color: #fff;
    font-weight: bold;
}
```

- **Explanation**:
  - **fadeIn**: Adds a smooth fade-in effect to the task cards.
  - **marquee**: Scrolls motivational text continuously below the navbar.

---

### 2. **Update `base.html` to Include Marquee Text and Animation CSS**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% block title %}Task Management System{% endblock %}</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <link rel="stylesheet" href="{{ url_for('static', filename='styles.css') }}">
</head>
<body>

    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <a class="navbar-brand" href="/">Task Manager</a>
        <div class="collapse navbar-collapse">
            <ul class="navbar-nav ml-auto">
                <li class="nav-item">
                    <a class="nav-link" href="/">Home</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="/add-task">Add Task</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="/delete-task">Delete Task</a>
                </li>
                {% if 'logged_in' in session %}
                <li class="nav-item">
                    <a class="nav-link" href="/logout">Logout</a>
                </li>
                {% endif %}
            </ul>
        </div>
    </nav>

    <!-- Marquee with Motivational Text -->
    <div class="bg-primary marquee">
        <p>Success is the sum of small efforts, repeated day in and day out. Keep going, you are doing great!</p>
    </div>

    <!-- Main Content -->
    <div class="container mt-5">
        {% block content %}{% endblock %}
    </div>

    <!-- Footer -->
    <footer class="bg-dark text-white text-center py-3 mt-5">
        <p>&copy; 2024 Task Management System | Created by Dhiraj Kr.</p>
    </footer>

    <!-- Bootstrap JS and dependencies -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
</body>
</html>
```

- **Explanation**:
  - The **marquee** section contains motivational text that scrolls from right to left continuously.
  - The **`styles.css`** file is linked to provide animation and additional styling.

---

### 3. **Update `index.html` to Display Tasks with Animation**

```html
{% extends 'base.html' %}

{% block title %}Homepage | Task Manager{% endblock %}

{% block content %}
<h1 class="text-center">Welcome to the Task Management System</h1>
<p class="text-center">This is a simple task manager to help you organize your tasks.</p>

<!-- Add Task and Delete Task Buttons -->
<div class="text-center mt-4">
    <a href="/add-task" class="btn btn-primary btn-lg mx-2">Add Task</a>
    <a href="/delete-task" class="btn btn-danger btn-lg mx-2">Delete Task</a>
</div>

<!-- Task List in Card Format with Animation -->
<div class="row mt-5">
    {% if tasks %}
        {% for task in tasks %}
        <div class="col-md-4">
            <div class="card mb-3">
                <div class="card-body">
                    <h5 class="card-title">{{ task }}</h5>
                </div>
            </div>
        </div>
        {% endfor %}
    {% else %}
    <div class="col-12">
        <p class="text-center">No tasks added yet.</p>
    </div>
    {% endif %}
</div>
{% endblock %}
```

- **Explanation**:
  - Each task card will now have a **fade-in animation** when displayed on the page.

---

### How to Run the Task Management System with Animation and Marquee Text:

1. **Install Flask**:
   - If Flask is not installed, run:

   ```bash
   pip install flask
   ```

2. **Run the Flask App**:
   - Navigate to the folder where your `app.py` is located and run:

   ```bash
   python app.py
   ```

3. **Access the Application**:
   - Open your browser and go to **http://127.0.0.1:5000/**.
   - Log in using the **username** and **password** as `drj`.
   - After logging in, you will see tasks displayed with animations and a motivational scrolling marquee text below the navbar.

---

### Key Features:

- **Logout Feature**: Users can log out, and their session will be cleared.
- **Task Display in Card Format**: Tasks are now shown in Bootstrap cards with a **fade-in animation**.
- **Motivational Marquee Text**: A motivational message scrolls below the navbar continuously.
- **Responsive Design**: The task cards and marquee are responsive and adjust to different screen sizes.

---

**End of Document** ✨