Windows 10 required it's fair share of tweaks to make it usable.

## Auto-login

The Windows 11 update might break this but it can be restored with the Windws 10 trick:

   Search for “netplwiz” and run as Administrator
   Uncheck the “Users must enter a username and password to use this computer” checkbox.
   Select the user account in the “Users” tab.
   Click on the “Apply” button.
   Type the password twice and click “Ok”
   
   If this still doesn't work then maybe
      HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
         DefaultUserName = Chris (String)
         DefaultPassword = clearpwd (String)
         AutoAdminLogon = 1 (String)

NB auto-login might be prevented by Windows Hello so it will need to be disabled if this is the case.
   Disable Windows Hello
      Settings > Accounts > Sign-in options
   If there is no option to disable Hello then maybe this registry edit will work
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\PasswordLess\Device
      set “DevicePasswordLessBuildVersion” = 0  (from 2)


## No lock/login when display is switched off

   Settings > Personalisation > Screen Saver settings > 
      On resume, display log-on screen: Uncheck

## Set workgroup
   
   This requires the network to be Private. To change it might require hunting around a bit. It was
   under Network & Internet > Ethernet > Ethernet icon > Network Profile for LOFTY.

   Don't know whether workgroups are actually used anymore. It might be something which helps the STBs
   find shared drives though.

## Open Command window here without shift

I think this is no longer necessary with Windows 11 as 'Terminal' appears on the normal right-click menu. Just in
case it goes away though, this is how it was done (it needs to be made into a .reg file):
```
Windows Registry Editor Version 5.00

; Puts the 'Open command window here' item on the normal right-click menu instead of ctrl-right-click
; 
; If windows updates keep on write protecting the normal 'cmd' entry then simply add an alternative one
; To restore command prompt to start menu right click goto Settings>Personalisation>Taskbar and uncheck the option
; to replace command prompt with power shell
;
; Default menu text is
;@="@shell32.dll,-8506"


[HKEY_CLASSES_ROOT\Directory\shell\cpacmd]
@="Command window here"
"NoWorkingDirectory"=""
"Extended"=-

[HKEY_CLASSES_ROOT\Directory\shell\cpacmd\command]
@="cmd.exe /s /k pushd \"%V\""

[HKEY_CLASSES_ROOT\Directory\Background\shell\cpacmd]
@="Command window here"
"NoWorkingDirectory"=""
"Extended"=-

[HKEY_CLASSES_ROOT\Directory\Background\shell\cpacmd\command]
@="cmd.exe /s /k pushd \"%V\""

[HKEY_CLASSES_ROOT\Drive\shell\cpacmd]
@="Command window here"
"NoWorkingDirectory"=""
"Extended"=-

[HKEY_CLASSES_ROOT\Drive\shell\cpacmd\command]
@="cmd.exe /s /k pushd \"%V\""

; To restore to the right-click menus it needs a registry update.
; WARNING: It might be necessary to grant permission to the keys before they can be corrected.

[HKEY_CLASSES_ROOT\Directory\Background\shell\cpacmd]
"HideBasedOnVelocityId"=-

[HKEY_CLASSES_ROOT\Directory\shell\cpacmd]
"HideBasedOnVelocityId"=-

[HKEY_CLASSES_ROOT\Drive\shell\cpacmd]
"HideBasedOnVelocityId"=-
```
