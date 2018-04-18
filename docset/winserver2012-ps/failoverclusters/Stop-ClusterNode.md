---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: D9E13DE4-9792-4015-B3F4-87CD1FFC06F0
---

# Stop-ClusterNode

## SYNOPSIS
Stops the Cluster service on a node in a failover cluster.

## SYNTAX

```
Stop-ClusterNode [[-Name] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>] [-Wait <Int32>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-ClusterNode** cmdlet stops the Cluster service on a node in a failover cluster.
If stopping the node brings the cluster below quorum, the operation is not permitted.
To stop the cluster, use the Stop-Cluster cmdlet instead.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Stop-ClusterNode -Name node3
Name                                                                      State 
----                                                                      ----- 
node3                                                                      Down
```

This example stops the Cluster service on the node named node3 of the local cluster.

### EXAMPLE 2
```
PS C:\>Stop-ClusterNode -Name node1 -Cluster cluster2
Name                                                                      State 
----                                                                      ----- 
node1                                                                      Down
```

This example stops the Cluster service on the node named node1 on the cluster named cluster2.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster node to stop.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the cluster node to stop.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait
Specifies the time in seconds to wait for the cmdlet.
If the **Wait** parameter is not specified, then the cmdlet waits for completion.
If `-Wait 0` is specified, then the call is initiated and the cmdlet returns without waiting.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Get-ClusterNode](./Get-ClusterNode.md)

[Remove-ClusterNode](./Remove-ClusterNode.md)

[Resume-ClusterNode](./Resume-ClusterNode.md)

[Start-ClusterNode](./Start-ClusterNode.md)

[Stop-Cluster](./Stop-Cluster.md)

[Suspend-ClusterNode](./Suspend-ClusterNode.md)
