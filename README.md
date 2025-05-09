# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

HTML (index.html):

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Animations with JavaScript</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <div id="box" class="box"></div>
  
  <button id="animateButton">Animate Box</button>
  <button id="savePreferenceButton">Save Preference</button>

  <script src="script.js"></script>
</body>
</html>


CSS (styles.css):

/* Box element styling */
.box {
  width: 100px;
  height: 100px;
  background-color: blue;
  margin: 50px;
  transition: all 0.5s ease-in-out;
}

/* CSS Animation */
@keyframes moveBox {
  0% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(200px);
  }
  100% {
    transform: translateX(0);
  }
}

/* Animation class */
.animate {
  animation: moveBox 2s ease-in-out infinite;
}

/* Button styles */
button {
  margin: 10px;
  padding: 10px 20px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
}


JavaScript (script.js):

// Get the elements
const box = document.getElementById("box");
const animateButton = document.getElementById("animateButton");
const savePreferenceButton = document.getElementById("savePreferenceButton");

// Check if there's a stored preference for animation
const storedPreference = localStorage.getItem("animateBox");
if (storedPreference === "true") {
  box.classList.add("animate");
} else {
  box.classList.remove("animate");
}

// Trigger animation when the "Animate Box" button is clicked
animateButton.addEventListener("click", () => {
  box.classList.add("animate");
  // Store the preference in localStorage so the animation persists across page loads
  localStorage.setItem("animateBox", "true");
});

// Save the preference to stop the animation
savePreferenceButton.addEventListener("click", () => {
  box.classList.remove("animate");
  localStorage.setItem("animateBox", "false");
});

