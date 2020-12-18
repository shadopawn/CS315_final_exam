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

My goal for the final project was to implementing a classic successful arcade game. I chose Space Invaders and worked to recreate it’s features and design in Godot. This was done keeping intellectual property restrictions in mind so using copyrighted materials from space invaders was off limits. I decided to call my game Fake Invaders.

## What Went Right

### 1) The resemblance to the goal is clear

My original goal was to create a recreation of the original Space Invaders and I would say I succeeded in doing so. My end result clearly resembles the game without using any of it's copyrighted materials. The game play is also very close to my target. When I showed my project to my parents they both immediately recognized it as Space Invaders I had to correct them of course because it was actually Fake Invaders. 

### 2) Good grasp of the tools and workflow

After working through the first few projects this semester I felt I had gotten a decent grasp of way Godot worked. Things like signals which had originally confused me I was using readily. I had also gotten better with git and setting up continuous integration. My first time setting up continuous integration I had several issues, but with that sorted out setting it up for subsequent projects was easy. I felt more confident with my tools going into the final project, and indeed I was no longer in tutorial hell every time I went to implement a new feature. The majority of the final project I was able to come up with my own solutions instead of having to search for them.

### 3) Destructible cover appearance

One of the most challenging features of Space Invaders that I had planned to implement was the destructible cover. Although I am not happy with the way I implemented destructible cover in my game I am happy with the way it looks. It seems to simulate the pixilated destruction seen in Space invaders well. Bullets and bombs leave blown out holes in the cover and this allows the player to shoot through his cover at the invaders. It also allows the invaders to slowly destroy the players cover forcing the player to move.

## What Went Wrong

### 1) Destructible cover implementation

I would have to agree with the feedback given on my final project. I got destructible cover to work but in the process I shoehorned tools into positions they shouldn't really be in. I got it to work by creating a grid of pixels with colliders. I wrote a recursive algorithm that checked the surrounding pixels and did a random check to see if it was destroyed before calling this function on its surrounding pixels. A better approach as my final project feedback recommended would have been to copy how games Worms or Scorched Earth make it work. This approach would  model or inspect the pixels that make up the terrain, and then keep track of a mask to eliminate them. I wish I had found this approach while doing my research.

### 2) Lack of polish

My final product could really stand to benefit from some polish. There are many things I wish I had cleaned up or improve at the top of that list would be my destructible cover implementation. Other than that that I would have like to add feed back when the player loses a life, as it currently stands the only indication of a life lost in the counter in the bottom left. There was another bug where bullets would stay on the screen when scenes transitioned. These were absolutely fixable problems that could have been fixed with some more effort.

### 3) Missing features

I did not manage to fully recreate the features of space invaders. My version only only has 1 enemy type where as the real game has 4. I also only recreated a single wave of Space Invaders the real game respawns the invaders and increases the difficulty. I am also missing the mystery ship. Because of my lack of invader variety my point system is comparatively flat. The original game gave different point amounts based on the invader killed, my version is lacking that. Adding these features would have flushed out my game and created a more complete Fake Invaders.