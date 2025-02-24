## Restore normal context menu to Windows 11 explorer

I’ve tried enduring this highly annoying 
feature of Windows11 which hides all the normal right click 
actions that are used almost constantly behind yet another menu 
which contains almost nothing of any use – the items that 
are of use are obfuscated by unreadable icons…

To remedy this dire state of affairs:
- Open a Command Prompt or Terminal, probably not Powershell
- Execute the following command:
```
reg add HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32 /ve /d "" /f
```
- Restart Explorer from Task Manager.

Right-click menu should now be back as it should be.

NB. This does not appear to require 'Administrator' access so can even be performed on constrained systems.

'reg' appears to be a command line tool for manipulating the registry.
The related 'Registry Editor' file can also be used instead of the 'reg' command.

I guess this is a typical 'continuous improver' solution to the over-crowding of the right-click 
menu that can occur - hide it behind yet another click. Why on earth didn't they do something sensible like
providing an editor for the right-click menu so the user, ie. me, can choose which items appear there?
