# Snake Game in Java (GUI with Swing)

A simple graphical implementation of the classic Snake game built in Java using Swing for the user interface. This project demonstrates key Java concepts like classes, event handling (KeyListener), timers, and graphics rendering (JPanel). It's a great way to learn GUI development in Java, which is common in desktop and Android apps.

## Features
- GUI-based: Runs in a resizable window with smooth animation.
- Real-time input: Use WASD or arrow keys for direction changes (immediate response, no Enter needed).
- Automatic snake movement with collision detection (walls and self).
- Growing snake on eating apples (red dots).
- Game over screen with message.
- Fixed speed (adjustable via DELAY constant).

## Requirements
- Java JDK (version 8 or later; tested on OpenJDK 24).
- A code editor like VS Code with the Java Extension Pack, or IntelliJ IDEA.
- No external libraries—uses standard Java Swing.

## Getting Started
1. Clone or download the repository (or save `Snake.java`).
2. Open the file in your editor.

## Building the Game
In the terminal (or VS Code integrated terminal):
```
javac Snake.java
```
This compiles to `Snake.class` (and inner classes).

## Running the Game
```
java Snake
```
- A 300x300 window opens with the snake (green head, white body) and a red apple.
- The snake moves automatically (starts right).
- Use keys to change direction (can't reverse 180°):
  - `W` or Up Arrow: Up
  - `S` or Down Arrow: Down
  - `A` or Left Arrow: Left
  - `D` or Right Arrow: Right
- Eat apples to grow and score (implicit—each apple adds length).
- Game over on hitting walls or self—window shows "Game Over" (close to exit).

## Code Structure
- **Snake.java**: The main file extending JFrame.
  - `initGame()`: Sets up the window, snake positions, apple, and timer.
  - `locateApple()`: Randomly places the apple.
  - `checkApple()`: Grows snake if head hits apple.
  - `move()`: Updates snake positions based on direction.
  - `checkCollision()`: Ends game on wall or self-hit.
  - `actionPerformed()`: Game loop handler (from Timer).
  - `GamePanel`: Inner class for rendering (paints snake and apple).
  - `TAdapter`: Inner class for key events (handles direction changes).

## Customization
- Window size: Change `WIDTH` and `HEIGHT` constants.
- Speed: Modify `DELAY = 140` (lower = faster).
- Dot size: Adjust `DOT_SIZE = 10` (affects grid scale).
- Enhancements:
  - Add score display: Modify `paintComponent` to draw score.
  - Pause/restart: Add key listeners for P/R.
  - Colors: Change `g.setColor` calls in `paintComponent`.

## Troubleshooting
- **No window opens**: Ensure JDK is installed and in PATH (`java --version`).
- **Keys don't work**: Click the window to focus it—Swing requires focus for KeyListener.
- **Compilation errors**: Check for missing imports or syntax—use an IDE for auto-fix.
- **On macOS**: If laggy, run from Terminal.app instead of VS Code.
- **Game over too quick**: Increase DELAY or start with larger window/smaller dots.

## License
This project is open-source under the MIT License. Feel free to fork and modify for your portfolio!

For questions or contributions, open a GitHub issue. Enjoy Java! 🐍
