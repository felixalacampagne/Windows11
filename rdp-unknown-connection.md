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

While attempting to get rid of this ridiculous pop-up on a restricted access machine I came across something which might be useful for actually doing the signing nonesense should the registry workaround cease to function. A powershell script has been created to generate a certificate for use in the signing, see here: https://github.com/IanVanLier/April-2026-security-update-Remote-Desktop-Conection-security-warning-/tree/main.
It appears that simply signing the rdp file is not sufficient, group-policy (GPO) entries are also required. Obviously these are not possible on a restricted system so the annoyance will continue for the foreseeable future since the system administrators could not be bothered to fix the problem or provide a solution.
