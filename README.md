# cli-tools-powershell

Equilaterus CLI-Tools for PowerShell.

* Effortless Powershell Scripting.

* Errors do not close command line  windows.

* Great to write CLI utils for your projects.

* [Multiplatform](https://github.com/PowerShell/PowerShell)!

## Instructions

1. Download **_EquilaterusCLI.ps1**.

2. Under the same folder as **_EquilaterusCLI.ps1**, create a ps1 file using the following snippet.

```powershell
. $PSScriptRoot/_EquilaterusCLI.ps1

Function Invoke-Script {
    # Add your commands here
    # ...
}

Start-Cli -Title 'My Title' -Filename 'FileToSearch'

```

3. Run your script!
