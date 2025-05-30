This issue plauges Windows 10 and resurfaces after the update to Windows 11

Cause #1

Scheduled jobs have a different sleep timeout to normal user operations, ie. the system
will sleep only a few minutes after starting a scheduled task even though the sleep
timeout is much longer than required for the task to complete. This is becuase 
scheduled tasks are subject to a differnt sleep timeout - one that has been cunningly 
hidden so you don't know about it and can't change it. 
This can be fixed with 

Windows Registry Editor Version 5.00
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\238C9FA8-0AAD-41ED-83F4-97BE242C8F20\7bc4a2f9-d8fc-4469-b07b-33eb785aaca0]
"Attributes"=dword:00000002

which I should convert into a 'reg' command someday as I keep needing to use it

Cause #2

Tasks started by the task scheduler take
many hours when they would normally take a matter of minutes (well maybe something like 90minutes). This is
especially true for tasks requiring network transfers.
Apparently this is because tasks started by the task scheduler by default have a MUCH lower network transfer 
speed than when started in the 'normal' way from explorer or the command line. Again this is a hidden
setting which cannot be seen or modified in task scheduler.

The only way to overcome this problem is to export the task, edit the XML to change the priorty to a normal
setting and then re-import. Can't recall the exact settings at the moment so this is more of a reminder 
that is must be done when creating a new task which uses the network.
