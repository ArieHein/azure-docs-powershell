---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://learn.microsoft.com/powershell/module/az.network/update-azrouteserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzRouteServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzRouteServer.md
---

# Update-AzRouteServer

## SYNOPSIS
Update an Azure RouteServer.

## SYNTAX

### RouteServerNameParameterSet (Default)
```
Update-AzRouteServer -ResourceGroupName <String> -RouteServerName <String>
 [-AllowBranchToBranchTraffic <Boolean>] [-HubRoutingPreference <String>]
 [-VirtualRouterAutoScaleConfiguration <PSVirtualRouterAutoScaleConfiguration>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RouteServerResourceIdParameterSet
```
Update-AzRouteServer [-AllowBranchToBranchTraffic <Boolean>] -ResourceId <String>
 [-HubRoutingPreference <String>]
 [-VirtualRouterAutoScaleConfiguration <PSVirtualRouterAutoScaleConfiguration>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-AzRouteServer** cmdlet switches the branch-to-branch traffic to an Azure RouteServer.

## EXAMPLES

### Example 1
```powershell
Update-AzRouteServer -ResourceGroupName $rgname -RouteServerName $routeServerName -AllowBranchToBranchTraffic 1
```

To enable branch to branch traffic for route server.

### Example 2
```powershell
Update-AzRouteServer -ResourceGroupName $rgname -RouteServerName $routeServerName -AllowBranchToBranchTraffic 0
```

To disable branch to branch traffic for route server.

### Example 3
```powershell
Update-AzRouteServer -ResourceGroupName $rgname -RouteServerName $routeServerName -HubRoutingPreference "AsPath"
```

To change routing preference for route server.

### Example 4
```powershell
$autoscale = New-AzVirtualRouterAutoScaleConfiguration -MinCapacity 3
Update-AzRouteServer -ResourceGroupName $rgname -RouteServerName $routeServerName -VirtualRouterAutoScaleConfiguration $autoscale
```

To update the Routing Infrastructure Units to 3.

## PARAMETERS

### -AllowBranchToBranchTraffic
Flag to allow branch to branch traffic for route server.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HubRoutingPreference
Routing Preference to route traffic

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ExpressRoute, VpnGateway, ASPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The resource group name of the route server.

```yaml
Type: System.String
Parameter Sets: RouteServerNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceId
ResourceId of the route server.

```yaml
Type: System.String
Parameter Sets: RouteServerResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteServerName
The name of the route server.

```yaml
Type: System.String
Parameter Sets: RouteServerNameParameterSet
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -VirtualRouterAutoScaleConfiguration
Autoscale configuration for route server.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualRouterAutoScaleConfiguration
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSRouteServer

## NOTES

## RELATED LINKS
