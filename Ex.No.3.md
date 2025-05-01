# Ex03 To-Do List using JavaScript

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
### index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Aesthetic To-Do List</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="app-container">
    <h1 class="title">🌸 My To-Do List</h1>
    <div class="input-container">
      <input type="text" id="todo-input" placeholder="What do you need to do?" />
      <button id="add-btn">Add</button>
    </div>
    <ul id="todo-list"></ul>
  </div>
  <script src="script.js"></script>
</body>
</html>

```

### style.css
```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  
  body {
    background: linear-gradient(to right, #ffdde1, #ee9ca7);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
  
  .app-container {
    background: #fff;
    padding: 30px;
    border-radius: 20px;
    width: 400px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.1);
  }
  
  .title {
    text-align: center;
    color: #ee9ca7;
    margin-bottom: 20px;
  }
  
  .input-container {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
  }
  
  #todo-input {
    flex: 1;
    padding: 10px;
    border: 2px solid #ee9ca7;
    border-radius: 10px;
    outline: none;
  }
  
  #add-btn {
    padding: 10px 20px;
    background-color: #ee9ca7;
    color: white;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: background 0.3s ease;
  }
  
  #add-btn:hover {
    background-color: #ff6f91;
  }
  
  #todo-list {
    list-style: none;
    max-height: 300px;
    overflow-y: auto;
  }
  
  .todo-item {
    background: #fbeeff;
    padding: 10px 15px;
    margin-bottom: 10px;
    border-radius: 12px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    animation: fadeIn 0.3s ease-in;
  }
  
  .todo-item span {
    word-break: break-word;
  }
  
  .delete-btn {
    background: none;
    border: none;
    font-size: 18px;
    color: #ff6f91;
    cursor: pointer;
    transition: transform 0.2s ease;
  }
  
  .delete-btn:hover {
    transform: scale(1.2);
  }
  
  /* Animation */
  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(8px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
```
### script.js
```
const addBtn = document.getElementById("add-btn");
const input = document.getElementById("todo-input");
const list = document.getElementById("todo-list");

addBtn.addEventListener("click", addTodo);
input.addEventListener("keypress", (e) => {
  if (e.key === "Enter") addTodo();
});

function addTodo() {
  const taskText = input.value.trim();
  if (taskText === "") return;

  const listItem = document.createElement("li");
  listItem.className = "todo-item";

  const span = document.createElement("span");
  span.textContent = taskText;

  const delBtn = document.createElement("button");
  delBtn.className = "delete-btn";
  delBtn.innerHTML = "🗑️";
  delBtn.onclick = () => {
    listItem.classList.add("fade-out");
    setTimeout(() => listItem.remove(), 200);
  };

  listItem.appendChild(span);
  listItem.appendChild(delBtn);
  list.appendChild(listItem);
  input.value = "";
}

```

## OUTPUT
![image](https://github.com/user-attachments/assets/8a20ac1f-0e97-4dd1-81e2-77a79b87726c)


## RESULT
The program for creating To-do list using JavaScript is executed successfully.
