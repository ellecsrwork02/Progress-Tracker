# Progress-Tracker
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Review Progress Tracker</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 20px; }
    .progress-container { margin: 20px 0; }
    .progress-bar { width: 100%; background: #ddd; border-radius: 5px; }
    .progress { height: 20px; background: #4caf50; width: 0%; border-radius: 5px; }
    button { margin-top: 10px; padding: 10px 20px; background: #4caf50; color: #fff; border: none; border-radius: 5px; cursor: pointer; }
  </style>
</head>
<body>
  <h1>Review Progress Tracker</h1>
  <div class="progress-container">
    <div class="progress-bar">
      <div class="progress" id="progress"></div>
    </div>
    <p id="progress-text">0% Complete</p>
    <button onclick="updateProgress()">Update Progress</button>
  </div>

  <script>
    let progressValue = 0;
    function updateProgress() {
      if (progressValue < 100) {
        progressValue += 10;
        const progressBar = document.getElementById('progress');
        const progressText = document.getElementById('progress-text');
        progressBar.style.width = progressValue + '%';
        progressText.innerText = progressValue + '% Complete';
      }
    }
  </script>
</body>
</html>

