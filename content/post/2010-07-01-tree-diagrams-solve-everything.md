+++
title = "Tree diagrams solve everything"
slug = "2010-07-01-tree-diagrams-solve-everything"
published = 2010-07-01T13:21:00+01:00
author = "Douglas Ashton"
tags = [ "probability",]
aliases = ["/2010/07/tree-diagrams-solve-everything.html"]
+++
Just a quick one. I saw this post, [When intuition and math probably
look
wrong](http://sciencenews.org/view/generic/id/60598/title/When_intuition_and_math_probably_look_wrong),
via Ben Goldacre's [mini blog](http://delicious.com/bengoldacre). The
problem is set as follows:  

> I have two children, one of whom is a son born on a Tuesday. What is
> the probability that I have two boys?

Intuition tells you the answer is 1/2, mathematicians tell you it's
something else. I'll leave the answer until the end of the post in case
you want to run off and solve it first. It's essentially a fancier
version of the [Monty Hall
problem](http://en.wikipedia.org/wiki/Monty_Hall_problem).  
<span id="more"></span>The [Science News](http://sciencenews.org/)
article deals with this just fine so I don't really want to expand on
it. The only thing I wasn't too impressed with was their grid
visualisation. It didn't really make anything any clearer for me. No,
the only way to go is a good old fashioned tree diagram. So I thought
I'd just show how I solve pretty much all probability problems, as
techniques go it's slow but you always get the right answer - no
intuition required.  
  
The basic approach is to follow all possible scenarios and split the
probabilities of all the events. From the information here we split
three events. A child is born, it is either a girl (1/2) or a boy (1/2).
We care if the boy was born on a Tuesday or not so we'll add this as a
possibility. I like to put everything over a common denominator so we
have: girl (7/14), boy not Tuesday (6/14), boy Tuesday (1/14). On the
diagram this goes  

[![](/images/thumbnails/2010-07-01-tree-diagrams-solve-everything-tree1.png)](/images/2010-07-01-tree-diagrams-solve-everything-tree1.png)

Now we have another child, everything's independent so we have the same
possibilities on each branch. We just multiply through the probabilities
and keep the common denominator to get  

[![](/images/thumbnails/2010-07-01-tree-diagrams-solve-everything-tree3.png)](/images/2010-07-01-tree-diagrams-solve-everything-tree3.png)

We can use this to solve all girl, boy, boy on Tuesday related
questions. Given one child is a boy born on a Tuesday we select all
final states that satisfy this (highlighted in red). If you add up their
numbers this is a total of 27 out of the 196. Of these 27 where there is
one boy born on a Tuesday we count the ones where the other child is a
boy (b or t). This comes to a total 13 of the final states.  
  
And that's it. Of the 27 possibilities where one child is a boy born on
Tuesday, 13 have another boy, so the answer is **13/27**.  
  
Note, if the question had been phrased "My *first* child was a boy born
on Tuesday..." then you see we follow down the bottom branch and the
problem returns to the intuitive answer. If this post seems a bit too
elementary then I apologise. It just seems like no one ever mentions
tree diagrams as a technique, preferring instead to make the problem
seem really hard by banging on about Bayes' theorem and conditional
probabilities and so on. They're all in there, just hidden out of
view.  
  
I like tree diagrams because setting one up is pretty mechanical and
solving the problem just becomes a question of event counting. You
certainly don't need to worry about Bayes' theorem or anything fancy
sounding. And once again, *no intuition required*.  
  
Which is good because my intuition is crap.
