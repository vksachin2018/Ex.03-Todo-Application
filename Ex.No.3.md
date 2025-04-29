# Ex03 To-Do List using JavaScript
## Date:28.03.25

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM
### Index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>To-Do List</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="todo-container">
    <h1>📝 To-Do List</h1>
    <input type="text" id="taskInput" placeholder="Add a new task">
    <button onclick="addTask()">Add</button>
    <ul id="taskList"></ul>
  </div>

  <script src="script.js"></script>
</body>
</html>
```
### Style.css
```
/* Reset some default styles */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #e0f7fa, #ffffff);
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .todo-container {
    background: #ffffff;
    padding: 40px 30px;
    border-radius: 15px;
    box-shadow: 0 8px 30px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 400px;
    transition: transform 0.2s ease-in-out;
  }
  
  .todo-container:hover {
    transform: translateY(-5px);
  }
  
  .todo-container h1 {
    text-align: center;
    margin-bottom: 25px;
    color: #00796b;
    font-size: 28px;
  }
  
  input[type="text"] {
    width: 100%;
    padding: 12px 15px;
    border: 2px solid #b2dfdb;
    border-radius: 8px;
    margin-bottom: 15px;
    font-size: 16px;
    outline: none;
    transition: border-color 0.3s;
  }
  
  input[type="text"]:focus {
    border-color: #00796b;
  }
  
  button {
    width: 100%;
    padding: 12px;
    background-color: #00796b;
    color: #fff;
    border: none;
    border-radius: 8px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  button:hover {
    background-color: #004d40;
  }
  
  ul {
    list-style-type: none;
    margin-top: 20px;
  }
  
  li {
    background: #f1f8e9;
    padding: 12px 15px;
    margin-bottom: 10px;
    border-radius: 8px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: background 0.3s ease;
  }
  
  li:hover {
    background: #dcedc8;
  }
  
  li.completed {
    text-decoration: line-through;
    color: #757575;
    background: #e0e0e0;
  }
  
  li button {
    background: none;
    border: none;
    font-size: 18px;
    color: #e53935;
    cursor: pointer;
    transition: transform 0.2s ease;
  }
  
  li button:hover {
    transform: scale(1.3);
  }
  ```
### Script.js
```
function addTask() {
    const taskInput = document.getElementById("taskInput");
    const taskText = taskInput.value.trim();
    if (taskText === "") return;
  
    const li = document.createElement("li");
    li.textContent = taskText;
  
    li.addEventListener("click", function () {
      li.classList.toggle("completed");
    });
  
    const deleteBtn = document.createElement("button");
    deleteBtn.textContent = "❌";
    deleteBtn.style.marginLeft = "10px";
    deleteBtn.onclick = function () {
      li.remove();
    };
  
    li.appendChild(deleteBtn);
    document.getElementById("taskList").appendChild(li);
    taskInput.value = "";
  }
  ```

## OUTPUT
![Screenshot 2025-04-26 103609](https://github.com/user-attachments/assets/cf71ab1c-53a4-4ae9-8db6-cb822484e555)

## RESULT
The program for creating To-do list using JavaScript is executed successfully.
