<?php
// No server-side processing needed for this example, just serving the page
?>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List with Timer & Reminders</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            animation: fadeIn 1.5s ease-in-out;
        }

        .container {
            background-color: #fff;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            width: 400px;
            border-radius: 15px;
            text-align: center;
            animation: slideUp 1s ease-out;
        }

        h1 {
            font-size: 2.2em;
            color: #4CAF50;
            margin-bottom: 20px;
            font-family: 'Roboto', sans-serif;
        }

        input {
            width: 80%;
            padding: 12px;
            margin-right: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 1em;
        }

        button {
            padding: 12px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #45a049;
        }

        ul {
            list-style-type: none;
            padding: 0;
            margin-top: 20px;
        }

        li {
            padding: 12px;
            background-color: #f9f9f9;
            margin: 8px 0;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: relative;
            animation: fadeInUp 0.5s ease-out;
        }

        li button {
            background-color: #e74c3c;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.9em;
            transition: background-color 0.3s ease;
        }

        li button:hover {
            background-color: #c0392b;
        }

        .task-time {
            font-size: 0.9em;
            color: #888;
        }

        .reminder-message {
            position: absolute;
            top: -30px;
            right: 0;
            background-color: #f39c12;
            color: white;
            padding: 8px 15px;
            border-radius: 5px;
            font-size: 1.1em;
            display: none;
            animation: blink 1s infinite;
        }

        /* Blinking Animation */
        @keyframes blink {
            0% { opacity: 0; }
            50% { opacity: 1; }
            100% { opacity: 0; }
        }

        /* Fade-in page */
        @keyframes fadeIn {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        /* Slide-up container */
        @keyframes slideUp {
            0% { transform: translateY(30px); opacity: 0; }
            100% { transform: translateY(0); opacity: 1; }
        }

        /* Fade-in-up list items */
        @keyframes fadeInUp {
            0% { opacity: 0; transform: translateY(20px); }
            100% { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>To-Do List with Timer & Reminders</h1>
        <input type="text" id="taskInput" placeholder="Add a new task" />
        <input type="datetime-local" id="reminderInput" />
        <button id="addButton">Add Task</button>
        <ul id="taskList"></ul>
    </div>

    <audio id="reminderSound" preload="auto">
        <source src="https://www.soundjay.com/button/beep-07.wav" type="audio/wav">
    </audio>

    <script>
        // Load tasks from local storage on page load
        window.onload = function() {
            loadTasks();
        };

        // Add task to the list
        document.getElementById('addButton').addEventListener('click', function() {
            const taskInput = document.getElementById('taskInput');
            const taskText = taskInput.value.trim();
            const reminderInput = document.getElementById('reminderInput');
            const reminderTime = reminderInput.value;

            if (taskText) {
                addTask(taskText, reminderTime);
                taskInput.value = ''; // Clear input field
                reminderInput.value = ''; // Clear reminder field
            }
        });

        // Add task to the task list and local storage
        function addTask(taskText, reminderTime) {
            const taskList = document.getElementById('taskList');
            const li = document.createElement('li');
            
            li.textContent = taskText;
            
            const deleteButton = document.createElement('button');
            deleteButton.textContent = 'Delete';
            deleteButton.onclick = function() {
                removeTask(taskText);
            };

            if (reminderTime) {
                const taskTime = new Date(reminderTime);
                const timeRemaining = Math.max(taskTime - new Date(), 0);
                const reminderMessage = `Reminder set for: ${taskTime.toLocaleString()}`;
                const timeElement = document.createElement('div');
                timeElement.classList.add('task-time');
                timeElement.textContent = reminderMessage;
                li.appendChild(timeElement);
                
                // Show reminder message and sound when time arrives
                setReminder(taskText, timeRemaining, li);
            }

            li.appendChild(deleteButton);
            taskList.appendChild(li);
            
            saveTask(taskText, reminderTime);
        }

        // Save task to local storage
        function saveTask(taskText, reminderTime) {
            let tasks = JSON.parse(localStorage.getItem('tasks')) || [];
            tasks.push({ taskText, reminderTime });
            localStorage.setItem('tasks', JSON.stringify(tasks));
        }

        // Remove task from the task list and local storage
        function removeTask(taskText) {
            let tasks = JSON.parse(localStorage.getItem('tasks')) || [];
            tasks = tasks.filter(task => task.taskText !== taskText);
            localStorage.setItem('tasks', JSON.stringify(tasks));
            
            // Reload tasks to reflect changes
            loadTasks();
        }

        // Set reminder for the task
        function setReminder(taskText, timeRemaining, li) {
            setTimeout(function() {
                // Show reminder message
                const reminderMessage = document.createElement('div');
                reminderMessage.classList.add('reminder-message');
                reminderMessage.textContent = `Reminder: ${taskText}`;
                li.appendChild(reminderMessage);
                reminderMessage.style.display = 'block';

                // Play sound
                const sound = document.getElementById('reminderSound');
                sound.play();
            }, timeRemaining);
        }

        // Load tasks from local storage and display them
        function loadTasks() {
            const tasks = JSON.parse(localStorage.getItem('tasks')) || [];
            const taskList = document.getElementById('taskList');
            taskList.innerHTML = ''; // Clear current list
            
            tasks.forEach(task => {
                const li = document.createElement('li');
                li.textContent = task.taskText;
                
                const deleteButton = document.createElement('button');
                deleteButton.textContent = 'Delete';
                deleteButton.onclick = function() {
                    removeTask(task.taskText);
                };

                if (task.reminderTime) {
                    const taskTime = new Date(task.reminderTime);
                    const timeRemaining = Math.max(taskTime - new Date(), 0);
                    const reminderMessage = `Reminder set for: ${taskTime.toLocaleString()}`;
                    const timeElement = document.createElement('div');
                    timeElement.classList.add('task-time');
                    timeElement.textContent = reminderMessage;
                    li.appendChild(timeElement);

                    // Set reminder for this task
                    setReminder(task.taskText, timeRemaining, li);
                }

                li.appendChild(deleteButton);
                taskList.appendChild(li);
            });
        }
    </script>
</body>
</html>
