$MyClearTextUsername='xx' 
$MyClearTextPassword='xx'
$SecurePassword=Convertto-SecureString –String $MyClearTextPassword –AsPlainText –force
$MyCredentials=New-object System.Management.Automation.PSCredential $MyClearTextUsername,$SecurePassword
Invoke-Command -ComputerName "172.xx.xx.xx" -SessionOption $sessionoption -ScriptBlock {

    param([string]$ComputerName = "localhost")
	Write-Host "Computer: $ComputerName"
	$Command = "schtasks.exe /query /s $ComputerName"
	Invoke-Expression $Command
	Clear-Variable Command -ErrorAction SilentlyContinue
	Write-Host "`n"
    
} -Port 5985 -Credential $MyCredentials -Authentication "Basic"
