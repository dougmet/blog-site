+++
title = "An unintuitive probability problem"
slug = "2009-11-29-an-unintuitive-probability-problem"
published = 2009-11-29T12:53:00.027000Z
author = "Douglas Ashton"
tags = [ "probability", "stat-mech",]
aliases = ["/2009/11/unintuitive-probability-problem.html"]
+++
Probability can do strange things to your mind. This week I had a
probability problem where every time I tried to use intuition to solve
it I ended up going completely wrong. I thought I'd share it as I think
it's interesting.  
  
Consider a one dimensional random walk. At each time step my walker will
go left with probability
![](/images/2009-11-29-an-unintuitive-probability-problem-pl.png), and
right with probability
![](/images/2009-11-29-an-unintuitive-probability-problem-pr.png). It
stays where it is with probability
![](/images/2009-11-29-an-unintuitive-probability-problem-oneminplpr.png).
Furthermore these probabilities are dependent on the walker's position
in space, so it's really
![](/images/2009-11-29-an-unintuitive-probability-problem-plx.png) and
![](/images/2009-11-29-an-unintuitive-probability-problem-prx.png).
I'm imagining I'm on a finite line of length, L, although it doesn't
matter too much.  
  
Now if
![](/images/2009-11-29-an-unintuitive-probability-problem-xlconst.png),
then we just have a normal random walker. In my problem I have the
following setup:
![](/images/2009-11-29-an-unintuitive-probability-problem-lmtx.png)
but
![](/images/2009-11-29-an-unintuitive-probability-problem-plxp1r.png).
What does this mean? At any given point, x, my walker is more likely to
go left than right. If it does go left it will come back with the same
rate (although it's more likely to go left again).  
  
  

[![](/images/thumbnails/2009-11-29-an-unintuitive-probability-problem-rw.png)](/images/2009-11-29-an-unintuitive-probability-problem-rw.png)

  
  
So here's the question: If I leave this for a really long time, what is
the equilibrium probability distribution for the walkers position,
![](/images/2009-11-29-an-unintuitive-probability-problem-Px.png)?  
  
<span id="more"></span>  
  
<span style="font-weight: bold;">Intuitive answer (1)</span>  
At any given site the chances are you are more likely to go left than
right. Therefore, this introduces a bias to go left. The walker is more
likely to be on the left hand side of the line after a long time.  
  
<span style="font-weight: bold;">Intuitive answer (2)</span>  
Because the transition rates are much faster on the left than the right,
if the walker happens to go to the left it will much more quickly
return. If the walker happens to go right then it's going to take a long
time to return. Therefore you're more likely to find it on the right.  
  
<span style="font-weight: bold;">The correct answer</span>  
Well it's a little of both. The correct answer is that there is equal
probability of finding the walker absolutely anywhere. The reason for
this does not come from intuition. At equilibrium we have the condition
that there must be no probability "current". That is to say that the
probability of being found at a given site must not change in time. This
can be expressed mathematically by the master equation (if you don't
want to do the maths we'll meet back at the end):  
  
[![](/images/thumbnails/2009-11-29-an-unintuitive-probability-problem-Master1.png)](/images/2009-11-29-an-unintuitive-probability-problem-Master1.png)  
  
You have to think of the ps as rates for this to work. In our case we
have that the rate for going left or right is the same as making the
reverse move. The master equation then reduces to  
  
[![](/images/thumbnails/2009-11-29-an-unintuitive-probability-problem-master2-fix.png)](/images/2009-11-29-an-unintuitive-probability-problem-master2-fix.png)  
  
and the solution is that
![](/images/2009-11-29-an-unintuitive-probability-problem-Pxconst.png).
So how does this sit with our intuitive ideas above? Well perhaps it's
best to look at a trace of such a random walk. In the below example we
have that
![](/images/2009-11-29-an-unintuitive-probability-problem-pxsim.png).
What happens is that the walker does indeed move quickly at small x and
slowly at large x (as in intuitive answer 2), but the slowness at large
x seems to reflect the walker away. When it does manage to penetrate the
barrier it takes a long time to come back. The average behaviour is that
every site, x, is occupied for the same amount of time.  
  
[![](/images/thumbnails/2009-11-29-an-unintuitive-probability-problem-rwsimulation.png)](/images/2009-11-29-an-unintuitive-probability-problem-rwsimulation.png)  
  
So there it is. Never trust your instincts when it comes to probability,
well not mine at least.  
  
Oh, and on a separate note, putting maths into a blog post is a bloody
nightmare - any ideas?  
EDIT: Some maths fixed...
