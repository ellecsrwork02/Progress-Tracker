<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Checklist Progress Tracker</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }
    .progress-container {
      margin: 20px 0;
    }
    .progress-bar {
      width: 100%;
      background: #ddd;
      border-radius: 5px;
    }
    .progress {
      height: 20px;
      background: #4caf50;
      width: 0%;
      border-radius: 5px;
    }
    ul {
      list-style-type: none;
      padding: 0;
    }
    li {
      margin: 10px 0;
    }
    input[type="checkbox"] {
      margin-right: 10px;
    }
  </style>
</head>
<body>
  <h1>Checklist Progress Tracker</h1>

  <!-- Progress Bar -->
  <div class="progress-container">
    <div class="progress-bar">
      <div class="progress" id="progress"></div>
    </div>
    <p id="progress-text">0% Complete</p>
  </div>

  <!-- Checklist -->
  <ul id="task-list">
    <li><input type="checkbox" class="task" onchange="updateProgress()"> Task 1</li>
    <li><input type="checkbox" class="task" onchange="updateProgress()"> Task 2</li>
    <li><input type="checkbox" class="task" onchange="updateProgress()"> Task 3</li>
    <li><input type="checkbox" class="task" onchange="updateProgress()"> Task 4</li>
    <li><input type="checkbox" class="task" onchange="updateProgress()"> Task 5</li>
  </ul>

  <script>
    function updateProgress() {
      const tasks = document.querySelectorAll('.task');
      const totalTasks = tasks.length;
      const completedTasks = Array.from(tasks).filter(task => task.checked).length;

      const progressValue = (completedTasks / totalTasks) * 100;
      const progressBar = document.getElementById('progress');
      const progressText = document.getElementById('progress-text');

      progressBar.style.width = progressValue + '%';
      progressText.innerText = Math.round(progressValue) + '% Complete';
    }
  </script>
</body>
</html>
