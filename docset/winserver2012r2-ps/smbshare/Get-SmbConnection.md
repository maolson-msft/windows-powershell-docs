---
external help file: SmbConnection.cdxml-help.xml
Module Name: SmbShare
online version: 
schema: 2.0.0
title: Get-SmbConnection
description: 
keywords: powershell, cmdlet
author: brianlic
manager: alanth
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 901BD906-798D-4C09-9C84-4FD2B1E19260
---

# Get-SmbConnection

## SYNOPSIS
Retrieves the connections established from the Server Message Block (SMB) client to the SMB servers.

## SYNTAX

```
Get-SmbConnection [[-ServerName] <String[]>] [[-UserName] <String[]>] [-SmbInstance <SmbInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbConnection** cmdlet retrieves the connections established from the Server Message Block (SMB) client to the SMB servers.
Users can connect to an SMB share using credentials different than the associated logon credentials so that there will be a connection listed per share per user logon per credential used.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-SmbConnection
ServerName          ShareName           UserName             Credential           Dialect             NumOpens 
----------          ---------           --------             ----------           -------             -------- 
Contoso-FS1         VMS5                Contoso\Contoso-HV1$ Contoso\Contoso-HV1$ 3.00                1 
Contoso-FS1         VMS5                NT VIRTUAL MACHI...  Contoso\Contoso-HV1$ 3.00                3 
Contoso-FS          VMS1                Contoso\Contoso-HV1$ Contoso\Contoso-HV1$ 3.00                1 
Contoso-FS          VMS1                NT VIRTUAL MACHI...  Contoso\Contoso-HV1$ 3.00                5 
Contoso-SO          VMS3                Contoso\Contoso-HV1$ Contoso\Contoso-HV1$ 3.00                1 
Contoso-SO          VMS3                NT VIRTUAL MACHI...  Contoso\Contoso-HV1$ 3.00                1 
Contoso-SO          VMS3                NT VIRTUAL MACHI...  Contoso\Contoso-HV1$ 3.00                2
```

This example retrieves the connections established from the SMB client to the SMB servers.

### EXAMPLE 2
```
PS C:\>Get-SmbConnection -ServerName Contoso-FS | Select-Object -Property *
ContinuouslyAvailable : True 
Credential            : Contoso\Contoso-HV1$ 
Dialect               : 3.00 
Encrypted             : False 
NumOpens              : 1 
ServerName            : Contoso-FS 
ShareName             : VMS1 
UserName              : Contoso\Contoso-HV1$ 
PSComputerName        : 
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbConnection 
CimInstanceProperties : {ContinuouslyAvailable, Credential, Dialect, Encrypted...} 
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties 
 
ContinuouslyAvailable : True 
Credential            : Contoso\Contoso-HV1$ 
Dialect               : 3.00 
Encrypted             : False 
NumOpens              : 5 
ServerName            : Contoso-FS 
ShareName             : VMS1 
UserName              : NT VIRTUAL MACHINE\F357A523-592B-4CA5-B61E-C06D5627E1C9 
PSComputerName        : 
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbConnection 
CimInstanceProperties : {ContinuouslyAvailable, Credential, Dialect, Encrypted...} 
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This example retrieves the connections established from the SMB client to the SMB server named Contoso-FS.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies that the connections made to the server are enumerated.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmbInstance
{{Fill SmbInstance Description}}

```yaml
Type: SmbInstance
Parameter Sets: (All)
Aliases: 
Accepted values: Default, CSV

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell� calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies that the connections made by the user are enumerated.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbConnection
The MSFT_SmbConnection object represent the per share per user logon per credentials used to connect.

## NOTES

## RELATED LINKS

[Get-SmbMultichannelConnection](./Get-SmbMultichannelConnection.md)

[Update-SmbMultichannelConnection](./Update-SmbMultichannelConnection.md)
