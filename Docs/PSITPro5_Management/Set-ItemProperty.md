﻿# Set-ItemProperty

## SYNOPSIS
Creates or changes the value of a property of an item.

## DESCRIPTION
The Set-ItemProperty cmdlet changes the value of the property of the specified item.
You can use the cmdlet to establish or change the properties of items.
For example, you can use Set-ItemProperty to set the value of the IsReadOnly property of a file object to true.

You also use Set-ItemProperty to create and change registry values and data.
For example, you can add a new registry entry to a key and establish or change its value.

## PARAMETERS

### Credential [PSCredential]

```powershell
[Parameter(ValueFromPipelineByPropertyName = $true)]
```

Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as "User01" or "Domain01\User01", or enter a PSCredential object, such as one generated by the Get-Credential cmdlet.
If you type a user name, you will be prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.


### Exclude [String[]]

Specifies those items upon which the cmdlet is not to act, and includes all others.


### Filter [String]

Specifies a filter in the provider's format or language.
The value of this parameter qualifies the Path parameter.
The syntax of the filter, including the use of wildcards, depends on the provider.
Filters are more efficient than other parameters, because the provider applies them when retrieving the objects rather than having Windows PowerShell filter the objects after they are retrieved.


### Force [switch]

Allows the cmdlet to set a property on items that cannot otherwise be accessed by the user.
Implementation varies from provider to provider.
For more information, see about_Providers.


### Include [String[]]

Specifies only those items upon which the cmdlet will act, excluding all others.


### InformationAction [System.Management.Automation.ActionPreference]

```powershell
[ValidateSet(
  'SilentlyContinue',
  'Stop',
  'Continue',
  'Inquire',
  'Ignore',
  'Suspend')]
```


Type a user name, such as "User01" or "Domain01\User01", or enter a PSCredential object, such as one generated by the Get-Credential cmdlet.
If you type a user name, you will be prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.


### InformationVariable [System.String]


Type a user name, such as "User01" or "Domain01\User01", or enter a PSCredential object, such as one generated by the Get-Credential cmdlet.
If you type a user name, you will be prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.


### InputObject [PSObject]

```powershell
[Parameter(
  Mandatory = $true,
  ParameterSetName = 'Set 2')]
[Parameter(
  Mandatory = $true,
  ParameterSetName = 'Set 3')]
```

Specifies the object that has the properties that you want to change.
Enter a variable that contains the object or a command that gets the object.


### LiteralPath [String[]]

```powershell
[Parameter(
  Mandatory = $true,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 2')]
[Parameter(
  Mandatory = $true,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 4')]
```

Specifies a path to the item property.
The value of LiteralPath is used exactly as it is typed.
No characters are interpreted as wildcards.
If the path includes escape characters, enclose it in single quotation marks.
Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.


### Name [String]

```powershell
[Parameter(
  Mandatory = $true,
  Position = 2,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 1')]
[Parameter(
  Mandatory = $true,
  Position = 2,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 4')]
```

Specifies the name of the property.


### PassThru [switch]

Returns an object representing the item property.
By default, this cmdlet does not generate any output.


### Path [String[]]

```powershell
[Parameter(
  Mandatory = $true,
  Position = 1,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 1')]
[Parameter(
  Mandatory = $true,
  Position = 1,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 3')]
```

Specifies the path to the items with the property to be set.


### Type [Microsoft.Win32.RegistryValueKind] = string

```powershell
[Parameter(
  Mandatory = $true,
  Position = 3,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 1')]
[Parameter(
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 2')]
[Parameter(
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 3')]
[Parameter(
  Mandatory = $true,
  Position = 3,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 4')]
```

Establishes or changes the data type of a registry value.
The default is String (REG_SZ).
Valid values for this parameter include the following:

-- String.
Specifies a null-terminated string.
Equivalent to REG_SZ.

-- ExpandString.
Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.
Equivalent to REG_EXPAND_SZ.

-- Binary.
Specifies binary data in any form.
Equivalent to REG_BINARY.

-- DWord.
Specifies a 32-bit binary number.
Equivalent to REG_DWORD.

-- MultiString.
Specifies an array of null-terminated strings terminated by two null characters.
Equivalent to REG_MULTI_SZ.

-- Qword.
Specifies a 64-bit binary number.
Equivalent to REG_QWORD.

-- Unknown.
Indicates an unsupported registry data type, such as REG_RESOURCE_LIST.

This parameter works as designed on the Set-ItemProperty cmdlet.
It is also available on the Set-Item cmdlet in the registry drives, but it has no effect.


### Value [Object]

```powershell
[Parameter(
  Mandatory = $true,
  Position = 3,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 1')]
[Parameter(
  Mandatory = $true,
  Position = 3,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 4')]
```

Specifies the value of the property.


### Confirm [switch]

Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.


### WhatIf [switch]

Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.


### UseTransaction [switch]

Includes the command in the active transaction.
This parameter is valid only when a transaction is in progress.
For more information, see Includes the command in the active transaction.
This parameter is valid only when a transaction is in progress.
For more information, see



## INPUTS
### System.Management.Automation.PSObject

You can pipe objects to Set-ItemProperty.

## OUTPUTS
### None or System.Management.Automation.PSCustomObject

When you use the PassThru parameter, Set-ItemProperty generates a PSCustomObject object that represents the item that was changed and its new property value.
Otherwise, this cmdlet does not generate any output.

## NOTES
The Set-ItemProperty cmdlet is designed to work with the data exposed by any provider.
To list the providers available in your session, type "Get-PSProvider".
For more information, see about_Providers.


## EXAMPLES
### -------------------------- EXAMPLE 1 --------------------------

```powershell
PS C:\>set-itemproperty -path c:\GroupFiles\final.doc -name IsReadOnly -value $true

```
This command sets the value of the IsReadOnly property of the final.doc file to true.

The command uses the Set-ItemProperty cmdlet to change the value of the property of the final.doc file.
It uses the Path parameter to specify the file.
It uses the Name parameter to specify the name of the property and the Value parameter to specify the new value.

The $true automatic variable represents a value of TRUE.
For more information, see about_Automatic_Variables.

The file is a System.IO.FileInfo object and IsReadOnly is just one of its properties.
To see all of the properties and methods of a FileInfo object, pipe the file to the Get-Member cmdlet.
For example, "final.doc | get-member".






### -------------------------- EXAMPLE 2 --------------------------

```powershell
PS C:\>set-itemproperty -path HKLM:\Software\MyCompany -name NoOfEmployees -value 823
PS C:\>get-itemproperty -path HKLM:\Software\MyCompany

PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 823
PS C:\>set-itemproperty -path HKLM:\Software\MyCompany -name NoOfEmployees -value 824
PS C:\>get-itemproperty -path HKLM:\Software\MyCompany
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824

```
This example shows how to use Set-ItemProperty to create a new registry entry and to assign a value to the entry.
It creates the NoOfEmployees entry in the MyCompany key in HKLM\Software key and sets its value to 823.

Because registry entries are considered to be properties of the registry keys (which are items), you use Set-ItemProperty to create registry entries, and to establish and change their values.

The first command uses the Set-ItemProperty cmdlet to create the registry entry.
It uses the Path parameter to specify the path to the HKLM: drive and the Software\MyCompany key.
It uses the Name parameter to specify the entry name and the Value parameter to specify a value.

The second command uses the Get-ItemProperty cmdlet to see the new registry entry.
If you use the Get-Item or Get-ChildItem cmdlets, the entries do not appear because they are properties of a key, not items or child items.

The third command changes the value of the NoOfEmployees entry to 824.

You can also use the New-ItemProperty cmdlet to create the registry entry and its value and then use Set-ItemProperty to change the value.

For more information about the HKLM: drive, type "get-help get-psdrive".
For more information about using Windows PowerShell to manage the registry, type "get-help registry".






### -------------------------- EXAMPLE 3 --------------------------

```powershell
PS C:\>get-childitem weekly.txt | set-itemproperty -name IsReadOnly -value $true

```
These commands show how to use a pipeline operator (|) to send an item to Set-ItemProperty.

The first part of the command uses the Get-ChildItem cmdlet to get an object that represents the Weekly.txt file.
The command uses a pipeline operator to send the file object to Set-ItemProperty.
The Set-ItemProperty command uses the Name and Value parameters to specify the property and its new value.

This command is equivalent to using the InputObject parameter to specify the object that Get-ChildItem gets.







## RELATED LINKS

[Online Version:](http://go.microsoft.com/fwlink/p/?linkid=293911)

[Clear-ItemProperty]()

[Copy-ItemProperty]()

[Get-ItemProperty]()

[Move-ItemProperty]()

[New-ItemProperty]()

[Remove-ItemProperty]()

[Rename-ItemProperty]()

[about_Providers]()
