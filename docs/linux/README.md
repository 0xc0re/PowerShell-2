# Install SolidFire PowerShell on Linux

![solidfire-powershell-logo](../../Install/product.png) ![linux-logo](linux-logo-small.png)

The commands should be run in a terminal session on the machine you want to install on. You don't have to be in a specific directory to execute any of these commands. You will need sudo access. 

## Uninstall Old Version of SolidFire

If you previously installed SolidFire 1.4, you should uninstall it before installing SolidFire 1.5.

1. Remove the old SolidFire module files:

        $ sudo rm -rf /usr/local/share/powershell/Modules/SolidFire

1. If you created a PowerShell profile file to initialize the SolidFire module on PowerShell startup, remove that file :

        $ sudo rm /opt/microsoft/powershell/6.0.0-beta.2/profile.ps1

1. If you will be upgrading to the latest PowerShell, you can also remove the directory where that profile file was located:

        $ sudo rm -rf /opt/microsoft/powershell/6.0.0-beta.2

## Install or Upgrade PowerShell bits

Follow the detailed instructions on the [PowerShell for Linux installation page](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md). 
    
## Install SolidFire bits

1. Start a PowerShell shell:

        $ pwsh

1. Inside the PowerShell shell, install SolidFire PowerShell Tools by downloading it from the [PowerShell Gallery](https://powershellgallery.com) with the following command:

        PS> Install-Module -Name SolidFire.Linux

1. Then, import the SolidFire module with the following command:

        PS> Import-Module SolidFire.Linux

1. To see a list of available commands, use:

        PS> Get-Command -Module SolidFire.Linux

## Paths

* `$PSHOME` is `/opt/microsoft/powershell/[version]/`
* User profiles will be read from `~/.config/powershell/profile.ps1`
* Default profiles will be read from `$PSHOME/profile.ps1`
* User modules will be read from `~/.local/share/powershell/Modules`
* Shared modules will be read from `/usr/local/share/powershell/Modules`
* Default modules will be read from `$PSHOME/Modules`
* PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`

The profiles respect PowerShell's per-host configuration,
so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.

On Linux and macOS, the [XDG Base Directory Specification][xdg-bds] is respected.

[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html

