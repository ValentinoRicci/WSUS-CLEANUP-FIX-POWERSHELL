# WSUS-CLEANUP-FIX-POWERSHELL

Based on
https://learn.microsoft.com/en-us/troubleshoot/mem/configmgr/update-management/wsus-automatic-maintenance

https://github.com/ValentinoRicci/WSUS-CLEANUP-FIX-POWERSHELL/blob/main/SUSDB-Maintenance.ps1

Requirements
* Powershell MUST be run in Administrator mode.
* WID must be local.
* Remote connections to SQL are now supported; choose [S] Change SQL Server from the menu to set the SQL Server.
* WSUS Console must be installed locally.
* Must have internet access to download the SQL PowerShell Module.
* Must be using v22 or higher of the SQL Server PowerShell Module.

This script will present the following menu options for performing SUSDB maintenance. When the script is executed, a SUSDB-Maintenance.log file will be created and opened.

## Powershell available commands

| CMD    | Description |
| ------ |:--------------------------------------------:|
| [S]    | Change SQL Server, currently set to |
| [A]    | Update Count| 
| [1]    | Update spDeleteUpdate procedure | 
| [2]    | Shrink Files | 
| [3]    | Shrink Database |
| [4]    | Reindex and Update Statistics |
| [5]    | Cleanup Sync History |
| [6]    | Cleanup Superseded Updates Older than x Days |
| [7]    | Cleanup Obsolete Updates |
| [8]    | WSUS Cleanup Wizard |
| [9]    | Cleanup Declined |
| [10]   | Shrink Files |
| [11]   | Shrink Database |
| [12]   | Reindex and Update Statistics |
| [RA]   | Run all above steps sequentially |
| [DD]   | Decline Drivers |
|<span style="color:red">[FDEL]</span> | <span style="color:red">Force delete of Declined from DB</span> |

**<span style="color:red">[FDEL]</span> command directly deletes rows from WID DB**

Sample scripts are not supported under any Microsoft standard support program or service. Sample scripts are provided AS IS without warranty of any kind.
Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.
The entire risk arising out of the use or performance of the sample script and documentation remains with you.
In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever
(including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use
of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.

