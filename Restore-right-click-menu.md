Restore normal context menu to Windows 11 explorer

I’ve tried enduring this highly annoying 
feature of Windows11 which hides all the normal right click 
actions that are used almost constantly behind yet another menu 
which contains almost nothing of any use – the items that 
are of use are obfuscated by unreadable icons…
 
reg add HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32 /ve /d "" /f

 
This should fix it – although it won’t be any use on a work system where access to 
the registry is denied, but the loss of productivity isn’t my problem in that case.