To prevent the assinine 'Caution: Unknown Remote Connection' popup which started
appearing in April 2026 when an RDP file is used to open an RDP session it is
necessary to add a registry key:

HKLM\Software\Policies\Microsoft\Windows NT\Terminal Services\Client
   (DWORD) RedirectionWarningDialogVersion 1

From an Administrator Powershell:
New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services\Client" -Name "RedirectionWarningDialogVersion" -Value 1 -PropertyType DWord -Force

M$ talk about using 'rdpsign.exe' to sign the RDP files, but no certificate is provided to do this with and the tool is effectively impossible to use as it requires the 'Secure Hash Algorithm 256 (SHA256) hash of the signing certificate that is included in the certificate store.', ie. no indication of what certificate or which store or how to get the hash.
(https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/rdpsign).

What the hell are these forkers on when they dream up this shirt? I just want to access my desktop machine from my laptop like I have done for the last 20years, why the hell does it have to be continuously improved into something a million times more complicated that it needs to be?
