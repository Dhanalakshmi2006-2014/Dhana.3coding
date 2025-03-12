HTML Code

<!DOCTYPE html>
<html>
<head>
	<title>To-Do List App</title>
	<link rel="stylesheet" href="style.css">
</head>
<body>
	<h1>To-Do List App</h1>
	<input type="text" id="task" placeholder="Enter task">
	<button id="add-task">Add Task</button>
	<ul id="task-list"></ul>
	<script src="script.js"></script>
</body>
</html>


CSS Code (in style.css file)

body {
	font-family: Arial, sans-serif;
	margin: 0;
	padding: 0;
}

#task {
	width: 50%;
	height: 30px;
	padding: 10px;
	margin-bottom: 10px;
	border: 1px solid #ccc;
}

#add-task {
	background-color: #4CAF50;
	color: #fff;
	padding: 10px 20px;
	border: none;
	border-radius: 5px;
	cursor: pointer;
}

#task-list {
	list-style: none;
	padding: 0;
	margin: 0;
}

#task-list li {
	padding: 10px;
	border-bottom: 1px solid #ccc;
}

#task-list li:last-child {
	border-bottom: none;
}

JavaScript Code (in script.js file)
let taskList = document.getElementById('task-list');
let taskInput = document.getElementById('task');
let addTaskButton = document.getElementById('add-task');

addTaskButton.addEventListener('click', addTask);

function addTask() {
	let task = taskInput.value.trim();
	if (task !== '') {
		let taskListItem = document.createElement('li');
		taskListItem.textContent = task;
		taskList.appendChild(taskListItem);
		taskInput.value = '';
	}
}

taskList.addEventListener('click', deleteTask);

function deleteTask(event) {
	if (event.target.tagName === 'LI') {
		event.target.remove();
	}
}
