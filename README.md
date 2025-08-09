# speakpal-app
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Simple SpeakPal App</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>Welcome to Simple SpeakPal</h1>
  <button id="speak-btn">Start Speaking</button>
  <p id="result"></p>

  <script src="app.js"></script>
</body>
</html>
const button = document.getElementById('speak-btn');
const result = document.getElementById('result');

button.addEventListener('click', () => {
  const recognition = new (window.SpeechRecognition || window.webkitSpeechRecognition)();
  recognition.lang = 'en-US';
  recognition.start();

  recognition.onresult = (event) => {
    const speech = event.results[0][0].transcript;
    result.textContent = 'You said: ' + speech;
  };

  recognition.onerror = (event) => {
    result.textContent = 'Error: ' + event.error;
  };
});
cd path/to/your/project/folder
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git branch -M main
git push -u origin main
