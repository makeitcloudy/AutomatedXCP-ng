# Citrix Hypervisor API / XCP-ng API - 8.2.1

.

```powershell
# 0. Get the XCP-ng or XenServer installed on one of your nodes.
# 1. Download the XenServer SDK
https://github.com/citrix/xenserver-sdk/blob/master/docs/index.md
https://developer-docs.citrix.com/projects/citrix-hypervisor-sdk/en/latest/

# 2. Once downloaded into your management node (in case it is windows based) extract zip file
#  $env:USERPROFILE\Documents\WindowsPowerShell\Modules
$env:PROGRAMFILES\WindowsPowerShell\Modules
#  $env:SystemRoot\system32\WindowsPowerShell\v1.0\Modules

# 3. Import the Module
Import-Module XenServerPSModule

```

## AutomatedXCPng Module

.

```powershell
# 4. Copy the AutomatedXCPng into the same location as the one mentioned for XenServerPSModule
Import-Module AutomatedXCPng
# Module wraps the XenServerPS Module with a bunch of functions which brings the functionality towards VM's provisioning
# 5. List the commands available within the AutomatedXCPng
Get-Command -Module AutomatedXCPng
# 6. Start using the commandlets

```

AutomatedXCPng offers:

* it creates the VM from scratch without touching the xcp-ng Center / XEN Console GUI
* it enumerates the iso available on your iso storage
* it enumerte vm details like network IP and MAC, vcpu, storage etc
* it creates the VM skeletons, bios, uefi, uefi secure boot, equipped with disks and dvd drives
* it adds extra disk
* it start, reboot, shutdown vms
* it takes snapshot
* it scrap the vms

```powershell
PS C:\Windows\system32> Get-Command -Module AutomatedXCPng

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Connect-PLXen                                      0.0        AutomatedXCPng
Function        Disconnect-PLXen                                   0.0        AutomatedXCPng
Function        Example-Example                                    0.0        AutomatedXCPng
Function        Get-PLXenCpuCount                                  0.0        AutomatedXCPng
Function        Get-PLXenIso                                       0.0        AutomatedXCPng
Function        Get-PLXenIsoLibrary                                0.0        AutomatedXCPng
Function        Get-PLXenIsoRepository                             0.0        AutomatedXCPng
Function        Get-PLXenNetwork                                   0.0        AutomatedXCPng
Function        Get-PLXenRam                                       0.0        AutomatedXCPng
Function        Get-PLXenSR                                        0.0        AutomatedXCPng
Function        Get-PLXenStorage                                   0.0        AutomatedXCPng
Function        Get-PLXenTemplate                                  0.0        AutomatedXCPng
Function        Get-PLXenVMNetwork                                 0.0        AutomatedXCPng
Function        New-PLXenSnapshotVM                                0.0        AutomatedXCPng
Function        New-PLXenVM                                        0.0        AutomatedXCPng
Function        Remove-PLXenSnapshotVM                             0.0        AutomatedXCPng
Function        Restart-PLXenVM                                    0.0        AutomatedXCPng
Function        Set-PLXenVM                                        0.0        AutomatedXCPng
Function        Start-PLXenVM                                      0.0        AutomatedXCPng
Function        Stop-PLXenVM                                       0.0        AutomatedXCPng
```

Combined with an iso prepared as per SeguraOSD section, one will end up with unattended installation of running OS'es for your lab scenario.
