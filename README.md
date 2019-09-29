# Equilaterus CLI-Tools for Powershell

* Effortless Powershell Scripting.

* Errors do not close command line  windows.

* Great to write CLI utils for your projects.

* It is [Multiplatform](https://github.com/PowerShell/PowerShell)!

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

## Start-Cli params

* **Title**: short text describing your task. 
* **Filename**: The tool will search for this file to start the execution.
* **AlternativePath**: by default it is '..'. If the **Filename** wasn't found the script will lockup in this path.

> It's common to create your scripts under a folder in your repo (usually *utils/*, *scripts/* or *tools*), *Filename* and *AlternativePath* will grant that the script is always executed in the desired folder.


## Example

Suppose that your util files are located under *utils/* folder, the correct script to *Run npm install* will be something like this:

```powershell
. $PSScriptRoot/_EquilaterusCLI.ps1

Function Invoke-Script {
    npm install
}

# You can omit -AlternativePath
Start-Cli -Title 'Install JS APP' -Filename 'package.json' -AlternativePath '..' 

```