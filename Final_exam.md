# Final Exam

# Part 1: Fundamentals

## Supporting technology

### Version control

Version control is system that manages changes to software. It provides many useful features such as storing the change history of files over a long period, branching and merging, and the ability to trace changes. All our projects this semester used a popular version control system, git. Git allowed use to track our changes and in combination with github we were able to host our repositories and view each others code. I have unfortunately only recently decided to used git from the command line. I was inspired to do so after reading *The Pragmatic Programmer*. I had been previously using git UI's and had been very confused by some of them. I found the git command generally easy to understand and more universal instead of a different UI for any new environment. And if I may quote *The Pragmatic Programmer* "A benefit of GUIs is WYSIWYG - what you see is what you get. The disadvantage is WYSIAYG - what you see is all you get." I would agree with this sentiment and understand the power a command line tool can have over a UI.

### Automation with GitHub Actions and Workflows

GitHub Actions and Workflows is an automation tool that runs commands and configurations based on a yml file. It interfaces well with github and can run commands based on many different GitHub events. For our projects this semester we used GitHub Actions and Workflows to set up continuous integration for our godot projects. The workflow we set up in this class created a build of our project and deployed it to Github pages. I personally appreciate the chance to learn more about this tool. The software engineering course I am taking encourages automated acceptance testing and GitHub Actions seems like to perfect tool to automate testing and reject or accept commits and merges based on the results.

## Godot Engine specifics

### Signals

Signals in Godot provide a good method to decouple game objects. The allow nodes to send messages that other nodes can listen and respond to. They also provide a much better alternative to checking for state changes in other nodes. Instead of checking for a change in another node every frame that node and just emit a signal. I used signals fairly extensively during my work with Godot. A lot of nodes have useful built in signals for example buttons with a pressed signal that is emitted every time the button is clicked. I also created some custom signals one example I made a game over signal for my final project that was emitted when the player lost all their lives. I used this signal to trigger the game over screen to appear.

### `_process` or `_physics_process`

In Godot `_process` is a built in method that is called every time a frame is drawn. `_physics_process` is slightly different in that is called for every physics step. `_physics_process` is better for process that need to happen before each physics step. This is why when working on physics based player movement it is better to do this in the `_physics_process` method. When originally programming my character controller for Project 2 I put my movement code inside `_process` and encountered some weird bugs. This was fixed by moving my code to `_physics_process`.

# Part 2: Project Reflection

My goal for the final project was to implementing a classic successful arcade game. I chose space invaders and worked to recreate it’s features and design in Godot. This was done keeping intellectual property restrictions in mind so using copyrighted materials from space invaders was off limits.

### What Went Right

### What Went Wrong