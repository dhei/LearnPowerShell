### Common PowerShell Cmdlets with Sample Outputs
```PowerShell
Get-Command Get-AzureWebsite*

CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Cmdlet          Get-AzureWebsite                                   Azure
Cmdlet          Get-AzureWebsiteDeployment                         Azure
Cmdlet          Get-AzureWebsiteJob                                Azure
Cmdlet          Get-AzureWebsiteJobHistory                         Azure
Cmdlet          Get-AzureWebsiteLocation                           Azure
Cmdlet          Get-AzureWebsiteLog                                Azure
Cmdlet          Get-AzureWebsiteMetric                             Azure

Get-Help Get-AzureWebsite*

Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Get-AzureWebsite                  Cmdlet    Azure                     Gets Azure websites in the current subscription.
Get-AzureWebsiteDeployment        Cmdlet    Azure                     List the deployments for an Azure website
Get-AzureWebsiteJob               Cmdlet    Azure                     Gets the web jobs associated with a website
Get-AzureWebsiteJobHistory        Cmdlet    Azure                     Gets a web job history
Get-AzureWebsiteLocation          Cmdlet    Azure                     Get the website locations available to the current subscription
Get-AzureWebsiteLog               Cmdlet    Azure                     Gets log for the specified website
Get-AzureWebsiteMetric            Cmdlet    Azure                     Gets metrics for Azure website in the current subscription.

Get-Date | Get-Member -MemberType Property 

   TypeName: System.DateTime

Name        MemberType Definition
----        ---------- ----------
Date        Property   datetime Date {get;}
Day         Property   int Day {get;}
DayOfWeek   Property   System.DayOfWeek DayOfWeek {get;}
DayOfYear   Property   int DayOfYear {get;}
Hour        Property   int Hour {get;}
Kind        Property   System.DateTimeKind Kind {get;}
Millisecond Property   int Millisecond {get;}
Minute      Property   int Minute {get;}
Month       Property   int Month {get;}
Second      Property   int Second {get;}
Ticks       Property   long Ticks {get;}
TimeOfDay   Property   timespan TimeOfDay {get;}
Year        Property   int Year {get;}

Get-Date | Get-Member -MemberType Property -static

   TypeName: System.DateTime

Name     MemberType Definition
----     ---------- ----------
MaxValue Property   static datetime MaxValue {get;}
MinValue Property   static datetime MinValue {get;}
Now      Property   datetime Now {get;}
Today    Property   datetime Today {get;}
UtcNow   Property   datetime UtcNow {get;}
```

### PowerShell Automatic Variables with Sample Outputs
[PowerShell about_Automatic_Variables documentation](https://technet.microsoft.com/en-us/library/hh847768.aspx)

##### Full path of the user's home directory
```PowerShell
$Home
C:\Users\<UserName>
```
##### Full path of installation directory for Windows Powershell
```PowerShell
$PsHome
C:\Windows\System32\WindowsPowerShell\v1.0
```

##### Powershell version table
```PowerShell
$PsVersionTable

Name                           Value
----                           -----
PSVersion                      4.0
WSManStackVersion              3.0
SerializationVersion           1.1.0.1
CLRVersion                     4.0.30319.42000
BuildVersion                   6.3.9600.17400
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0}
```

##### Get full path of current Powershell window
```PowerShell
(Get-Item -Path ".\" -Verbose).FullName
```

##### Get full path of current script
```PowerShell
$MyInvocation.MyCommand.Path
```

##### Get full path of the invoker or calling script (not the current script)
```PowerShell
$MyInvocation.PSScriptRoot
```

##### List all environment variables
```PowerShell
ls env:
```

##### Get environment variable Path
```PowerShell
$env:Path
```

##### Get environment variable ComputerName
```PowerShell
$env:ComputerName
```

##### Get cmd.exe path
```PowerShell
$env:Comspec
```

##### Create environment variable for current process/session (not permenant)
```PowerShell
$env:myVariable = "myValue"
```

##### Delete environment variable for current process/session (not permenant)
```PowerShell
del $env:myVariable
```

##### Create permenant environment variable of user-level
```PowerShell
[Environment]::SetEnvironmentVariable("myVariable", "myValue", "User")
```

##### Delete permenant environment variable of user-level
```PowerShell
[Environment]::SetEnvironmentVariable("myVariable", $null, "User")
```
