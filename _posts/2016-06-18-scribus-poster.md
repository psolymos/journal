---
title: "Making awesome scientific posters with Scribus"
layout: blog
category: poster
tags: [Scribus, layout]
comments: false
published: true
---

Why invest in nice looking poster? Because it is the hook.
The content is what keeps folks around and interested in follow-up.

## TOC

1. Introduction
  * Why this book? (I have been using it since 2007?, share some tips)
  * Why make a poster in the 1st place? (Pros and cons, and sometimes an oral is downgraded)
  * Why Scribus? (Software and why it matters, it is the hook, full control, professional look, cool open source tools and skillset)
2. Getting started
  * Your research that you are presenting
  * Conference poster guidelines (important dates, format, orientation, dimensions)
  * Software we need (must, and optional, e.g. LaTeX and others, see [here](http://academia.stackexchange.com/questions/1880/software-to-use-for-creating-posters-for-academic-conferences))
  * Create a folder and start collecting necessary files there (files like logos of institutions or sponsors etc.)
3. Storyboard (sections and what to put in them, and [in what order](http://academia.stackexchange.com/questions/29352/which-is-the-better-scheme-for-a-poster-tell-a-story-or-important-first))
4. Layout and dimensions
5. Fonts (font types, typefaces, font size, legibility, readibility, eye tracking) and alignment (left, right, full -- and all the Scribus extras about spacing etc.)
6. Colors (contrasts, color blinds, color palettes: [here](https://wiki.scribus.net/canvas/How_to_create_your_own_colours), [here](http://www.pictaculous.com/), [here](https://docs.gimp.org/en/gimp-concepts-palettes.html), [here](https://docs.gimp.org/en/gimp-palette-dialog.html) for creating/editing palettes with webapp and GIMP, and how to add them to Scribus)
7. Illustrations:
  * photos/images (GIMP) -- including logos for affiliations/sponsors
  * line drawings (Inkscape: [here](http://tavmjong.free.fr/INKSCAPE/MANUAL/html/index.html), [here](http://wiki.inkscape.org/wiki/images/Introduction_to_Inkscape_by_Gavin_Corley.pdf)),
  * comics?
  * figures/plots (reproducible research using R, python, etc.)
  * flowcharts (hand drawn in Scribus, specialized software: DiagrammeR, Graphviz, diagram packages; Dia, Scribus, Google Drive, [https://www.draw.io/](https://www.draw.io/), [TikZ in LaTeX](http://www.texample.net/tikz/examples/simple-flow-chart/))
  * maps ([QGIS](http://www.qgistutorials.com/en/))
8. Tables (native Scribus tables, LaTeX tables, markdown/pandoc)
9. Math notation (simple ones natively, complex ones with LaTeX: [math notation links](http://cazencott.info/index.php/post/2014/08/15/Making-posters-with-Scribus))
10. References, links etc., copyright (use of others work, attribution)
11. Putting it together: boxes, [whitespace](https://science.nichd.nih.gov/confluence/display/~jonasnic/Whitespace), placement, again with eye-tracking.
12. Printing the poster (paper types, storage, travel, print at destination, foldable, multi-piece, price vs. color density)
13. Presenting your poster: shameless self promotion (engagement, social media in action, QR code in jpg/eps, handouts, links, cards)
14. Follow-up after congress (conversion, sharing the poster at Slideshare or similar outlet, social media)

When to discuss other stuff? Like authorship, etc. that is more general?

Forgot to bring the poster.

Somehow classify posters (the good, the bad, the ugly, etc.)

## Goals

1. Write book and develop the poster template.
2. Reproduce the template from scratch and make a tutorial video.
3. Make mini videos (each chapter, really):
  * GIMP for photo/image manipulation
  * Inkscape for line drawings
  * Find something for flowcharts
  * QGIS for maps
  * LaTeX for math and tables
  * R for reproducible/modifiable stats plots

## References

### General links

[general Scribus tutorial](https://www.bio.umass.edu/biology/undergraduate/biology-computer-resource-center/documentation/making-a-poster-with-scribus),
[general poster tutorial](http://www.kmeverson.org/academic-poster-design.html),
[Scribus based one](https://www.linux.com/news/how-create-poster-presentations-scribus),
[An Unofficial Guide](https://archive.org/details/TheUnofficialGuideForAuthors),
[Graphics for conservation](http://scalar.usc.edu/works/graphics-for-conservation/index)
[Stackexchange](http://academia.stackexchange.com/questions/tagged/poster),
[http://www.postersession.com/](http://www.postersession.com/),
[http://www.makesigns.com/](http://www.makesigns.com/tutorials/poster-design-layout.aspx),
[Poster perfect](http://www.the-scientist.com/?articles.view/articleNo/31071/title/Poster-Perfect/), [poster design with really good fun tips, like #D glasses, dry erase doodle](http://colinpurrington.com/tips/poster-design),
[scientific paper](http://pec.sagepub.com/content/40/11/1387.abstract?id=p7015),
[good principles](http://academia.stackexchange.com/questions/2330/what-are-some-general-good-principles-for-creating-a-poster-for-a-poster-session),
[simple rules](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.0030102),
[browse f1000 poster for examples](http://f1000research.com/browse/posters),

### Scientific literature about eye tracking etc.

From [this](http://betterposters.blogspot.ca/2010/10/eye-tracking.html) blogpost, here are 2 refs:

1. Chu S, Paul N, Ruel L. 2009. Using eye tracking technology to examine the effectiveness of design elements on news websites. Information Design Journal 17(1): 31-43. [http://dx.doi.org/10.1075/idj.17.1.04chu](http://dx.doi.org/10.1075/idj.17.1.04chu)
2. Holmqvist K, Wartenberg C. 2005. The role of local design factors for newspaper reading behaviour – an eye-tracking perspective. Lund University Cognitive Studies 127: 1-21. [http://www.lucs.lu.se/LUCS/127/LUCS.127.pdf](http://www.lucs.lu.se/LUCS/127/LUCS.127.pdf)

### Readibility and legibility

Serif vs. sans-serif fonts: [wiki](https://en.wikipedia.org/wiki/Serif#Readability_and_legibility), [blog](http://www.webdesignerdepot.com/2013/03/serif-vs-sans-the-final-battle/), [literature](http://alexpoole.info/academic/literaturereview.html),
and some [more](https://science.nichd.nih.gov/confluence/display/~jonasnic/Acknowledgements+and+References).

> Finally, we should accept that most reasonably designed typefaces in mainstream use will be equally legible, and that it makes much more sense to argue in favour of serif or sans serif typefaces on aesthetic grounds than on the question of legibility.

### Misc

Block, S. 1996. The DOs and DON’Ts of poster presentation. Biophysical Journal 71:3527-3529. [dos and donts of poster presentation; I fixed the typo in the title of the published article, so if you’re copying my citation, don’t]

Briscoe, M.H. 1996. Preparing Scientific Illustrations: A Guide to Better Posters, Presentations, and Publications, 2nd ed. Springer-Verlag, New York. [preview via Google Books]

Foulsham, T., and A. Kingstone. 2011. Look at my poster! Active gaze, preference and memory during a poster session. Perception 40:1387-1389. [link]

Keegan, D.A., and S.L. Bannister. 2003. Effect of colour coordination of attire with poster presentation on poster popularity. Canadian Medical Association Journal 169:1291-1292. [link]

Rigden, C. 1999. ‘The eye of the beholder’—designing for colour-blind users. British Telecommunications Engineering 17:2-6. [PDF]

Tufte, E.R. 1983. The Visual Display of Quantitative Information. Graphics Press, Connecticut. [Amazon]

Wolcott, T.G. 1997. Mortal sins in poster presentations or, How to give the poster no one remembers. Newsletter of the Society for Integrative and Comparative Biology Fall:10-11. [PDF]

Woolsey, J. D. 1989. Combating poster fatigue: how to use visual grammar and analysis to effect better visual communications. Trends in Neurosciences 12:325-332.
