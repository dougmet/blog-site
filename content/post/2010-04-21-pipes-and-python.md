+++
title = "Pipes and Python"
slug = "2010-04-21-pipes-and-python"
published = 2010-04-21T10:31:00.001000+01:00
author = "Douglas Ashton"
tags = [ "software",]
aliases = ["/2010/04/pipes-and-python.html"]
+++
I spent ages writing a post about some tricks I use to do quick analysis
of data but it got incredibly bloated and started waffling about work
flows and so on. Anyway, I woke up from that nightmare so I thought I'd
just bash out a couple of my top tips.  
  
This is a pretty nerdy post, you may want to back away slowly.  
  
**Pipes**  
Pipes are, in my opinion, why the command line will reign for many years
to come. Using the pipe I can quickly process my data by passing it
between different programmes gradually refining it as it goes. Here's an
example that makes a histogram (from a Bash terminal):  
  
`> cat myfile.data | awk 'NR>100 {print $5}' | histogram | xmgrace -pipe`  
  
The first command prints the data file. The `|` is the pipe, this
redirects the output to the next programme,
[Awk](http://www.grymoire.com/Unix/Awk.html), which here we are simply
using to pick out the 5th column for all rows over 100 and print the
result. Our pruned data is piped down the line to a programme I made
called histogram which does the histogram and outputs the final result
to my favourite plotting programme to have a look at it.  
  
So we've used three programmes with a single "one liner" (some of my
one-liners become ginormous). Once you start getting the hang of this
sort of daisy chaining it can speed things up incredibly. One bit that
took me a while the first time was the histogram programme. This took an
annoying amount of time to set up because I used C.  
  
This is where Python now comes in.  
  
**Python**  
  
I won't even try to give a Python tutorial. I'm a decade late to the
party and have barely scratched the surface. However, I've found that
for relatively little effort you can get access to thousands of
functions, libraries and even graphics. Most importantly you can quickly
write a programme, pipe in some data, and do sophisticated analysis on
it.  
  
With the [scipy and numpy](http://www.blogger.com/www.scipy.org)
libraries I've done root-finding and integration. The
[pylab](http://matplotlib.sourceforge.net/) module seems to provide many
of the functions you'd get in MatLab. Python is a bit of a missing link
for me, it's much lighter than huge programmes like Mathematica or
MatLab and I just get things done quickly. Here's that histogram
programme, Python style.  
  

    #! /usr/bin/env python
    import sys
    import pylab
    import numpy

    # Check the inputs from the command line
    if len(sys.argv)!=3:
       print "Must provide file name and number of bins"
       sys.exit(1)

    # Read in the data file
    f = open(sys.argv[1],'r')
    histo=[]
    for line in f.readlines():
       histo.append(map(float, line.split()))

    dimension = len(histo[0])

    if dimension == 1:
       pylab.hist(histo, bins=int(sys.argv[2]))

       pylab.xlabel("x")
       pylab.ylabel("N(x)")
       pylab.show()

    elif dimension == 2:
       # Need to chop up the histo list into two 1D lists
       x=[]
       y=[]
       for val in histo:
          x.append(val[0])
          y.append(val[1])

       # This function is apparently straight out of MatLab
       # I killed most of the options
       pylab.hexbin(x, y, gridsize = int(sys.argv[2]))

       pylab.show()

  
Which conveniently detects how many dimensions we're histogramming in so
you don't need two programmes. This is pretty short for a programme that
does what it does.  
  
I hate wasting my time trying to do something that my brain imagined
hours ago. I wouldn't say that these techniques are super easy, but once
you've learned the tools they are quick to reuse. I'd say they're as
important to my work now as knowing C. Got any good tricks? Leave a
comment.  
  
Something less nerdy next week I promise.
