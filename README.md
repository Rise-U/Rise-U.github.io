# Rise-U.github.io
// Preload and sound when page loads
window.onload = function () {
  const preload = document.querySelector('.preload');
  const fistIcon = document.querySelector('.fist-icon');
  
  // Play sound
  let audio = new Audio('pop-sound.mp3'); // Path to the sound
  audio.play();

  // Fade out the preload icon after animation
  setTimeout(() => {
    preload.style.opacity = 0;
    setTimeout(() => {
      preload.style.display = 'none'; // Hide it completely after fade
      document.querySelector('.home-screen').style.display = 'grid'; // Show the main screen
    }, 500);
  }, 1000); // Fade after 1s
};

// Function to open an app (page transition)
function openApp(appName) {
  const appContent = document.getElementById('app-content');
  
  appContent.innerHTML = `<div class="app-content">${appName} App</div>`;
  appContent.style.animation = 'fadeIn 1s ease-out forwards';
}

// App Content FadeIn Animation
const styleSheet = document.styleSheets[0];
styleSheet.insertRule('@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }', styleSheet.cssRules.length);

