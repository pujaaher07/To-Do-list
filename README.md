<!DOCTYPE html>
<html>
<head>
    <title>To-Do List</title>

    <style>
        body {
            font-family: Arial;
            background-color: #f4f4f4;
        }

        .container {
            width: 320px;
            margin: 100px auto;
            text-align: center;
            background: white;
            padding: 20px;
            border-radius: 10px;
        }

        input {
            width: 65%;
            padding: 8px;
        }

        button {
            padding: 8px;
            cursor: pointer;
        }

        li {
            margin: 10px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .deleteBtn {
            background-color: red;
            color: white;
            border: none;
            padding: 5px 8px;
            border-radius: 5px;
        }

        .deleteBtn:hover {
            background-color: darkred;
        }
    </style>
</head>

<body>

<div class="container">
    <h2>My To-Do List</h2>

    <input type="text" id="taskInput" placeholder="Enter task">
    <button onclick="addTask()">Add</button>

    <ul id="taskList"></ul>
</div>

<script>
    function addTask() {
        let input = document.getElementById("taskInput");
        let task = input.value;

        if (task === "") {
            alert("Please enter a task");
            return;
        }

        let li = document.createElement("li");

        let span = document.createElement("span");
        span.textContent = task;

        span.onclick = function () {
            span.style.textDecoration = "line-through";
        };

        let delBtn = document.createElement("button");
        delBtn.textContent = "X";
        delBtn.className = "deleteBtn";

        delBtn.onclick = function () {
            li.remove();
        };

        li.appendChild(span);
        li.appendChild(delBtn);

        document.getElementById("taskList").appendChild(li);

        input.value = "";
    }
</script>

</body>
</html>
