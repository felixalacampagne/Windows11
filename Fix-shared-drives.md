Symptom:

Some shared drives are suddenly unavailable, but possibly some are still working.
Possibly nonsensical messages like are displayed:

You can't access this shared folder because your organization's security policies block unauthenticated guest access

Solution:

The continuous improvers randomly decided to block access to shared drives using a guest account, ie. the only 
working means of access for many NAS drives, eg. Western Digital, and practically the only choice 
(given the complexity of creating users etc. under unix) for most others, eg. Enigma2 
satellite receivers. Fortunately the fix is:

    Start gpedit.msc

    Go to Computer Configuration > Administrative templates > Network > Lanman Workstation
    
    Find 'Enable insecure guest logons.' and ensure that it is 'Enabled'.

This issue is the reason I started the repository of Windows 11 fixes. I normally keep such data on my NAS except
the NAS is not available after a Windows 11 installation. It actually appeared as an issue in an update to
Windows 11 around February 2025, earlier Windows 11 installations had not suffered from it.

These are my comments from when the issue arose:

09-Feb-2025 Suddenly discovered that I could no longer access my nas or one of the 
satellite boxes from Windows 11. Could still access PCs and the another satellite box. 
Thought it might be the SMB 1 billshirt rearing it's ugly head again but after wasting hours 
trying to find the place to set it I discovered it was already set correctly.

Next comes the google search with the inevitable time wasting dead ends.

What are these stupid forkers thinking when they make these random changes which 
break vital functionality of a system? By the time the correct setting is stumbled 
across about 20 other so called security settings which have been tampered with in an attempt 
to get the missing functionality back - usually in a hurry so there is no record of what the 
changes were! 
How can that be considered a security enhancement. 
At the very least there should be a prompt to ask the user if these 'enhancement' should be applied 
with an explanation of what it will break, obviously with the option to NOT apply it
