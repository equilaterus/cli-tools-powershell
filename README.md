# Equilaterus CLI-Tools for Powershell

Effortless Powershell Scripting!

* Automatically handles the start location path avoiding errors when the script is located on subfolders or when it's called from different paths.

* By default errors do not close command line windows, so you can display better feedback to your users.

* Great to write CLI utils for your projects without needing to write additional code.

* One script to rule them all: Powershell is [Multiplatform](https://github.com/PowerShell/PowerShell)!

## Instructions

1. You can download the latest stable version using the following PowerShell command:

   ```powershell
   Invoke-WebRequest -Uri https://raw.githubusercontent.com/equilaterus/cli-tools-powershell/master/_EquilaterusCLI.ps1 -OutFile '_EquilaterusCLI.ps1'
   ```

2. Under the same folder where **_EquilaterusCLI.ps1** was downloaded, create a ps1 file using the following snippet.

   ```powershell
   . $PSScriptRoot/_EquilaterusCLI.ps1
   
   Function Invoke-Script {
       # Add your commands here
       # ...
   }
   
   Start-Cli -Title 'My Title' -Filename 'FileToSearch'
   
   ```

3. Run your script!


## Examples

Suppose that your util files are located under *utils/* folder, the correct script to *Run npm install* will be something like this:

```powershell
. $PSScriptRoot/_EquilaterusCLI.ps1

Function Invoke-Script {
    npm install
}

# You can omit -AlternativePath as '..' is its default value
Start-Cli -Title 'Install JS APP' -Filename 'package.json' -AlternativePath '..' 

```

### More examples

* Create a script to [Install Ruby Gems and Bundler](https://github.com/equilaterus/wikilaterus/blob/master/_utils/install-site.ps1)

* Create a script to [Run a Docker Compose](https://github.com/equilaterus/base-docker-images/blob/master/utils/run-prod.ps1)

> **Summarizing:** Define your script to automate any given task. Add *Filename* parameter so that Equilaterus CLI knows exactly where the execution should start.


## Start-Cli params

* **Title**: short text describing your task. 
* **Filename**: Equilaterus CLI will lookup for this file to set the location where the script execution should start.
* **AlternativePath**: by default it is *'..'*. If the **Filename** wasn't found in the current location, the script will loockup in this path.

  > It's common to create your scripts under a folder in your repo (usually *utils/*, *scripts/* or *tools*), *Filename* and *AlternativePath* will grant that the script is always executed in the desired folder no matter where the execution started or where your script is located.

* **MaxPopsOnExit**: by default it is 10. If you are doing additional *push*'s to different locations you can adjust this parameter to ensure that your script will end on the original location.

* **SkipIntro**: by default is false. Hides the intro information.

* **SkipLicense**: by default is false. Hides the license information that appears on the script execution.

## More info

* Installing and using Powershell: [See Wikilaterus entry](https://equilaterus.github.io/wikilaterus/wiki/Programming-Powershell.html) 