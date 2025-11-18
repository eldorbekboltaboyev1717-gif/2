<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vazifalar ro'yxati</title>
    <style>
        body { font-family: Arial; margin: 20px; }
        input { padding: 8px; width: 250px; }
        button { padding: 8px 12px; margin-left: 5px; }
        ul { list-style: none; padding-left: 0; }
        li { padding: 5px 0; }
        li.done { text-decoration: line-through; color: gray; }
    </style>
</head>
<body>
    <h2>Vazifalar ro'yxati</h2>
    <input type="text" id="taskInput" placeholder="Yangi vazifa kiriting">
    <button onclick="addTask()">Qo'shish</button>
    <ul id="taskList"></ul>

    <script>
        function addTask() {
            const input = document.getElementById('taskInput');
            const task = input.value.trim();
            if(!task) return alert("Vazifa kiriting!");
            
            const li = document.createElement('li');
            li.innerHTML = `${task} <button onclick="markDone(this)">Bajarildi</button> <button onclick="deleteTask(this)">O'chirish</button>`;
            document.getElementById('taskList').appendChild(li);
            input.value = "";
        }

        function markDone(btn) {
            btn.parentElement.classList.toggle('done');
        }

        function deleteTask(btn) {
            btn.parentElement.remove();
        }
    </script>
</body>
</html>
