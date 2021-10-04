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

