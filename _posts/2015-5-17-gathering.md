---
layout: post
title: Gathering
comments: true
---
The core gameplay in my game is going to revolve around exploring the world and gathering resources. To me this means two things: 
<br/><br/>
<b>
1.	The most basic action of pushing the gather button should be satisfying
<br/>
2.	Gathering should never feel like a chore
</b>
<br/>
<br/>
The latter point is an issue of balancing resource costs and designing areas that make gathering challenging and interesting. When I start focusing on level layout I’ll delve more deeply into that topic but for today I’m going to be focusing on the first objective. 
<br/><br/>
Once I had the player moving around the environment the very next thing I did was create entities that the player could walk up to, press a key to interact with, and destroy the entity while increasing the resource count by a fixed amount. At the most fundamental level this is what the gathering system is intended to do, however this on its own sucks. The player’s only feedback from the game to let them know they made a difference is a box disappearing. I needed to give the action some character.
<br/>
<table style="border:1px">
  <tr>
    <td>
      <img src="{{ site.baseurl }}/images/gathering_noshake.gif" alt="No shake" style="width: 400px;"/>
    </td>
  </tr>
  <tr>
    <td>
      Bleh...
    </td>
  </tr>
</table>

I started off fiddling around with brxr.net’s explosion sound generator until I found one I was happy with and made it play when the node was destroyed. I highly recommend getting placeholder sounds working early in development as it changes your perspective on mechanics immensely. Something dull and lifeless can be completely transformed with just some simple sounds. 
<br/><br/>
Next up was causing a little screen shake to go along with the noise. I decided to try for a subtle shake as this is an action that will be happening fairly frequently and I don’t want the player’s actively noticing it. I want the shake to add a little extra weight and feel to the gathering action without distracting the player.
<br/>

<table style="border:1px">
  <tr>
    <td>
      <img src="{{ site.baseurl }}/images/gathering_shake.gif" alt="No shake" style="width: 400px;"/>
    </td>
  </tr>
  <tr>
    <td>
      Getting better...
    </td>
  </tr>
</table>


At this point the action was pretty satisfying and I could probably have just put some sort of smoke puff over the node and called it a day. While that may have worked I decided to instead make the disappearing animation part of gameplay. Instead of simply increasing the resource count when pushing the button I made the node explode in a shower of collectables. Collectables are, after all a staple of the platformer genre - and with good reason. Simply put, it is fun to run over stuff to pick it up. I changed the gather action to spawn a semi random number of resource objects and fire them out. Once they stop moving (which I signify with a glowing border) the player is able to pick them up.  
<br/>
Put all these feedback features together and this is the result:

<iframe width="640" height="390" src="https://www.youtube.com/embed/L-OcOxOHelM" frameborder="0" allowfullscreen></iframe>
