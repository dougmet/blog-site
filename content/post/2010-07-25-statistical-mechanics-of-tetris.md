+++
title = "Statistical mechanics of tetris"
slug = "2010-07-25-statistical-mechanics-of-tetris"
published = 2010-07-25T01:59:00+01:00
author = "Douglas Ashton"
tags = [ "stat-mech",]
aliases = ["/2010/07/statistical-mechanics-of-tetris.html"]
+++
I'm finding that I'm becoming increasingly fascinated by shape. It seems
such a simple thing yet scratch the surface only a little and the
complexity comes pouring out. Take simple tiling problems; I can tile my
floor with squares or regular hexagons, but not regular octagons -
they'll always leave annoying gaps. From a statistical mechanics point
of view those gaps are very important, little sources of entropy that
you can't get rid of. In three dimensions understanding the [packing of
tetrahedra](http://www.nytimes.com/2010/01/05/science/05tetr.html) has
proved [no simple
task](http://www.engin.umich.edu/dept/che/research/glotzer/). But that's
a story for another day.  
  
So it came as no surprise that I was very taken with [Lev
Gelb's](http://www.chemistry.wustl.edu/%7Egelb/) talk on polyominoes at
the Brno conference. Polyominoes are connected shapes on a two
dimensional lattice. A monomino is a square, a domino you know.
Tetrominoes are made of four squares and are exactly like the pieces
from Tetris. Assuming that they're stuck in the plane (so you can't flip
them over) there are 7 tetrominoes.  
  

[![](/images/thumbnails/2010-07-25-statistical-mechanics-of-tetris-tetrominoes.png)](/images/2010-07-25-statistical-mechanics-of-tetris-tetrominoes.png)

  
<span id="more"></span>All of these can individually tile space so it is
possible to have no gaps. Shapes such as S and Z, L and J are chiral
opposites. There are some subtle differences in the rotational entropy
as well. O has a single rotational state. I, S and Z have 2, the rest
have 4.  
  
Many have studied these sorts of shapes before. Lev's group are looking
at it in the context of nanoparticles adsorbing to a surface. What
they've done is to run really efficient simulations in an open system
(grand canonical). They fix a chemical potential - this is kind of like
fixing the pressure - and then measure what how many particles are on
the surface.  
  
At low pressure the density you get is the same for all shapes, it's too
low to notice the difference. At high pressures you start to see the
difference. As you may expect, with their simpler shape, the squares are
the easiest to pack in. For the same pressure you get the highest
density of all the shapes. The pictures below ([from the
paper](http://pubs.acs.org/doi/abs/10.1021/la900196b)) show what the
high density configurations look like.  
  

[![](/images/thumbnails/2010-07-25-statistical-mechanics-of-tetris-high_density.png)](/images/2010-07-25-statistical-mechanics-of-tetris-high_density.png)

You can see there's quite a bit of ordering. But is it long range
ordering, i.e. a *phase transition*? The quick answer is no. The
correlations build up, and in interesting ways unique to each shape, but
there are no discontinuities that could be considered a proper phase
transition. It would seem you need more than four monomers for that. How
many more? Well just one apparently! With pentominoes you do see phase
transitions with some shapes.  
  
On a related note you can ask, how long must the rods be before they
will form a liquid crystal? For that they must be seven squares long
(according to [JCP **128**,
214902](http://dx.doi.org/10.1063/1.2927877)).  
  
Finally they move on to mixtures. There a lots of combinations you can
do. A nice shot is the full mixture with all the shapes in.  
  

[![](/images/thumbnails/2010-07-25-statistical-mechanics-of-tetris-all_tetris.png)](/images/2010-07-25-statistical-mechanics-of-tetris-all_tetris.png)

It seems that the different shapes mix quite happily, they don't split
into domains of each different type. What does all this mean for tetris?
Um, well it looks to me that if they mix pretty well then it should be
possible to play a perfect game! OK, I'm clutching at straws a bit
there.  
  
I could geek out about shapes all day. See the detailed paper (open
access) at [Langmuir, <span class="citation_year">2009</span>, **<span
class="citation_volume">25</span>** (12), pp
6702–6716](http://pubs.acs.org/doi/abs/10.1021/la900196b). Or Lev's
[group pages](http://www.chemistry.wustl.edu/%7Egelb/tetrominoes.html)
for some nice animations.
