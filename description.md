### Walkthrough

1. Import the sys and pygame modules.
	We use the pygame module since it contains the functionality needed to make a game.
	Sys module is meant to exit the game when the player quits.

2. `pygame.init()` initializes background settings that Pygame needs to work properly.

3. We call `pygame.display.set_mode()` to create a display window called screen on which we'll draw all the game's graphical elements.
The tuple `(1200, 800)` defines the dimensions of the game window.
By passing these dimensions to pygame.display.set_mode(), we create a game window 1200 X 800 pixels high.

The screen object is called a **surface**. A __surface__ in pygame is a part of the screen where you display a game element.
Each element in the game, like the aliens or the ship, is a surface.
The surface returned by display.set_mode() represents the entire game window.
When we activate the game's animation loop, this surface is automatically redrawn on every pass through the loop.

The game is controlled by a `while loop` that contains an event loop and code that manages screen updates.
An `event` is an action that the user performs while playing the game, such as pressing a key or moving the mouse. To make the program respond to events, we'll write an __event loop__ to **listen** for an event and perform an appropriate task depending on the kind of event that occurred.
The `for` loop is an event loop.
To access the events detected by pygame, we'll use the `pygame.event.get()` method.
Any keyboard or mouse event will cause the for loop to run. Inside the loop, we'll write a series of `if` statements to detect and respond to specific events.
	for example when the player clicks the game window's close button, a `pygame.QUIT` evebt is detected and we call `sys.exit()` to exit the game.
	
The call to `pygame.display.flip()` at tells pygame to make the most recently drawn screen visible.
In this case it draws an empty screen each time through the `while loop` to erase the old screen so that only the new screen is visible.
When we move the game eleemnts around, `pygame.display.flip()` will continually update the display to show the new position of elements and hide the old ones, creating the illusion of smooth movement.


### Adding the ship image

The best way to start on choosing artwork is using license free artwork from this [site!](https://pixabay.com)
The easiest image file to use is bitmap (.bmp) file because Pygame loads bitmaps by default.
