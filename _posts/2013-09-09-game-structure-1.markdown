---
layout: post
title:  "[E] Game Structure - Part 1: Main Loop"
date:   2013-09-09 14:30:00
tags: ['update', 'game development', 'article']
cat: 'article'
description: "First article of game structure, learn how a game works."
---

In this article, I will introduce the most basic thing of a game structure, game loop. For the first part, only the main loop is mentioned. Let's take a look at below diagram.
<a href="http://i.imgur.com/kXhNsna.png" target="_blank"><img src="http://i.imgur.com/kXhNsna.png" alt="Main Loop"/></a>
A game is a program with infinite loop, start when user run the game itself and stop when user inputs the *EXIT COMMAND*. As you see on the above diagram, there are three main tasks in the main loop: **INPUT**, **SCENE LOOP** and **RENDER**.

Let's say that when you start the game, that is the **Initialize phase** which collects all data and starts the main loop. Inside the main loop, the program itself continually processes user input, then manages game logic and objects, finally it will render and draw on the screen.
<a href="http://i.imgur.com/bvTFFaX.png" target="_blank"><img src="http://i.imgur.com/bvTFFaX.png" alt="Main Loop"/></a>
Inside the **SCENE LOOP**, there are objects controller and logic controller which controls the game flow. For those two controllers, we can call them the **STATES MANAGER**. The logic itself will controls which scene we are in, which level we are playing and all other objects like NPC, Menu and even Player status. For the above diagram, it is the simple structure of states manager, or scene manager.

Now let's turn to a simple example of the main loop. In Initialize phase, the program will load the data and push the Title Scene into Scene Manager. Inside the Scene Manager's logic, it decides that there are three commands *New Game*, *Load Game* and *Exit Game* and controls an object that will handle the input command(s). The render will take data from Scene Manager and draw them on the screen, in this case, three texts of those above commands are drawn. Player will input their command in Input phase and push it into Scene Manager's logic and repeat the loop over and over again.

In coding task, we have this below pseudo-code which simulates the main loop:
{% highlight ruby %}
initialize()
begin
  input = get_input()
  scene_update(input)
  render()
end until input == "exit"
finalize()
exit()
{% endhighlight %}
Beside those above tasks, there are some other things like FPS Calculation, Cache Manager,... We will talk about them in later parts of the series.

In conclusion, a game is a infinite loop. Though each game has a different logic, its core (main loop) is still the same.
