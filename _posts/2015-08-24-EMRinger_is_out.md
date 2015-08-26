---
title: "EMRinger is published!"
layout: post
group: blog
---

Earlier this year, [I posted](http://benjaminbarad.com/2015/02/17/EMRinger/) about my first project with the Fraser lab, which resulted in the tool [EMRinger](https://github.com/fraser-lab/EMRinger). The paper came out last week as a brief communication in [nature methods](http://www.nature.com/nmeth/journal/vaop/ncurrent/full/nmeth.3541.html) under the title "EMRinger: side chain–directed model and map validation for 3D cryo-electron microscopy" (doi: [10.1038/nmeth.3541](http://dx.doi.org/10.1038/nmeth.3541)/pmid: [26280328](http://www.ncbi.nlm.nih.gov/pubmed/26280328)). 

This was my first time going through the peer review process, and for the most part it went smoothly. That said, it took 6 months for what was a positive review process to result in a publication! Thankfully, we preprinted the paper on [biorxiv](http://dx.doi.org/10.1101/014738), so the work was publicly available during that time. I also gave 2 talks on EMRinger in the intervening months, at the Bay Area Cryo-EM symposium and as a selected poster presentation at the 3DEM Gordon Conference. Having the preprint was very nice for being able to easily send our manuscript to people that were interested in learning more. I have more thoughts about the preprinting experience, but I will probably break those off into a separate post where I can focus solely on my experiences with it and plans for the future.

<!--break-->

During those 6 months, I made some progress on some of the next steps I had planned out when I last wrote about EMRinger. Most importantly (I think), we got emringer fully integrated into [Phenix](http://phenix-online.org), both as a command line tool with `phenix.emringer` and as a graphical application within the Phenix GUI. For me, this was really important, as I think having it integrated into one of the major structural biology software packages will lower the barrier to entry for calculating scores and getting better structures. The webapp is still in development, but I plan to complete it once I've finished with [UCSF iPQB Bootcamp](http://bootcamp.ipqb.org/), which is an awesome student-run program to get first-year graduate students ready to do graduate work. I'll write about that soon as well.

Now all that is left is to see whether people start calculating EMRinger scores... and to get to work on the next set of projects!