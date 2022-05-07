refer to https://docs.microsoft.com/en-us/powershell/azure/install-az-ps?view=azps-7.5.0

## Check PowerShell version
```
$PSVersionTable
```
```
Name                           Value
----                           -----
PSVersion                      5.1.14409.1018
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
BuildVersion                   10.0.14409.1018
CLRVersion                     4.0.30319.42000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

## PowerShell script execution policy
PowerShell script execution policy must be set to remote signed or less restrictive. Get-ExecutionPolicy -List can be used to determine the current execution policy. For more information, see about_Execution_Policies.
```
Get-ExecutionPolicy -List
```
```
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```
### Set execution policy 
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

# Azure Sign in
command as `Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force` isn't working so just use `Install-Module Az`.
```
Connect-AzAccount
```


# Refer
## PowerShell disabled support for TLS 1.0 for the Gallery - Update-Module and Install-Module broken
https://dev.to/darksmile92/powershell-disabled-support-for-tls-1-0-for-the-gallery-update-module-and-install-module-broken-1oii
