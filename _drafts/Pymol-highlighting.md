---
title: Syntax Highlighting for Pymol Scripts
layout: post
group: blog
---
<img class="img-responsive center-block" src="/static/img/pymol/snippet.png" alt="snippet.png">

I am learning to be a structural biologist, and with that comes learning to make figures in [Pymol](http://www.pymol.org), the most used molecular graphics software for crystallographers (UCSF Chimera tends to be more popular among electron microscopists in my experience). 
One of the great things about pymol is the ability to write scripts to reproducibly create the same figure, as well as being able to write loops to perform tasks iteratively. 
A few members of our lab excel at writing these `pml` files, and spend a fair amount of time working with them. 
While watching them work on these files (with the hopes of getting better at writing them myself), I noticed something very distinctive about the user experience.
When editing the files, they look like this:

<img class="img-responsive center-block" src="/static/img/pymol/screenshot_unformatted.png" alt="unhighlighted code">

It is plain! There is no indication of what the different parts of the code mean, which makes it much more difficult to parse the meaning of each part of the code in my experience. I am sure that for people more familiar with pymol that problem disappears, but for me it was a significant stumbling block. I decided that it was time to fix it, and so I set about to write a "language grammar" to allow for syntax highlighting of pymol files in sublime text. You can find the result at my [Github](https://github.com/bbarad/pymol_syntax) or download the final product for sublime text through [Package Control](https://sublime.wbond.net/packages/Pymol%20Language). You can read about the process and see the final product in more detail below.

<!--break-->