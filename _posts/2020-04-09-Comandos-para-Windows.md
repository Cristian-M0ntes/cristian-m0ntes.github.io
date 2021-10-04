---

layout: post
---

netsh advfirewall firewall add rule name="Open port 9000" protocol=TCP dir=in action=allow localport=9000
netsh advfirewall firewall show rule all

reg add "HKEY_LOCAL_MACHINE\SYSTEM\currentControlSet\Control\Terminal Server" /v fDenyTSConnections \t REG_DWORD /d 0 /f

wevtutil el
wevtutil cl Ejemplo

#en powershell 
wevtutil el | Foreach-Object {wevtutil cl "$_"}

#VNC
reg query "HKCU\Software\ORL\WinVNC3\Password"
#Windows Autologin
reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon"
#SNMP Parameters
reg query "HKLM\SYSTEM\Crrent\ControlSet\Services\SNMP"
#Putty clear text proxy credentials
reg query "HKCU\Software\SimonTatham\PuTTY\Sessions"
#Search the reistry - copy (pipe) to the clipboard 
reg query HKLM /f password /t REG_SZ [clip]
reg query HKCU /f password /t REG_SZ [clip]
#Directory permissions 
cacls
icacls

