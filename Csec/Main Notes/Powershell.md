[[Win]]
Ps commands are known as cmdlets. they are much more poweful than a trad windows command and allow for mor advanced data manipulation

cmdlets follow Verb-Noun convention

Verb describes action, and the noun specifies the object on which the action is performed

**Basics**
Get-Command: essential tool for discovering commands
Get-Help: provides detailed info about a cmdlet (you can use -examples)
Get-Alias: shows practically applied alliases


A powerful feature of PowerShell is the possibility of extending its functionality bu downloading additional cmdlets from online reps
we can use Find-Module to search for modules with similar names if we dont know the exact one

Once identified you can download the module with Install-Module

**Piping filtering and sorting**

**Piping** Is a technique that allows the output of one command to be used as the input for another, in powershell its even more powerful because it passes objects rather than just text.

You can combine piping with a set of cmdlets that allow for advanced data manipulation and analysis

Sort-Object sorts object using one of their properties for example length

Where-Object Filter using objects that fit certain criteria

Select-Object is used to select specific properties from objects or limit the number returned

Select-String searches for text patterns within files similar to grep

**System and network info**
Get-ComputerInfo snapshot of the entire system

systeminfo same but more reduced

Get-LocalUser lists all local users

Get-NetIpConfiguration info about the network

Get-NetIPAdress details for all ips configured on the system

**Analysis**

Get-Process shows all running processes with info

Get-Service same but for status of services on the machine

Get-NetTCPConnection shows current TCP connections

Get-FileHash generates file hashes

**Scripting** 

Invoke-Command is essential for executing commands remotely

