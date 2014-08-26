---
title: Syntax Highlighting for Pymol Scripts
layout: post
group: blog
---
<img class="img-responsive center-block" src="/static/img/pymol/snippet.png" alt="snippet.png">

The Fraser lab makes most of its figures that represent protein structure and electron density in [Pymol](http://www.pymol.org), which in my experience seems to be the most popular molecular graphics software for crystallography. One of the great things about pymol is the ability to write scripts to reproducibly create the same figure, as well as being able to write loops to perform tasks iteratively. A few members of our lab excel at writing these `pml` files, and spend a fair amount of time working with them. 

When editing the files, they look like this:

<img class="img-responsive center-block" src="/static/img/pymol/screenshot_unformatted.png" alt="unhighlighted code">

They are treated as *plain text*; there is no indication of what the different parts of the code mean, which makes it much more difficult to parse the meaning of each part of the code in my experience. I am sure that for people more familiar with pymol, this is no longer problematic, but for me it was a stumbling block. To fix this, I wrote a __language grammar__ to allow for syntax highlighting of pymol files in sublime text. You can find the result at my [Github](https://github.com/bbarad/pymol_syntax) or download the final product for sublime text through [Package Control](https://sublime.wbond.net/packages/Pymol%20Language). I recommend the package control version because it will update automatically as I add improvements over time. You can read about the process and see the final product in more detail below.

<!--break-->

## The Final Product
<img class="img-responsive center-block" src="/static/img/pymol/screenshot_formatted.png" alt="highlighted code">
I am giving away the game by showing the final result so soon, but I thought it was important to show everything that is highlighted. Syntax highlighting is accomplished via a series of regular expressions which are associated with scope names that color schemes read to color text.

## The Syntax
Pymol syntax is surprisingly complicated. The traditional syntax is essentially `command target, options`, but there are many variations for different special cases. For instance, the `ray` command takes no arguments at all, `set_view` takes only a parenthesized series of floats as an argument, and `show` and `color` take the option (color choice or show type) before the target object! To add to the confusion, there is an additional, more python-like syntax: `cmd.command(options)`. Finally, targets can be either names or the result of selector logic, which need not be parenthesized.

Ultimately I broke it down into lines which simply start with the `command` from those which begin with the `cmd.command` syntax. From there, I checked for the target syntax, including parentheticals, and if that was found checked for a comma and labelled everything that came after as an option. This did not accound for the `show` and `color` syntaxes, in which the second argument should have been the target, but ultimately I have decided that this is a future goal rather than an immediate concern. 

After a discussion with [Justin Biel](http://fraserlab.com/members#Justin Biel), I decided to confine command highlighting to a known list of commands, to allow for mis-highlighting of incorrect spellings, making typos more obvious. Because of this, however, I may have missed some commands. Please let me know if you run into any like this and I will be sure to add them!

## The Technology
I wrote my language grammar in the textmate format, which works with a number of text editors but in particular [Sublime Text](http://www.sublimetext.com/), which is my editor of choice. For [vim](http://www.vim.org/) users, there is the similar project from [Michal Gajda](http://www.vim.org/scripts/script.php?script_id=2814) that I have not used but which I took inspiration from for my project.

The format of the textmate file is somewhat frustrating xml, but I was thankfully able to use the excellent [AAAPackageDev](https://github.com/SublimeText/AAAPackageDev) to work in YAML and have lots of helpful autocompletion and highlighting tools. Hopefully it is simple enough that others will be able to make modifications freely.

One of the convenient parts of working with sublime text is [Package Control](https://sublime.wbond.net/), a package manager for user extensions. I ultimately chose to add my pymol language grammar to package control, both to simplify the installation and to easily update users to the newest versions. I can use git's tagging system to indicate new version in a way that is orthogonal to the commit system, so that users need to download new updates only at major milestones.

Please let me know if you find any problems. Any and all issues can be submitted at my [github page for the project](https://github.com/bbarad/pymol_syntax/issues), and if you are feeling particularly adventurous I would recommend trying to correct the problem yourself and then submitting a pull request! I would love to see a solution to the target/option ordering problem in particular.

I hope this makes working with pymol more enjoyable!