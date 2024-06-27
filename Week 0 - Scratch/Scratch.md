## Scratch
---
*   _Scratch_ is a visual programming language developed by MIT.
*   Scratch utilizes the same essential coding building blocks that we covered earlier in this lecture.
*   Scratch is a great way to get into computer programming because it allows you to play with these building blocks in a visual manner, not having to be concerned about the syntax of curly braces, semicolons, parentheses, and the like.
*   Scratch `IDE` (integrated development environment) looks like the following:
![scratch interface](cs50Week0Slide162.png "scratch interface")

Notice that on the left, there are _building blocks_ that you can use in your programming. To the immediate right of the building blocks, there is the area to which you can drag blocks to build a program. To the right of that, you see the _stage_ where a cat stands. The stage is where your programming comes to life.

*   Scratch operates on a coordinate system as follows:

![scratch coordinate system](cs50Week0Slide167.png "scratch coordinate system")

Notice that the center of the stage is at coordinate (0,0). Right now, the cat’s position is at that same position.


## Hello World
---
*   To begin, drag the “when green flag clicked” building block to the programming area. Then, drag the `say` building block to the programming area and attach it to the previous block.
    
        when green flag clicked
        say [hello, world]
    
    Notice that when you click the green flag now, on the stage, the cat says, “hello world.”
    
*   This illustrates quite well what we were discussing earlier regarding programming:
![scratch with black box](cs50Week0Slide172.png "scratch with black box")

Notice that the input `hello world` is passed to the function `say`, and the _side effect_ of that function running is the cat saying `hello world`.


## Hello, You
---
*   We can make your program more interactive by having the cat say `hello` to someone specific. Modify your program as below:
    
        when green flag clicked
        ask [What's your name?] and wait
        say (join [hello,] (answer))
    
    Notice that when the green flag is clicked, the function `ask` is run. The program prompts you, the user, `What's your name?` It then stores that name in the _variable_ called `answer`. The program then passes `answer` to a special function called `join`, which combines two strings of text `hello`, and whatever name was provided. These collectively are passed to the `say` function. The cat says, `Hello,` and a name. Your program is now interactive.
    
*   Quite similarly, we can modify our program as follows:
    
        when green flag clicked
        ask [What's your name?] and wait
        speak (join [hello,] (answer))
    
    Notice that this program, when the green flag is clicked, passes the same variable, joined with `hello`, to a function called `speak`.

## Meow and Abstraction
---
*   Along with pseudocoding, _abstraction_ is an essential skill and concept within computer programming.
*   Abstraction is the act of simplifying a problem into smaller and smaller problems.
*   For example, if you were hosting a huge dinner for your friends, the _problem_ of having to cook the entire meal could be quite overwhelming! However, if you break down the task of cooking the meal into smaller and smaller tasks (or problems), the big task of creating this delicious meal might feel less challenging.
*   In programming, and even within Scratch, we can see abstraction in action. In your programming area, program as follows:
    
        when green flag clicked
        play sound (Meow v) until done
        wait (1) seconds
        play sound (Meow v) until done
        wait (1) seconds
        play sound (Meow v) until done
    Notice that you are doing the same thing over and over again. Indeed, if you see yourself repeatedly coding the same statements, it’s likely the case that you could program more artfully – abstracting away this repetitive code.
    
*   You can modify your code as follows:
    
        when green flag clicked
        repeat (3)
        play sound (Meow v) until done
        wait (1) seconds
    
    Notice that the loop does exactly as the previous program did. However, the problem is simplified by abstracting away the repetition to a block that _repeats_ the code for us.
    
*   We can even advance this further by using the `define` block, where you can create your own block (your own function)! Write code as follows:
    
        define meow
        play sound (Meow v) until done
        wait (1) seconds
        
        when green flag clicked
        repeat (3)
        meow
    
    Notice that we are defining our own block called `meow`. The function plays the sound `meow`, then waits one second. Below that, you can see that when the green flag is clicked, our meow function is repeated three times.
    
*   We can even provide a way by which the function can take an input `n` and repeat a number of times:
    
        define meow n times
        repeat (n)
         play sound [meow v] until done
         wait (1) seconds
    
    Notice how `n` is taken from “meow n times.” `n` is passed to the meow function through the `define` block.
    
*   The cat, by the way, we can call a `sprite` – a general term used in game programming for an object or character on the screen with which the player will interact.

## Conditionals
---
*   _conditionals_ are an essential building block of programming, where the program looks to see if a specific condition has been met. If a condition is met, the program does something.
*   To illustrate a conditional, write code as follows:
    
        when green flag clicked
        forever
        if <touching (mouse-pointer v)?> then
        play sound (Meow v) until done
    
    Notice that the `forever` block is utilized such that the `if` block is triggered over and over again, such that it can check continuously if the cat is touching the mouse pointer.
    
*   We can modify our program as follows to integrate video sensing:
    
        when video motion > (50)
        play sound (Meow v) until done
    
*   Remember, programming is often a process of trial and error. If you get frustrated, take time to talk yourself through the problem at hand. What is the specific problem that you are working on right now? What is working? What is not working?

## Oscartime
---
*   We showed you in this lecture a number of Scratch programs to stoke your imagination.
*   _Oscartime_ is one of David’s own Scratch programs – though the music may haunt him because of the number of hours he listened to it while creating this program. Take a few moments to play through the game yourself.
*   Building Oscartime ourselves, we first add the lamp post.
![oscartime interface](cs50Week0Scratch10.png "oscartime interface")

*   Then, write code as follows:
    
        when green flag clicked
        switch costume to (oscar1 v)
        forever
        if <touching (mouse-pointer v)?> then
        switch costume to (oscar2 v)
        else
        switch costume to (oscar1 v)
    
    Notice that moving your mouse over Oscar changes his costume. You can learn more by [exploring these code blocks](https://scratch.mit.edu/projects/565100517).
    
*   Then, modify your code as follow to create a falling piece of trash:
    
        when green flag clicked
        go to x: (pick random (-240) to (240)) y: (180)
        forever
        if <(distance to (floor v)) > (0)> then
        change y by (-3)
    
    Notice that the trash’s position on the y-axis always begins at 180. The x position is randomized. While the trash is above the floor, it goes down 3 pixels at a time. You can learn more by [exploring these code blocks](https://scratch.mit.edu/projects/565117390).
    
*   Next, modify your code as follows to allow for the possibility of dragging trash.
    
        when green flag clicked
        forever
        if <<mouse down?> and <touching (mouse-pointer v) ?>> then
        go to (mouse-pointer v)
        
    
    You can learn more by [exploring these code blocks](https://scratch.mit.edu/projects/565119737).
    
*   Next, we can implement the scoring variables as follows:
    
        when green flag clicked
        forever
        if <touching (Oscar v) ?> then
        change (score) by (1)
        go to x: (pick random (-240) to (240)) y: (180)
    
    You can learn more by [exploring these code blocks](https://scratch.mit.edu/projects/565472267).
*   Go try the full game [Oscartime](https://scratch.mit.edu/projects/277537196).

## Ivy’s Hardest Game
---
*   Moving away from Oscartime to Ivy’s Hardest Game, we can now imagine how to implement movement within our program.
*   Our program has three main components.
*   First, write code as follows:
    
        when green flag clicked
        go to x: (0) y: (0)
        forever
        listen for keyboard
        feel for walls
    
    Notice that when the green flag is clicked, our sprite moves to the center of the stage at coordinates (0,0) and then listens for the keyboard and checks for walls forever.
    
*   Second, add this second group of code blocks:
    
        define listen for keyboard
        if <key (up arrow v) pressed?> then
        change y by (1)
        end
        if <key (down arrow v) pressed?> then
        change y by (-1)
        end
        if <key (right arrow v) pressed?> then
        change x by (1)
        end
        if <key (left arrow v) pressed?> then
        change x by (-1)
        end
    
    Notice how we have created a custom `listen for keyboard` script. For each of our arrow keys on the keyboard, it will move the sprite around the screen.
    
*   Finally, add this group of code blocks:
    
        define feel for walls
        if <touching (left wall v) ?> then
        change x by (1)
        end
        if <touching (right wall v) ?> then
        change x by (-1)
        end
    
    Notice how we also have a custom `feel for walls` script. When a sprite touches a wall, it moves it back to a safe position – preventing it from walking off the screen.
    
*   You can learn more by [exploring these code blocks](https://scratch.mit.edu/projects/326129433).
*   Go try the full game [Ivy’s Hardest Game](https://scratch.mit.edu/projects/326129433/).
*   Scratch allows for many sprites to be on the screen at once.
*   Adding another sprite, add the following code blocks to your program:
    
        when green flag clicked
        go to x: (0) y: (0)
        point in direction (90)
        forever
        if <<touching (left wall v)?> or <touching (right wall v)?>> then
        turn right (180) degrees
        end
        move (1) steps
        end
    
    Notice how the Yale sprite seems to get in the way of the Harvard sprite by moving back and forth. When it bumps into a wall, it turns around until it bumps the wall again. You can learn more by [exploring these code blocks](https://scratch.mit.edu/projects/565127193).
    
*   You can even make a sprite follow another sprite. Adding another sprite, add the following code blocks to your program:
    
        when green flag clicked
        go to (random position v)
        forever
        point towards (Harvard v)
        move (1) steps
    
    Notice how the MIT logo now seems to follow around the Harvard one. You can learn more by [exploring these code blocks](https://scratch.mit.edu/projects/565479840).
    
*   Go try the full game [Ivy’s Hardest Game](https://scratch.mit.edu/projects/565742837).