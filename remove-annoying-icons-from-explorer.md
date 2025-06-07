Seems like with every update to Windows the continuous improvement grassholes deliver yet another slew unwanted noise in the Explorer
navigation menu. Here are some clues for removing the most obnoxious ones.

## Home
```
reg add HKCU\Software\Classes\CLSID\{f874310e-b6b7-47dc-bc84-b9e6b38f5903} /v "@" /d "CLSID_MSGraphHomeFolder" /f
reg add HKCU\Software\Classes\CLSID\{f874310e-b6b7-47dc-bc84-b9e6b38f5903} /v "System.IsPinnedToNameSpaceTree" /t REG_DWORD /d 0 /f
```

If it still shows then take ownership of this key and change the value to 0
Computer\HKEY_CLASSES_ROOT\WOW6432Node\CLSID\{f874310e-b6b7-47dc-bc84-b9e6b38f5903}
System.IsPinnedToNameSpaceTree=0

## Gallery
```
reg delete HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Desktop\NameSpace\{e88865ea-0e1c-4e20-9aa6-edcd0212c87c}
```

## iCloud
```
reg add HKCU\Software\Classes\CLSID\{78E66C0B-0349-41A6-AE0A-A0783B439B47} /v "System.IsPinnedToNameSpaceTree" /t REG_DWORD /d 0 /f
```
The id might change so probably need to search CLSID for 'iCloud Drive' or 'IsPinnedToNamespaceTree'

## OneDrive
```
reg add HKCU\Software\Classes\CLSID\{018D5C66-4533-4307-9B53-224DE2ED1FE6} /v "System.IsPinnedToNameSpaceTree" /t REG_DWORD /d 0 /f
```
