---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: EAFB9C98-000C-4EAC-A32D-6B0F1939AA2F
online version: https://learn.microsoft.com/powershell/module/az.monitor/get-azmetric
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzMetric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzMetric.md
---

# Get-AzMetric

## SYNOPSIS
Gets the metric values of a resource.

## SYNTAX

### GetWithDefaultParameters (Default)
```
Get-AzMetric [-ResourceId] <String> [-TimeGrain <TimeSpan>] [-StartTime <DateTime>] [-EndTime <DateTime>]
 [-MetricFilter <String>] [-Dimension <String[]>] [[-MetricName] <String[]>] [-DetailedOutput]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetWithFullParameters
```
Get-AzMetric [-ResourceId] <String> [-TimeGrain <TimeSpan>] [-AggregationType <AggregationType>]
 [-StartTime <DateTime>] [-EndTime <DateTime>] [-Top <Int32>] [-OrderBy <String>] [-MetricNamespace <String>]
 [-ResultType <ResultType>] [-MetricFilter <String>] [-Dimension <String[]>] [-MetricName] <String[]>
 [-DetailedOutput] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzMetric** cmdlet gets the metric values for a specified resource.

## EXAMPLES

### Example 1: Get a metric with summarized output
```powershell
Get-AzMetric -ResourceId "/subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/website3" -TimeGrain 00:01:00
```

```output
Id         : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/website3/providers/Microsoft.Insights/metrics/Requests
Name       : 
                LocalizedValue : Requests
                Value          : Requests

Type       : Microsoft.Insights/metrics
Unit       : Count
Data       : {Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue, Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue, 
             Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue, Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue…}
Timeseries : {Microsoft.Azure.Management.Monitor.Models.TimeSeriesElement}
```

This command gets the metric values for website3 with a time grain of 1 minute.

### Example 2: Get a metric with detailed output
```powershell
Get-AzMetric -ResourceId "/subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/website3" -TimeGrain 00:01:00 -DetailedOutput
```

```output
Id         : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/website3/providers/Microsoft.Insights/metrics/Requests
Name       : Microsoft.Azure.Management.Monitor.Models.LocalizableString

Type       : Microsoft.Insights/metrics
Unit       : Count
Data       : {Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue, Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue,
             Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue, Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue…}
Timeseries : {Microsoft.Azure.Management.Monitor.Models.TimeSeriesElement}
```

This command gets the metric values for website3 with a time grain of 1 minute.
The output is detailed.

### Example 3: Get a specified metric
```powershell
Get-AzMetric -ResourceId "/subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/website3" -MetricName "Requests" -TimeGrain 00:01:00
```

```output
Id         : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/website3/providers/Microsoft.Insights/metrics/Requests
Name       : 
                LocalizedValue : Requests
                Value          : Requests

Type       : Microsoft.Insights/metrics
Unit       : Count
Data       : {Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue, Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue,
             Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue, Microsoft.Azure.Commands.Insights.OutputClasses.PSMetricValue…}
Timeseries : {Microsoft.Azure.Management.Monitor.Models.TimeSeriesElement}
```

This command gets detailed output for the Requests metric.

### Example 4: Get summarized output for a specified metric with specified dimension filter
```powershell
$dimFilter = "$(New-AzMetricFilter -Dimension City -Operator eq -Value "Seattle","Toronto") and $(New-AzMetricFilter -Dimension AuthenticationType -Operator eq -Value User)"

Get-AzMetric -ResourceId <ResourceId> -MetricName availabilityResults/availabilityPercentage -TimeGrain 00:05:00 -MetricFilter $dimFilter -StartTime 2024-07-02T00:00:00Z -EndTime 2024-07-02T00:10:00Z -AggregationType Average
```

```output
Id         : [ResourceId]/providers/Microsoft.Insights/metrics/availabilityResults/availabilityPercentage
Name       : 
                LocalizedValue : Availability
                Value          : availabilityResults/availabilityPercentage

Type       : Microsoft.Insights/metrics
Unit       : Percent
Data       : 
Timeseries : {}
```

This command gets summarized output for the PageViews metric with specified dimension filter and aggregation type.

## PARAMETERS

### -AggregationType
The aggregation type of the query

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Monitor.Models.AggregationType]
Parameter Sets: GetWithFullParameters
Aliases:
Accepted values: None, Average, Count, Minimum, Maximum, Total

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

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

### -DetailedOutput
Indicates that this cmdlet displays detailed output.
By default, output is summarized.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Dimension
The metric dimensions to query metrics for

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndTime
Specifies the end time of the query in local time.
The default is the current time.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MetricFilter
Specifies the metric dimension filter to query metrics for.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MetricName
Specifies an array of names of metrics.

```yaml
Type: System.String[]
Parameter Sets: GetWithDefaultParameters
Aliases: MetricNames

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String[]
Parameter Sets: GetWithFullParameters
Aliases: MetricNames

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MetricNamespace
Specifies the metric namespace to query metrics for.

```yaml
Type: System.String
Parameter Sets: GetWithFullParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OrderBy
Specifies the aggregation to use for sorting results and the direction of the sort (Example: sum asc).

```yaml
Type: System.String
Parameter Sets: GetWithFullParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the resource ID of the metric.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResultType
Specifies the result type to be returned (metadata or data).

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Monitor.Models.ResultType]
Parameter Sets: GetWithFullParameters
Aliases:
Accepted values: Data, Metadata

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies the start time of the query in local time.
The default is the current local time minus one hour.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeGrain
Specifies the time grain of the metric as a **TimeSpan** object in the format hh:mm:ss.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Top
Specifies the maximum number of records to retrieve (default:10), to be specified with $filter.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: GetWithFullParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.TimeSpan

### System.Nullable`1[[Microsoft.Azure.Management.Monitor.Models.AggregationType, Microsoft.Azure.Management.Monitor, Version=0.21.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.DateTime

### System.Nullable`1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable`1[[Microsoft.Azure.Management.Monitor.Models.ResultType, Microsoft.Azure.Management.Monitor, Version=0.21.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Insights.OutputClasses.PSMetric

## NOTES

More information about the supported metrics may be found at:
https://learn.microsoft.com/azure/azure-monitor/platform/metrics-supported

## RELATED LINKS

[Get-AzMetricDefinition](./Get-AzMetricDefinition.md)
[New-AzMetricFilter](./New-AzMetricFilter.md)
