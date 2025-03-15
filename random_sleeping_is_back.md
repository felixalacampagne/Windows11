### Randomly sleeping in the middle of work

Problem: 

The extensive measures I had to take to ensure that the computer would stay awake while
performing long running tasks and then go to sleep when they have finished appear to
no longer work. 

The script for doing this relies on command prompt window titles to determine
whether any long running tasks are active. The 'tasklist' command is used to determine whether
processes with specific window titles are active. It seems that this
no longer works for Windows 11 - the tasklist output no longer contains the window
title, instead it contains 'N/A'. Needless to say the command windows are present and
displaying the required titles.

Yet another example of continuous improvement forking up something which worked perfectly well.

Solution:

The problem appears to be caused by the new 'Terminal' way of running command line programs using
a single tabbed window. This seems to have broken 'tasklist' such that it cannot see the title although
it does see the processes.

So the solution is to open a 'Terminal', possibly from the Explorer context menu, and select the little
down arrow (next to the '+' next to the title in the title bar), then Settings.
- Default profile: Command Prompt - this is probably already set
- Default terminal application: Windows Console Host - this is the important one.

The multi-tabbed command prompt window is quite a good idea but typically implemented in a
half-assed way that fails to provide the functionality of the old version thus rendering it unusable - 
in other words, a perfect example of continuous improvement.
