# 📝 Todo List with Event Bubbling

A simple and beginner-friendly **Todo List Web Application** built with **HTML and JavaScript** to understand **DOM manipulation, event handling, and event bubbling**.

The application allows users to add new tasks and delete existing tasks. The main learning objective of this project is to understand how **event bubbling can be used for event delegation**, especially when working with dynamically created elements.

---

## 🚀 Features

* ➕ Add new tasks
* 🗑️ Delete existing tasks
* ⚡ Dynamically create Todo items
* 🎯 Event delegation using event bubbling
* 🖱️ Click event handling
* 🌐 Simple browser-based application
* 💡 Beginner-friendly JavaScript implementation



## 🛠️ Technologies Used

* **HTML5** – Structure of the application
* **JavaScript** – Application logic and interactivity
* **DOM Manipulation** – Dynamically creating and removing elements
* **Event Bubbling** – Handling events from dynamically created elements

---

## 📂 Project Structure

```text
Todolist-with-event-bubbling-behaviour/
│
├── index.html       # Todo application interface
├── Todolist.js      # Todo logic and event handling
└── README.md        # Project documentation
```

---

# 🎯 How the Application Works

The application contains:

* An input field for entering a task
* An **Add Task** button
* An unordered list (`<ul>`) containing Todo items
* A delete button for each Todo item

The HTML currently provides the basic Todo interface, while `Todolist.js` handles task creation and deletion.

### Application Flow

```text
User enters a task
        ↓
Clicks "Add Task"
        ↓
JavaScript creates <li>
        ↓
Delete button is created
        ↓
Task is added to <ul>
        ↓
User clicks Delete
        ↓
Click event bubbles to <ul>
        ↓
JavaScript identifies clicked button
        ↓
Task is removed
```

---

# 🧩 Event Bubbling

One of the main concepts demonstrated in this project is **event bubbling**.

When an event occurs on an element, the event can propagate upward through its parent elements.

For example:

```text
Button
  ↑
  │
List Item
  ↑
  │
  UL
  ↑
  │
Parent Element
```

In this project, instead of adding a separate click event listener to every delete button, a single listener is attached to the `<ul>` element.

---

# 🎯 Event Delegation

The project uses **event delegation** to handle delete operations.

The important part of the JavaScript is:

```javascript
ul.addEventListener("click", function(event) {
    if (event.target.nodeName == "BUTTON") {
        let listItem = event.target.parentElement;
        listItem.remove();
    }
});
```

When a delete button is clicked:

```text
Delete Button
      ↓
Event occurs
      ↓
Event bubbles
      ↓
UL receives event
      ↓
event.target identifies button
      ↓
Parent <li> is selected
      ↓
<li> is removed
```

This approach is particularly useful because the Todo items and their delete buttons are created dynamically after the page loads.

---

# ➕ Adding a Task

When the user clicks the **Add Task** button, JavaScript creates a new `<li>` element.

The application performs these steps:

```javascript
let item = document.createElement("li");
item.innerText = inp.value;
```

Then it creates a delete button:

```javascript
let delbtn = document.createElement("button");

delbtn.innerText = "delete";
delbtn.classList.add("delete");
```

The button is added to the task:

```javascript
item.appendChild(delbtn);
```

Finally, the task is added to the Todo list:

```javascript
ul.appendChild(item);
```

The input is then cleared for the next task.

---

# 🗑️ Deleting a Task

When the user clicks a delete button, the event reaches the `<ul>` through event bubbling.

The application checks:

```javascript
event.target.nodeName == "BUTTON"
```

Then it gets the button's parent `<li>`:

```javascript
let listItem = event.target.parentElement;
```

Finally, it removes the task:

```javascript
listItem.remove();
```

This demonstrates how event delegation can be used instead of creating individual listeners for every dynamically created delete button.

---

# 🔄 Event Bubbling vs Individual Event Listeners

### Traditional Approach

You could add an event listener to every delete button:

```javascript
deleteButton.addEventListener("click", function() {
    // delete task
});
```

However, dynamically created buttons would require additional handling.

### Event Delegation Approach

Instead, this project attaches one listener to the parent `<ul>`:

```javascript
ul.addEventListener("click", function(event) {
    // identify clicked button
});
```

This allows dynamically added buttons to work with the same event listener.

---

# 🧠 JavaScript Concepts Learned

Through this project, I practiced:

* DOM manipulation
* `querySelector()`
* `addEventListener()`
* `createElement()`
* `appendChild()`
* `parentElement`
* `remove()`
* `event.target`
* Event bubbling
* Event delegation
* Dynamic HTML element creation
* Handling dynamically generated elements

---

# ▶️ How to Run

## 1. Clone the repository

```bash
git clone https://github.com/Ganesh-Machale/Todolist-with-event-bubbling-behaviour.git
```

## 2. Navigate to the project

```bash
cd Todolist-with-event-bubbling-behaviour
```

## 3. Open the project

Open:

```text
index.html
```

in your browser.

You can also use **VS Code Live Server** for development.

---

# 📸 Application Interface

The current application contains:

```text
Todo App

[ Enter your task: ] [ Add Task ]

• Eat       [delete]
• Sleep     [delete]
```

Users can add additional tasks dynamically, and each generated task receives a delete button.

---

# 🎯 Purpose of the Project

The main purpose of this project is not only to build a Todo List but also to understand an important JavaScript concept:

> **Event Bubbling and Event Delegation**

The project demonstrates how a parent element can handle events triggered by its child elements.

This is especially useful when working with dynamically generated DOM elements.

---

# 🔮 Future Improvements

Possible improvements include:

* ✅ Mark tasks as completed
* ✏️ Edit existing tasks
* 💾 Save tasks using Local Storage
* 🔍 Search tasks
* 🗂️ Add task categories
* 📅 Add due dates
* 🎨 Improve UI/UX
* 🌙 Add dark mode
* 📱 Improve responsive design
* 🚫 Prevent empty tasks
* 🕒 Add task timestamps

---

# 📚 Learning Outcome

This project helped me understand an important practical JavaScript workflow:

```text
DOM
 ↓
Event Listener
 ↓
Event Target
 ↓
Event Bubbling
 ↓
Event Delegation
 ↓
Dynamic Element Handling
```

Understanding event bubbling and event delegation provides a useful foundation for building larger interactive JavaScript applications and frontend frameworks.

---

# 👨‍💻 Author

## Ganesh Machale

**Full Stack Web Developer | MERN Stack Developer**

### GitHub

https://github.com/Ganesh-Machale

### Repository

https://github.com/Ganesh-Machale/Todolist-with-event-bubbling-behaviour

---

## ⭐ Support

If you found this project useful for learning JavaScript, consider giving the repository a ⭐ **Star** on GitHub.

---

### 🏷️ Topics

`JavaScript` `HTML` `DOM` `EventBubbling` `EventDelegation` `TodoList` `JavaScriptDOM` `FrontendDevelopment` `WebDevelopment`
