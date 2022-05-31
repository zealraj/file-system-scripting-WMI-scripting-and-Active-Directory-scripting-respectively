# file-system-scripting-WMI-scripting-and-Active-Directory-scripting-respectively
i have written different functions/pipelines in powershell that deals with  deals with file system scripting, WMI scripting, and Active Directory scripting respectively

Line number 3 to 15 are the parameters for the script. They are divided into 3 groups -> CopyOldDocs/GetOSVersion/RemoveExpiredUsers. The keyword used to divide params in groups is ParameterSetName.

It is mandatory to supply a parameter to the script when running as [Switch] $CopyOldDocs, [Switch] $GetOSVersion, [Switch] $RemoveExpiredUsers all are mandatory parameters belonging to different groups.

You can run the script using one of the following methods :
1) .\Practical2.ps1 -CopyOldDocs 
2) .\Practical2.ps1 -RemoveExpiredUsers 
3) .\Practical2.ps1 -GetOSVersion 
4) .\Practical2.ps1 -GetOSVersion -ComputerName <remote computername here> 


The following lines from the script check which function you want to run:
if ($CopyOldDocs) {
	Copy-OldDocs
}
if ($RemoveExpiredUsers)
{
	Remove-ExpiredUsers
}
if ($GetOSVersion)	{
	Get-OSVersion
}
