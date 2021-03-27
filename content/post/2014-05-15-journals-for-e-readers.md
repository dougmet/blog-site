+++
title = "Journals for e-readers"
slug = "2014-05-15-journals-for-e-readers"
published = 2014-05-15T16:43:00+01:00
author = "Douglas Ashton"
tags = [ "journals", "communication",]
+++
One thing that makes me cross is that despite the terrifying amount of
money our library pays to buy back our research in the form of journals,
they're still not terribly easy to read. I've got an e-reader now and
I'd like to read things on that, just the sort of value-added that the
publishers could do. Unfortunately everything is still just a pdf file
only to be printed on A4.  
  
There are [some utilities](http://willus.com/k2pdfopt/) for coping with
this but it's not really ideal.  
  
I wanted to see how tough it is. So I tried to convert my last paper
into something that would look nicer on an e-reader (in my case a
kindle). The paper was written for an
[APS](http://www.aps.org/publications/journals) journal using the
[REVTeX 4.1](https://journals.aps.org/revtex) package. This makes it
very easy to write papers formatted for APS (and possibly some others as
well). The answer is that this was the best I could get it using
REVTeX.  
  
[Ashton2014\_ereader.pdf](http://people.bath.ac.uk/da246/publications/papers/Ashton2014_ereader.pdf)  
which originally looked like this:  
<http://arxiv.org/pdf/1401.2064v1.pdf>  
or [here if you have
access](http://link.aps.org/doi/10.1103/PhysRevE.89.031301)  
  
It's actually not too bad! The abstract's gone a little wrong and the
font is not strong enough, but it's not a disaster. It proves to me that
the guys who make REVTeX could quite easily make a beautiful e-reader
mode full of useful options. I made the citations clickable links for
example.  
  
To get this working I simply replaced this line  

```
    \documentclass[aps, prl, twocolumn,superscriptaddress,amsmath,amssymb,floatfix]{revtex4-1}
```
  
  
with these lines  

```
    \documentclass[12pt,a5paper,superscriptaddress,amsmath,amssymb,floatfix]{revtex4-1}

    \usepackage[papersize={4.5in,6in},margin=0.5cm]{geometry}
```
  
Without the second one it doesn't seem to work very well. If you've got
a better (and just as easy method) then leave a comment. I could have
made it better by dropping REVTeX and customising every detail. Frankly
that was proving a lot of work and that's not what I believe LaTeX
should be about.  
  
From now on I'll be uploading an e-reader version as well as an A4
version for my papers.  
  
UPDATE:  
Royal Society of Chemistry, with a bit of fiddling looks fantastic on
the kindle:  
[Ashton2013\_ereader.pdf](http://people.bath.ac.uk/da246/publications/papers/Ashton2013_ereader.pdf)  
Had to dig about a bit to get this one-column (there's a \\twocolumn\[
half way down the page in the template that needs removing). Fiddled
with the margins and widths a lot. See the [.tex file
here](http://people.bath.ac.uk/da246/publications/papers/ereader.tex).
Might go back to the APS paper and reduce the paper size even more. This
seems to work quite nicely:  
  
```
    \usepackage[papersize={9cm,12cm},margin=0.5cm]{geometry}
```

UPDATE2:  
Got the RSC send-to-kindle button working and this just sends the
two-column pdf. I guess the best hope is converting the html version
then.  
  
FINAL UPDATE:  
I've found the best way I think now. It's to skip pdf altogether and go
via html. Using htlatex I compiled the same original latex file into
this webpage:  
<http://people.bath.ac.uk/da246/papers/Ashton2014/>  
It's a bit broken here and there (you must use revtex4 and not
revtex4-1, one day I'll go back through and work out all the settings
needed to properly convert a revtex made file. Mostly it works.  
  
Next step was to download the
[KindleGen](http://www.amazon.com/gp/feature.html?docId=1000765211) utility
and use that to convert the html to a .mobi file format. This is what I
then put onto my kindle. If you download this and put it onto your
kindle  
<http://people.bath.ac.uk/da246/papers/Ashton2014/Ashton2014.mobi>  
you'll see that this is basically perfect for what you want from a
Kindle version of a paper. For sure some things need fixing, for example
the equations are a bit small. I'll work all of that out and make a
separate post.  
  
The bottom line for this whole thing is that if I, a mostly lazy man,
can get half way decent conversions of my LaTeX files onto an e-reader
in an evening, then the journals could easily do this.
