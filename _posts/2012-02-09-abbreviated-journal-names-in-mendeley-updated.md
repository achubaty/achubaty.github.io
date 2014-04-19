---
layout: post
status: publish
published: true
title: Abbreviated Journal Names in Mendeley [updated]
author: Alex Chubaty
date: !binary |-
  MjAxMi0wMi0wOSAxNjoxNDozNiAtMDgwMA==
date_gmt: !binary |-
  MjAxMi0wMi0xMCAwMDoxNDozNiAtMDgwMA==
categories:
- Mendeley
tags: []
comments:
- id: 1
  author: ARB
  author_email: aurelie.boissezon@unige.ch
  author_url: ''
  date: !binary |-
    MjAxMy0wNi0xOSAwNDoyMzowMCAtMDcwMA==
  date_gmt: !binary |-
    MjAxMy0wNi0xOSAxMToyMzowMCAtMDcwMA==
  content: ! "Hello!  thanks for this helpful article! But I have a problem whith
    the command \"chmod\". The terminal give an error message: 'chmod\" is not recognized
    as an internal or external command ... Do you know how to fix this problem? \n\nThanks!
    \n\nARB"
- id: 2
  author: Alex Chubaty
  author_email: alex.chubaty@gmail.com
  author_url: http://alexchubaty.com/
  date: !binary |-
    MjAxMy0wNi0yMCAwMDozMDowMCAtMDcwMA==
  date_gmt: !binary |-
    MjAxMy0wNi0yMCAwNzozMDowMCAtMDcwMA==
  content: ! 'chmod is standard for unix/linux systems.

    1) what operating system are you running? as mentioned in the post, these instructions
    won''t work for windows.

    2) if you are on a *nix machine, did you enter the command exactly as it appears
    (e.g., no added characters, like quotes)?'
---

*UPDATE: I just posted [an update]({% post_url 2013-06-20-more-on-journal-abbreviations-in-mendeley %}). This feature is coming soon to Mendeley!*


Several journals require abbreviated journal names, but as of yet Mendeley doesn't make this possible. Or so I thought. After coming across [this blog post](http://simply-p450s.blogspot.com/2012/01/journal-abbreviations-in-mendeley.html) I decided to try to get this functionality working on my computers.

To summarize, you can get Mendeley to read in a list of abbreviated journal names by:

- creating a folder inside the Mendeley data  directory called '*journalAbbreviations*';
- placing a formatted text file named '*default.txt*' inside this directory. Each line of this text file needs to contain the full name of the journal, a tab character, and the abbreviated journal name.

"Easy", I thought. All I needed was to find a list of full journal names and their abbreviations for my field and make sure it was formatted correctly. Turns out the few lists I did find were incomplete: they didn't have all the journals I cite. I don't want to have to maintain a text file by hand, so I looked to a more "automated" approach, outlined below.

I use both BibTeX and Mendeley for my references, and have setup Mendeley to automagically update and maintain my bibliography (*.bib*) files. This is key to obtaining a list of the journals I use - I extracted this info from the *.bib* files and compared this list of journals against the master list to get the abbreviations.

First, <del>I obtained (by hand, sadly) a list of all the ISI journals indexed by Web of Science from <a href="http://images.webofknowledge.com/WOK46/help/WOS/A_abrvjt.html" target="_blank">this site</a>. I copy/pasted all the journals into a text file named '*masterlist.txt*'.</del> I wrote a script to generate a master list of all journal names and their abbreviations from Web of Science ([see this post]({% post_url 2012-02-28-list-of-abbreviated-journal-names %})). This file is pretty big, and not very helpful at that point. I don't need ALL of those journals, only the journals I cite from my Mendeley library.

The Perl script I wrote (with Charlie and Filipe) does all of this and saves the list of journals used directly into the Mendeley data folder.

To get this working yourself, follow the steps below:

**NOTE:** This was written for and tested on a machine running Ubuntu 11.10 64-bit with a default Mendeley installation (also tested and run on Ubuntu 12.04 and 12.10). IT WON'T WORK ON WINDOWS OR A MAC WITHOUT SOME CHANGES TO THE PERL SCRIPT because the Mendeley directories are in different places on different operating systems. There may be some funny perl-related issues going between OSes too that I'm not aware of.

- Download and save <a href="/uploads/2013/04/jabbrev.zip" target="_blank">jabbrev.zip</a> and unzip the directory '*jabbrev*'
- open a terminal (and keep it open) and type:

    ```
    cd path/to/jabbrev
    ```

- In Mendeley go to '*Tools*' --> '*Options*' and select the '*BibTeX*' tab.
- Check the box 'Enable BibTeX syncing' and select either:
'*Create one BibTeX file for my whole library*' or '*Create one BibTeX file per collection*'
- Set the path to where these BibTeX files will be saved (e.g., `~/Documents/Mendeley/bibliographies`).
- Click '*Apply*' and '*OK*', wait for Mendeley to generate the files, then exit Mendeley.
- In a nautilus window, go to the bibliographies directory you just set up (e.g., `~/Documents/Mendeley/bibliographies`)
- Switch back to your open terminal window and allow the script to be executed by typing:

    ```
    chmod a+x script.pl
    ```

- The script accepts a filepath for each of the masterlist and multiple bibtex files. Execute the script by typing:

    ```
    ./script.pl /path/to/masterlist.txt /path/to/bibfile1.bib [/path/to/bibfile2.bib ...]
```

- Sit back and wait (it may take a while to run, especially with a large library!).
- Open Mendeley back up, go to '*View*' --> '*Citation Style*' --> '*More Styles...*' and select a citation format that uses abbreviated journal names (e.g., Vancouver). You should now be able to generate bibliographies in Word and Open(Libre)Office documents with abbrev j names!*

\*note that the abbreviated names do NOT have periods.

**EDIT:** view the perl script at <a href="http://pastebin.com/2C7X8aGZ">http://pastebin.com/2C7X8aGZ</a> [updated 2013-02-27]. It's not perfect (yet) but it's mostly there. Suggestions welcome, especially how to deal with some of the funny cases.

