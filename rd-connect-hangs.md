## Remote Desktop connection hangs at blurry login screen

Mainly noticed this trying to connect to upgraded desktop machine. It can take 3 or 4 attempts to connect, each one
hanging at a different stage, until a session is established successfully.

Figured this must be one of the things they put into Windows 11 on an unsupported system to 'encourage'
purchase of a brand new machine however I was surprised to see that it is a quite commonly reported issue.

This is what I have tried:

- Fiddle with 'Select Network Detect Level'
= Run gpedit.msc
= Use the following path to get to the "Connections" folder

      Computer Configuration >
        Administrative Templates >
          Windows Components >
            Remote Desktop Services >
              Remote Desktop Session Host >
                Connections

= Open "Select network detection on the server".
= Change the State to ENABLED
= Under Options: change the Select Network Detect Level drop-down to 
  "Turn off Connect Time Detect and Continuous Network Detect".  
= Click Apply > OK Close Group Policy Editor.  
= Open an administrator Command Prompt and run gpupdate /force. NB This reported an error when
  I rand it so no clue whether is took effect.
