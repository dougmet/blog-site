+++
title = "The thermodynamic limit"
slug = "2012-04-18-the-thermodynamic-limit"
published = 2012-04-18T16:51:00.001000+01:00
author = "Douglas Ashton"
tags = [ "stat-mech",]
aliases = [
  "/2012/04/thermodynamic-limit.html"
]
math = true
+++
This post has been at the back of mind for a while and written in small,
most likely disjoint pieces. I wanted to think about connecting some of
the more formal side of statistical mechanics to our everyday
intuitions. It's probably a bit half baked but this is a blog not a
journal so I'll just write a follow-up if I think of anything.  
  
I'm often accused of living in a rather idealised world called the
thermodynamic limit.

  
This is completely true.  
  
To see why this is a good thing or a bad thing I should probably say
something about what I think it is. I'll start at the colloquial end and
work up, first let's say that in the thermodynamic limit everything is
in equilibrium.  

#### Nothing ever changes around here

If you put enough stuff in a jar, keep it sealed in a room that stays
the same temperature, and give it enough time then it will eventually
end up in its equilibrium state. One could argue that the real
equilibrium is the grey mush at the end of the universe so clearly I'm
going for some time scale that's enough to let everything in the jar
settle down but not so much that I get bored waiting for it. For atoms
and molecules this usually gives us a window between roughly a
picosecond (10^-12 seconds) and lets say a 100 seconds (I get bored
pretty easily). Once it is in equilibrium the contents of the jar will
stay in the same state forever – or until it gets kicked over. The point
is that in equilibrium nothing changes.  
  
Or does it? To our eyes we may see no change, but the atoms inside the
jar will be wriggling furiously, perhaps even diffusing over great
distances. How could such great change on the small scale be consistent
with eternal boredom on the macroscopic length scale? The answer has two
parts. Firstly, the atoms that make up the world are all frighteningly
similar. So if one diffuses away it will quickly be replaced by an
indistinguishable substitute. The second part motivates the "enough
stuff" part of the previous paragraph.  
  
Listen to a group of people talking and the conversation will ebb and
flow, and sometimes go completely quiet. Sit in a busy cafe and all you
can hear is general noise. A sort of hubbub that you can easily identify
as conversation, maybe you can even get a feel for the mood, but you
can't tell what anyone is saying. In the thermodynamic limit there are
so many atoms that all we can see is a sort of average behaviour. We can
tell what sort of state it is (a liquid, a solid, a magnet – the mood)
but the individuals are lost.  
  
So as we lumber towards a stricter definition of the thermodynamic limit
we should think about what we mean by a state. I've [talked about this
before](/2009/02/entropy.html). In
statistical mechanics there is a huge difference between a 'state' and a
'configuration'. By configuration we mean the exact position (and
sometimes velocity) of every particle in the jar. We're doing this
classically so we won't worry about uncertainty. A state, in the
stat-mech sense, is an ensemble of configurations that share some
macroscopic property. For example their density, or magnetisation, or
crystal structure.  
  
To be the equilibrium state, the corresponding configurations must
satisfy at least one of two criteria (ideally both). Firstly they should
have a low energy compared to the other configurations. If particles
attract they should be close, if dipoles point the same way they should
try to do that. This is intuitive, balls roll down hill, systems like to
lower their potential energy. Secondly there should be a lot of them. An
awful lot of them. This is often referred to as entropy, but really I'm
just saying you need to buy a lot of tickets to guarantee winning a
prize.  

#### A bit more mathematical

This combination of potential energy, U, and entropy, S, is known as the
free energy. You can write it down as:  

$$F = U -TS$$

High temperatures, T, favour high entropy (lots of configurations), low
temperatures favour low energy. In statistical mechanics, unlike normal
mechanics, systems lower their free energy and not just their energy.
The state with the lowest free energy is the equilibrium state. No
exception.  
  
The aim with statistical mechanics is to write down equations that take
interactions on the individual particle level and relate this to the
probability of finding the particles in a particular configuration. In
the mathematical sense the final step is known as "taking the
thermodynamic limit", and this means taking the number of particles in
your equation, N, to infinity.  
  
It is these infinities that make states formally stable, and give us
phase transitions. Infinitesimal changes in conditions, such as
temperature, can lead to dramatic changes to the equilibrium state. Of
course there are not infinity particles in the real world. However, with
roughly 10^24 water molecules in my cup of tea it's a pretty good
approximation.  
  
To be in the thermodynamic limit, therefore, we need an infinite amount of
stuff sitting for an infinite amount of time. The system must be able to
explore all configurations to decide which state to settle on. You can
see where we're going to run into problems.  

#### Back to the real world

Getting back to the start of this post, why are my accusers being
so accusatory? Most likely because the real world, for the most part, is
massively out of equilibrium. From stars and galaxies, down to swimming
bacteria. Then there are materials, such as glasses, where
the relaxation time has become so long that the equilibrium state can't
be reached in times longer than the age of the universe. Or some say
forever – but I'll come back to ergodicity at a later date.  
  
In colloid land things get quite interesting. As mentioned in a
[previous
post](/2011/02/colloids-are-just-right.html),
colloids that are big enough to easily see take about a second to move
around enough to start equilibrating. That's very close to me getting
bored, so if it's a dense system or there are strong attractions one can
expect colloids to quickly fall out of equilibrium.  
  
The theoretical framework for life out of equilibrium is hugely more
complicated that at equilibrium. Even quantities such as temperature
start to lose their meaning in the strictest sense. In fact, while
people are working hard and no doubt making progress, it's safe to say
that it will never be as elegant – or let's say as easy – as what we
have in the thermodynamic limit.  

#### All is not lost

So this means everything we study in equilibrium is useless? It clearly
doesn't exist. Well it's true nothing in the universe meets the strict
definition of infinite time and infinite stuff, but in reality it's
usually alright to have a lot of stuff and enough time. In fact we
regularly study systems with only hundreds of particles and correctly
predict the phase behaviour. It's usually the enough time part that is
the problem.  
  
Knowing what the equilibrium state should be is a bit like knowing the
destination but not the journey. In many many cases this is enough,
atoms can rearrange themselves so quickly that it doesn't really matter
how they get where they're going. Of course in many cases that we worry
about today we need to know both where the system is going, and how it
will get there. It could be that on the way to the true equilibrium
state we get stuck in a state with low, but not the lowest, free energy.
A bit like settling on your favourite restaurant before going to the end
of the street and trying them all. In this case we can maybe plot a
different route through the phase diagram with controls such as pressure
and temperature.  
  
Increasingly these pathways to self-assembly are the focus for many in
the statistical mechanics community. We want to design new materials
with exotic thermodynamic ground states (equilibrium states), so it is
really important to know what will happen in the thermodynamic limit –
we will always need phase diagrams. But with colloids, they're pretty
impatient and will easily settle for the wrong state, so we also need to
think carefully about how we will get to the ground state. It's an
exciting time right now because experimentally we're even able to mess
around with the fundamental interactions between particles in real time,
numbers that we usually take as constants can suddenly be changed. it
really is possible to control every stage of the assembly process from
the start all the way to the end.
