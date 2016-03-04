---
title: Dev Bootcamp - my dive into the world of development
date: 2016-01-22
tags: dev bootcamp
---

I recently graduated from Dev Bootcamp, a 19 week intensive programming school for aspiring web developers. I wanted to take some time to describe my journey and experience through the program. A little bit about myself, I graduated with a degree in Aerospace Engineering and shortly after went to work for Epic, a Healthcare Software company. I worked primarily with servers, operating systems, and databases. While there, I found I loved the idea of developing software and decided to join Dev Bootcamp.

Some of the other schools I considered were App Academy and Fullstack Academy. App Academy was free but required you to pay a certain percantage of your first year starting salary. What was unique about Dev Bootcamp was the emphasis on team dynamics and self-improvement. This, along with the location being in Chicago, was the main factor for me selecting Dev Bootcamp.

Going in, I had already heard some great things about the program from some other friends. I was excited to join the curriculum and was curious about what I was going to learn. Others had told me the curriculum was very focused on Ruby on Rails, and I was a bit dissapointed by that going into the program. I would later find that the program had a heavy focus on learning Ruby as a language first before diving into the specifics of frameworks such as Sinatra or Ruby on Rails.

## Phase 0 experience

Phase 0 was the first part of the curriculum and featured and online part that could be worked on remotely. I found that phase 0 was a good introduction to the world of coding and its greatest benefits to me were repetition. We also worked on weekly pair programming assignments over Skype which introduced me to the world of pair programming. I found the assignments to be a bit easy but I was able to make things more difficult for myself on my own. The curriculum was quoted to take around 25 hours a week and I found that I spent closer to 12 on the core material each week.

Over the course of the 9 weeks we covered basic ruby syntax, basic object oriented javascript, and SQL. One of the primary benefits for me was the heavy focus on reflection. As part of the assignments, we wrote weekly blog posts on the material as well as refactored code that we wrote for various assignments. Below is a short snippet of the quality of code I was producing at the end of the 9 weeks. At this point we were not following Test-Driven Development principles nor did we have knowledge of Model-View-Controller design.

<pre class="blogpost"><code>
# class to validate a credit card number in ruby
class CreditCard
  def initialize(credit_card)
    len = int_to_a(credit_card).length
    raise ArgumentError.new("Please enter a valid credit card number") if len!=16
    @credit_card = credit_card
  end

  def check_card
    array =int_to_a(@credit_card)
    last = array.pop
    array.map! {|x| x*2}.push(last) # Double every value but the last
    sum = array.map{|x| (x>=10 ? int_to_a(x).reduce(:+) : x)}.reduce(:+)
    return sum % 10 == 0
  end

  def int_to_a(integer)
    # Splits integer into an array of integer values. Ex: 1234 => [1,2,3,4]
    integer.to_s.split("").map {|x| x.to_i}
  end
end
</code></pre>

## On-site experience

The actual on-site part of the class was 9 weeks long. It was split into three phases that were three weeks each. The hours were quoted to be 60-80 hours a week. I found that I spent closer to 40 on the core materials. There were plenty of stretch materials to work on and other resources to keep me busy though.

We learned Ruby, Javascript, Sinatra, Ruby on Rails, Rspec, testing frameworks, javascript frameworks. The main thing that we gained out of the program was a coder's mindset and the ability to pick up new things quickly. I liked the attention to building up our knowledge incrementally. We dove deeply in the underlying technologies rather than just learning a framework. This helped give us an understanding of when you might choose to use a framework and what the tradeoffs are.

As part of the 8-day capstone project, I worked on turn-based strategy game in JavaScript. By this point, we had an understanding of both Test-Driven Development and separation of concerns. Below is a sample of code from that game as part of the code that implements the Artificial intelligence for the computer opponent. At this point, the design of my classes are more meaningful and they delegate responsibilities to other classes. There is also the use of Prototypical Inheritence for gaining behavior of other related classes.

<pre class="blogpost"><code>
// Computer AI implemented using a Finite State Machine with embedded rules

ComputerPlayer.prototype = new Player();
ComputerPlayer.prototype.constructor = ComputerPlayer;

function ComputerPlayer(army) {
  this.army = army;
  this.active = false;  // boolean to be used to determine which players turn it is
  this.mode = null;
  this.battle = null;
};

ComputerPlayer.prototype.update = function(map, myTurn) {
  this.army.update(map);
};


ComputerPlayer.prototype.handleComputerMove = function() {
  return this.mode.handleComputerMove();
};

// Computer Modes - Aggressive, Defensive, Patrol
ComputerPlayer.prototype.updateMode = function(mode) {
  switch(mode) {
    case "aggressive":
      this.mode = new AggressiveMode(this.battle);
      break;
    case "defensive":
      this.mode = new DefensiveMode(this.battle);
      break;
    case "patrol":
      this.mode = new PatrolMode(this.battle);
      break;
    default:
      this.mode = new DefaultMode(this.battle);
      break;
  }
};
</code></pre>

## Would I recommend


![Dev Bootcamp](images/blog/devbootcamp.png)

I had a great experience at Dev Bootcamp. The skills I gained coming out of the course were much different than what I had expected, but arguably were much more valuable. The ability to learn things on my own and become a much more empathetic team member seems to be a very valuable skill in the tech industry today.

I would recommend Dev Bootcamp to a friend. In addition to all the skills I gained, the community is a great thing to be a part of. It helped keep me accountable for finishing all of my work in addition to producing work of my highest quality. The community is also very supportive throughout the process of searching for a job.

In the future, I hope to continue my learning. I plan on developing my skills further in Ruby on Rails and Javascript. In addition, I intend to learn other languages in more detail (such as Python and C++) as well as take a deeper dive into some of the bigger topics in Computer Science today such as Machine Learning and Computer Vision. I also strive to continually write better code.
