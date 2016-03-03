---
title: Creating an AI for a turn-based strategy game
date: 2016-01-23
tags: ai
---

<p>I recently worked on a turn-based strategy game named Fantasy Wars. We worked with a group of 4 people and completed the project in 8 days. The game allows you to select one of three different races and battle on one of four different maps.</p>
<p>The game was implemented with Javascript and the Phaser framework. Phaser is a framework that aids in game development by providing things such as a State Manager as well as integration with sprites and Tiled. Given the timelines of the project, it was an ideal fit to use something like Phaser which could accomplish some of the groundwork for us. Particularly useful to us was the Game State manager.</p>
<p>Each turn, players are able to select their units and move a certain distance based on the unit's speed and terrain that it is crossing. Each unit has an attack range, which they can then use to attack enemy units that are within range. In addition, every turn you receive gold based on the number of buildings that you own. You can then choose to build additional units from your barracks.</p>

<h2 class="section-heading">AI Design</h2>

<p>When designing an AI for the game, there were some core tradeoffs that needed to be balanced. Namely - simplicity, effectiveness, and flexibility. I explored the possibility of using a minimax algorithm for the AI. A minimax algorithm works by selecting the move that minimizes loss in the worst case. Due to the complexity involved in implementing a proper minimax along with the time constraints of the project (a couple days), I decided to go with a State-based implementation. This would still allow for flexibility of design while greatly reducing the complexity.</p>

<p>In our game, there was a class for the Player. Note that we used protypical inheritence in Javascript to define our "class" structure. The computer player inherited from this class. In addition, the computer player had a mode. This gave us flexibility to implement the AI in different ways based on different situations. For example, there was both an aggressive and defensive mode. The aggressive mode would favor attacking enemy units and moving to capture their headquarters. The defensive mode would favor gaining terrain bonuses and moving to defend their own headquarters. We were initially planning on completing a campaign mode for the initial release, and this would have allowed the computer to assume drastically different behavior for different missions.</p>

<p>The mode class was used as an Abstract class - meaning we would never instantiate a Mode directly. We would only instantiate AgrressiveMode, DefensiveMode, etc. The mode had a couple core methods - such as determineNextMove or determineNextAttack. It was then up to the AggressiveMode or Defensive Mode to implement these separately to override the default behavior.</p>

<p>This allowed us to favor different logic based on the different game states. The mode could be changed on a fly with a call to an updateMode method. For example, if an enemy got too close to our headquarters, we could change to defensive mode.</p>

<h2 class="section-heading">Future Improvements</h2>

<a href="#">
    <img class="img-responsive" src="img/fantasywars.png" alt="">
</a>
<span class="caption text-muted">A turn based strategy game with strategic elements.</span>

<p>There were many pros for using the state-based design. The main benefits were flexibility (for use with missions) as well as simplicity. Some cons were that some of the moves were not optimal and blending strategies together was more difficult (i.e sending half the units to attack while the other half defend).</p>
<p>In the future, the game could be designed with a minimax algorithm. The individual states could also be made smarter to take in account different situations. We could come up with some method to score the game state, and change tactics based on that score.</p>