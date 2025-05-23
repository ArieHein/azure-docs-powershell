---
external help file: Az.EdgeOrder-help.xml
Module Name: Az.EdgeOrder
online version: https://learn.microsoft.com/powershell/module/Az.EdgeOrder/new-azedgeordercontactdetailsobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/EdgeOrder/help/New-AzEdgeOrderContactDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/EdgeOrder/help/New-AzEdgeOrderContactDetailsObject.md
---

# New-AzEdgeOrderContactDetailsObject

## SYNOPSIS
Create an in-memory object for ContactDetails.

## SYNTAX

```
New-AzEdgeOrderContactDetailsObject -ContactName <String> -EmailList <String[]> -Phone <String>
 [-Mobile <String>] [-PhoneExtension <String>] [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for ContactDetails.

## EXAMPLES

### Example 1: Contact details object
```powershell
$contactDetail = New-AzEdgeOrderContactDetailsObject -ContactName ContactName -EmailList @("emailId") -Phone Phone
```

```output
ContactName    : random
EmailList      : {"emailId"}
Mobile         :
Phone          : 1234567890
PhoneExtension :
```

Creates a in-memory contact details object

## PARAMETERS

### -ContactName
Contact name of the person.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailList
List of Email-ids to be notified about job progress.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mobile
Mobile number of the contact person.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Phone
Phone number of the contact person.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhoneExtension
Phone extension number of the contact person.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.ContactDetails

## NOTES

## RELATED LINKS
