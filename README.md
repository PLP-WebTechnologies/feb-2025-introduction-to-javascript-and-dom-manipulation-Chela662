<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Web Page</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <header>
    <h1>Interactive JavaScript</h1>
  </header>

  <section id="content">
    <p>This is a paragraph with some initial content. Click the button below to change the text.</p>
    
    <button id="changeTextBtn">Change Text</button>
    <button id="addElementBtn">Add New Element</button>
    <button id="removeElementBtn">Remove Last Element</button>
    <button id="changeBackgroundBtn">Change Background Color</button>
    
    <form id="userForm">
      <label for="userInput">Enter some text:</label>
      <input type="text" id="userInput" placeholder="Type here">
      <button type="submit">Display Input</button>
    </form>
    
    <div id="userInputDisplay"></div>
  </section>

  <footer>
    <p>&copy; 2025 Interactive Web Page</p>
  </footer>

    <script>
        // Change text content dynamically
document.getElementById("changeTextBtn").addEventListener("click", function() {
  const paragraph = document.querySelector("p");
  paragraph.textContent = "The text has been changed dynamically!";
  paragraph.style.color = "green"; // Modify CSS via JavaScript
});

// Add a new element dynamically
document.getElementById("addElementBtn").addEventListener("click", function() {
  const newDiv = document.createElement("div");  // Create new div
  newDiv.innerHTML = "<p>This is a new dynamically added element!</p>";
  newDiv.style.backgroundColor = "#e7f7ff";
  newDiv.style.padding = "10px";
  newDiv.style.marginTop = "20px";
  
  document.getElementById("content").appendChild(newDiv);  // Add to DOM
});

// Remove the last added element
document.getElementById("removeElementBtn").addEventListener("click", function() {
  const content = document.getElementById("content");
  const lastElement = content.lastElementChild;
  
  if (lastElement) {
    content.removeChild(lastElement);  // Remove last added element
  }
});

// Change background color of the page
document.getElementById("changeBackgroundBtn").addEventListener("click", function() {
  document.body.style.backgroundColor = "#ffebcd"; // Light background color
});

// Display user input dynamically
document.getElementById("userForm").addEventListener("submit", function(event) {
  event.preventDefault();  // Prevent form submission
  const userInput = document.getElementById("userInput").value;
  const displayDiv = document.getElementById("userInputDisplay");

  displayDiv.textContent = `You entered: ${userInput}`;
  document.getElementById("userInput").value = "";  // Clear input field after submission
});

    </script>
</body>
</html>
#css
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    color: #333;
    line-height: 1.6;
    font-size: 16px;
    text-align: left; 
  }
  
  header {
    background-color: #333;
    color: white;
    padding: 10px 0;
    text-align: center;
    font-size: 24px;
    font-weight: bold;
    position: sticky;
    top: 0;
  }
  
  #content {
    margin: 20px;
    position: left;
  }
  .background {
    background-color: #f4f4f4;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  button {
    padding: 10px 20px;
    margin: 10px 0;
    background-color: #007BFF;
    color: white;
    border: none;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
   
  footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px 0;
    position: fixed;
    width: 100%;
    bottom: 0;
  }
  
