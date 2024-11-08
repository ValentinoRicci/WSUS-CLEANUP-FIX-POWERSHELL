# WSUS-CLEANUP-FIX-POWERSHELL

This script try to fix the *Error: Connection Error. Click Reset Server Node to try to connect to the server again.* in WSUS console.
The issue is mainly due to the IIS provider when the WSUS is storing too many updates (more than 200k). The issue 

Based on
https://learn.microsoft.com/en-us/troubleshoot/mem/configmgr/update-management/wsus-automatic-maintenance

## Maintain the Windows Server Update Services (WSUS) database manually or automatically
Routine maintenance of the WSUS database (SUSDB) is important to ensure the application's health and optimal performance. This article describes concise steps and scripts to maintain SUSDB manually or automatically.

https://github.com/ValentinoRicci/WSUS-CLEANUP-FIX-POWERSHELL/blob/main/SUSDB-Maintenance.ps1

## How long does the maintenance take?
The maintenance duration might vary depending on the machine's resources, including CPU, memory, and disk capacity. Factors affecting the maintenance duration include the time since the last maintenance, the number of selected products and classifications, and the volume of updates that need to be cleaned up.

In a small environment, with minimal products and classifications and recent maintenance on SUSDB, the automatic scripts with the RA option might take less than one minute to run. However, in some cases, it might take several days to complete. If it takes longer than expected and you can't complete the maintenance successfully, you need to create a new SUSDB.

## Requirements
* Powershell MUST be run in Administrator mode.
* WID must be local.
* Remote connections to SQL are now supported; choose [S] Change SQL Server from the menu to set the SQL Server.
* WSUS Console must be installed locally.
* Must have internet access to download the SQL PowerShell Module.
* Must be using v22 or higher of the SQL Server PowerShell Module.

## Powershell available commands
This script will present the following menu options for performing SUSDB maintenance. When the script is executed, a SUSDB-Maintenance.log file will be created and opened.

| CMD    | Description |
| ------ |:--------------------------------------------:|
| [S]    | Change SQL Server, currently set to |
| [A]    | Update Count| 
| [1]    | FIX Slow performance of the spDeleteUpdate procedure.| 
| [2]    | Shrink the SUSDB files | 
| [3]    | Shrink the SUSDB database |
| [4]    | Reindex and update statistics on SUSDB |
| [5]    | Perform a cleanup of the synchronization history |
| [6]    | Perform a cleanup of superseded updates older than 30 days or according to your specific configuration |
| [7]    | Perform a cleanup of obsolete updates |
| [8]    | WSUS Cleanup Wizard |
| [9]    | Cleanup Declined  Updates|
| [10]   | Shrink the SUSDB files |
| [11]   | Shrink the SUSDB database |
| [12]   | Reindex and update statistics on SUSDB |
| [RA]   | Run all above steps sequentially |
| [DD]   | Decline Drivers |
| [FDEL] | ForcePerform various **DELETE commands** to drop Declined Updates from **SUSDB tables** |

Sample scripts are not supported under any Microsoft standard support program or service. Sample scripts are provided AS IS without warranty of any kind.
Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.
The entire risk arising out of the use or performance of the sample script and documentation remains with you.
In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever
(including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use
of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.

