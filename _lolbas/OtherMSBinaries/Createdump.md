---
Name: Createdump.exe
Description: Microsoft .NET Runtime Crash Dump Generator (included in .NET Core)
Author: Daniel Santos
Created: 2022-08-05
Commands:
  - Command: createdump.exe -n -f dump.dmp [PID]
    Description: Dump process by PID and create a minidump file. If "-f dump.dmp" is not specified, the file is created as '%TEMP%\dump.%p.dmp' where %p is the PID of the target process.
    Usecase: Dump process memory contents using PID.
    Category: Dump
    Privileges: SYSTEM
    MitreID: T1003
    OperatingSystem: Windows 10, Windows 11
Full_Path:
  - Path: C:\Program Files\dotnet\shared\Microsoft.NETCore.App\*\createdump.exe
Detection:
  - IOC: createdump.exe process with a command line containing the lsass.exe process id
Resources:
  - Link: https://twitter.com/bopin2020/status/1366400799199272960
  - Link: https://docs.microsoft.com/en-us/troubleshoot/developer/webapps/aspnetcore/practice-troubleshoot-linux/lab-1-3-capture-core-crash-dumps
Acknowledgement:
  - Person: bopin
    Handle: '@bopin2020'
---