# Windows commands

These windows commands should help out with live triaging a system. It's specifically tailored towards Windows.

## System Information commands


Echo's date and time
        
        echo %DATE% %TIME%

Displays hostname

        hostname

Displays system information and pipes into find strings related to OS name and OS Version

        systeminfo | findstr /B /C:"OS Name" /C:"OS Version"

Retrieves csproduct

        wmic csproduct get name

Gets BIOS serialnumber

        wmic bios get serialnumber

    wmic computersystem list brief

    wmic product get name,version

    echo %PATH%

  ## User information

    whoami

    net users

    net localgroup administrators

    net group administrators

    wmic rdtoggle list

    wmic useraccount list

    wmic group list

    wmic netlogin get name, last logon,badpasswordcount

    wmic netclient list brief

    doskey /history > history.txt

  ## Network Information Commands

    netstat -e

    netstat -naob

    netstat -nr

    netstat -vb

    route print

    nbtstat -S

    arp -a

    ipconfig /display dns

    netsh winhttp show proxy

    ipconfig /allcompartments /all

    netsh wlan show interfaces

    netsh wlan show all

    reg query "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\InternetSettings\Connections\WinHttpSettings"

    type %SYSTEMROOT%\system32\drivers\etc\hosts

    wmic nicconfig get descriptions,IPaddress,MACaddress
    wmic

  ## Service information

    at

    tasklist

    tasklist /svc

    tasklist /svc /fi "imagename eq svchost.exe"

    tasklist /svc /fi "pid eq <PID>"

    schtasks

    net start

    sc query

    wmic service list brief | findstr "Running"

    wmic service list config

    wmic service list brief

    wmic service list status

    wmic service list memory

    wmic job list brief

    Get-Service | Where-Object { $_.Status -eq "running" }

  ## Policy, patch and settings information

    set

    gpresult /r

    gprresult /z > <Output file name>.txt

    gprresult /H report.html /F

    wmic qfe

    reg query "HKLM\Software\Microsoft\Windows\CurrentVersion\GroupPolicy\AppMgmt"
