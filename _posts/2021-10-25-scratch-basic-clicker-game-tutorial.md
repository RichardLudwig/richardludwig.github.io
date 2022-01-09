---
layout: post
title:  "Scratch Basic Clicker Game Tutorial"
author: richard
categories: [ Tutorial ]
video: assets/videos/thumbnails/scratch-clicker-game-thumbnail.mov
tags: [recent, tutorials]
pitch: "Create a basic clicker game with Scratch"
permalink: "/blog/scratch-basic-clicker-game-tutorial"
---

Scratch is a programming language children use to develop programs using block coding.

Below is a tutorial you may use to create a basic clicker game using Scratch 3. Choose a sprite and implement the blocks below to create a clicker game.
<hr>
<br>
<br>
Once you have chosen a sprite, set the score to 0 every time the green flag is clicked (and the game is restarted).
<br>
<img src="../assets/images/scratch/clicker-game/clicker-game-init-score.png" alt="scratch clicker game init score setup">
<br>
<br>
Create a function that executes every time the sprite is clicked. The function below does the following:
<ul>
    <li>Implements a "Pop" sound</li>
    <li>Sets the sprite size to 115% of its normal size</li>
    <li>Increments the score by 1</li>
    <li>Waits 0.1 seconds before returning the sprite size to 100% of its normal size.</li>
</ul>
<br>
<img src="../assets/images/scratch/clicker-game/clicker-game-count-function.png" alt="scratch clicker game count function">
<br>
<br>
Below is the full program code, which you will implement on a sprite of your choice. You can copy the code here or download it from <a href="https://github.com/RichardLudwig/ScratchDemos/blob/main/BasicClickerGame.sb3" target="_blank">GitHub</a>.
<br>
<br>
<img src="../assets/images/scratch/clicker-game/clicker-game-full-program.png" alt="full scratch clicker game code"/>