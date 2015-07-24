---
layout: post
title: Finding the Source of a Strange Macbook Sound
---
======================
For a couple of weeks my MacBook Pro had made intermittant, seemingly random, beeping sounds 
and I couldn't figure out what program or process was caussing this behavior.  It was driving me nuts!

after a lot of googling the solution in the end was pretty simple.  
Here's what I did:  

There is a program called *opensnoop* installed on Macs that tracks file openings.  
And since it was likely that a sound file (with the aiff extension) 
was opened to play the sound I typed this into a terminal:

    $ sudo opensnoop -v 2>/dev/null | grep "aiff"

and waited.  The next time the sound occured it printed out the process that caused it.  
Turned out it was some misconfiguration in the OS X notification center.  
I turned that off and the problem was solved.
