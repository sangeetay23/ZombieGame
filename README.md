## Zombie Attack Game Documentation

This documentation outlines the structure and functionality of the "Zombie Attack" game, built using HTML, CSS, and JavaScript.

###  index.html

**Purpose:** This file defines the HTML structure of the game.

**Breakdown:**

1. **Basic HTML structure:** Contains `<html>`, `<head>`, and `<body>` tags.
2. **Meta tags:** Sets charset, compatibility, and viewport settings.
3. **Title:** Defines the title of the webpage as "Zombie Attack".
4. **Stylesheet:** Links to the `styles.css` file for styling the game.
5. **Script:** Links to the `script.js` file containing game logic, with `defer` attribute to ensure HTML is fully parsed before executing the script.
6. **Audio elements:** Includes three audio elements:
   - `gunshot`:  A machine gun sound for player shots.
   - `start-sound`: A sound effect that plays when the game starts.
   - `lose-sound`: A sound effect that plays when the player loses.
7. **Author:** Displays the game developer's name and link to their website.
8. **Points:**  A container (`<div class="points">`) for displaying the player's score and remaining lives.
9. **Crosshair:** A hidden (`<div class="crosshair">`) element for displaying the player's aiming cursor.
10. **Game Board:** A container (`<div class="board">`) that serves as the game area.
11. **Start Message:** A clickable message (`<div id="start" class="message">`) that triggers the game start when clicked.

### styles.css

**Purpose:** This file defines the styles and visual appearance of the game elements.

**Key Styles:**

1. **Body Styles:**
   - Sets the background to an image of a post-apocalyptic scene.
   - Disables scrolling (`overflow: hidden`).
2. **Font:**
   - Uses the "Press Start 2P" font for a retro game aesthetic.
3. **Author and Points Styles:**
   - Centers the author's name and score/lives display.
   - Applies white text and a shadow effect.
4. **Crosshair Styles:**
   - Creates a circle-shaped crosshair with a red background.
   - Positions the crosshair in the center of the screen.
5. **Game Board Styles:**
   - Covers the entire screen.
   - Center-aligns the "Start" message at the bottom.
6. **Zombie Styles:**
   - Defines the appearance of zombies, including a walking animation.
   - Styles the zombie's image, size, position, and animation transitions.
7. **Responsive Styles:**
   - Adjusts font sizes and element sizes for different screen sizes using media queries to ensure optimal visibility on various devices.

### script.js

**Purpose:** This file contains the JavaScript logic for the game, including:

**Game Variables:**

1. **`points`:** Stores the player's current score, initialized to 0.
2. **`hp`:** Stores the player's remaining lives, initialized to 3.

**Functions:**

1. **`updatePoints()`:** Updates the score and lives displayed on the screen.
2. **`escapedZombie()`:** Decrements player lives when a zombie escapes the screen.
3. **`aim(e)`:** Updates the crosshair position based on the mouse cursor position.
4. **`kill(e)`:** Handles zombie killing events, updating the score and removing the zombie from the screen.
5. **`miss(e)`:** Handles missed shots, decreasing the score.
6. **`Zombie` Class:**
   - **Constructor:** Initializes zombie properties like position, size, and speed.
   - **`animate(z)`:** Creates and returns an interval to animate the zombie's movement.
   - **`spawn()`:** Creates a new zombie element, adds it to the board, and applies animation and event listeners.
7. **`spawnZombies()`:** Spawns new zombies at random intervals and manages game over conditions.
8. **`clearBoard()`:** Clears the game board, disables further interactions, and displays the game over message.
9. **`startGame(e)`:** Initializes the game by removing the start button, enabling game controls, and starting the zombie spawning process.

**Event Listeners:**

1. **`startGame()`:** Attached to the "Start" message to trigger the game start.
2. **`aim()`:** Attached to the `body` to track mouse movements and update crosshair position.
3. **`mousedown()`:** Prevents default behavior of mouse clicks to prevent unexpected actions.
4. **`miss()`:** Attached to the game board to detect missed shots.
5. **`kill()`:** Attached to each zombie element to handle zombie destruction.

**Overall Flow:**

1. **Initialization:**  The game starts with a "Start" message and an initial score and lives display.
2. **Start:** When the "Start" message is clicked, the game begins, spawning zombies at random intervals.
3. **Gameplay:** The player aims with the crosshair and clicks to shoot zombies.
4. **Zombie Killing:** Clicking a zombie removes it from the screen and increases the player's score.
5. **Zombie Escape:** If a zombie reaches the left edge of the screen, the player loses a life.
6. **Game Over:** When the player runs out of lives, the game ends, the board is cleared, and a "You lose!" message appears.

This documentation provides a comprehensive understanding of the "Zombie Attack" game's implementation, covering the HTML structure, CSS styling, and JavaScript logic.
