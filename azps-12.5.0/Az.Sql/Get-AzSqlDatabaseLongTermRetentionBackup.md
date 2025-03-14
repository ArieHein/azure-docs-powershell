---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://learn.microsoft.com/powershell/module/az.sql/get-azsqldatabaselongtermretentionbackup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlDatabaseLongTermRetentionBackup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlDatabaseLongTermRetentionBackup.md
---

# Get-AzSqlDatabaseLongTermRetentionBackup

## SYNOPSIS
Gets one or more long term retention backups.

## SYNTAX

### Location (Default)
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ResourceGroupName <String>]
 [-OnlyLatestPerDatabase] [-DatabaseState <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ServerName
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ServerName] <String> [-DatabaseName <String>]
 [-ResourceGroupName <String>] [-OnlyLatestPerDatabase] [-DatabaseState <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BackupName
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ServerName] <String> -DatabaseName <String>
 [-BackupName] <String> [-ResourceGroupName <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### GetBackupByResourceId
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ResourceId] <String> [-BackupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GetBackupsByResourceId
```
Get-AzSqlDatabaseLongTermRetentionBackup [-Location] <String> [-ResourceId] <String> [-OnlyLatestPerDatabase]
 [-DatabaseState <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GetBackupByInputObject
```
Get-AzSqlDatabaseLongTermRetentionBackup [-InputObject] <AzureSqlDatabaseModel> [-BackupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GetBackupsByInputObject
```
Get-AzSqlDatabaseLongTermRetentionBackup [-InputObject] <AzureSqlDatabaseModel> [-OnlyLatestPerDatabase]
 [-DatabaseState <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzSqlDatabaseLongTermRetentionBackup** cmdlet gets all long term retention backups for a location, server, or database or gets a specific long term retention backup.

## EXAMPLES

### Example 1: Get all backups for a location
```powershell
Get-AzSqlDatabaseLongTermRetentionBackup -Location northeurope
```

```output
BackupExpirationTime			 : 3/22/2018 5:50:55 AM
BackupName						 : b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
BackupTime						 : 3/15/2018 5:50:55 AM
DatabaseName					 : database01
DatabaseDeletionTime			 :
Location						 : northeurope
ResourceId						 : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
ServerName						 : server01
ServerCreateTime				 : 2/29/2018 12:12:19 AM
ResourceGroupName                : 
BackupStorageRedundancy			 : Geo

BackupExpirationTime			 : 3/22/2018 11:43:18 PM
BackupName						 : c2c2c2c2-dddd-eeee-ffff-a3a3a3a3a3a3;131656309980000000
BackupTime						 : 3/15/2018 11:43:18 PM
DatabaseName					 : database02
DatabaseDeletionTime			 : 3/18/2018 4:36:00 PM
Location						 : northeurope
ResourceId						 : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server02/longTermRetentionDatabases/database02/longTermRetentionBackups/c2c2c2c2-dddd-eeee-ffff-a3a3a3a3a3a3;131656309980000000
ServerName						 : server02
ServerCreateTime				 : 2/28/2018 12:12:19 AM
ResourceGroupName                : 
BackupStorageRedundancy			 : Geo
```

This command gets all long term retention backups for all databases (which may be alive or deleted) in southeastasia, resource group will be set only if server is live.

### Example 2: Get all backups for a location under a resource group
```powershell
Get-AzSqlDatabaseLongTermRetentionBackup -Location northeurope -ResourceGroupName resourceGroup01
```

```output
BackupExpirationTime			 : 3/22/2018 5:50:55 AM
BackupName						     : b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
BackupTime						     : 3/15/2018 5:50:55 AM
DatabaseName					     : database01
DatabaseDeletionTime			 :
Location						       : northeurope
ResourceId						     : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
ServerName						     : server01
ServerCreateTime			  	 : 2/29/2018 12:12:19 AM
ResourceGroupName          : resourceGroup01
BackupStorageRedundancy		 : Geo
```

This command gets all long term retention backups for all databases (which may be alive or deleted) under a resource group in northeurope.

### Example 3: Get a specific long term retention backup
```powershell
Get-AzSqlDatabaseLongTermRetentionBackup -Location northeurope -ServerName server01 -DatabaseName database01 -BackupName "b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000"
```

```output
BackupExpirationTime			 : 3/22/2018 5:50:55 AM
BackupName						     : b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
BackupTime						     : 3/15/2018 5:50:55 AM
DatabaseName					     : database01
DatabaseDeletionTime			 :
Location						       : northeurope
ResourceId					       : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
ServerName						     : server01
ServerCreateTime			  	 : 2/29/2018 12:12:19 AM
ResourceGroupName          : 
BackupStorageRedundancy		 : Geo
```

This command gets the backup with name b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000

### Example 4: Get all long term retention backups for a database
```powershell
Get-AzSqlDatabase -ResourceGroupName resourcegroup01 -ServerName server01 -DatabaseName database01 | Get-AzSqlDatabaseLongTermRetentionBackup
```

```output
BackupExpirationTime			 : 3/22/2018 5:50:55 AM
BackupName						     : b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
BackupTime						     : 3/15/2018 5:50:55 AM
DatabaseName					     : database01
DatabaseDeletionTime			 :
Location						       : northeurope
ResourceId						     : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
ServerName						     : server01
ServerCreateTime				   : 2/29/2018 12:12:19 AM
ResourceGroupName          : 
BackupStorageRedundancy		 : Geo
```

This command gets all long term retention backups for database01

### Example 5: Get long term retention backups using filtering
```powershell
Get-AzSqlDatabaseLongTermRetentionBackup -Location northeurope -ServerName server01 -DatabaseName database01 -BackupName "601061b7*"
```

```output
BackupExpirationTime			 : 3/22/2018 11:43:18 PM
BackupName					       : d3d3d3d3-eeee-ffff-aaaa-b4b4b4b4b4b4;131656309980000000
BackupTime						     : 3/15/2018 11:43:18 PM
DatabaseName					     : database02
DatabaseDeletionTime			 : 3/18/2018 4:36:00 PM
Location						       : northeurope
ResourceId					       : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/resourcegroup01/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database02/longTermRetentionBackups/d3d3d3d3-eeee-ffff-aaaa-b4b4b4b4b4b4;131656309980000000
ServerName						     : server01
ServerCreateTime				   : 2/28/2018 12:12:19 AM
ResourceGroupName          : 
BackupStorageRedundancy		 : Geo

BackupExpirationTime			 : 3/22/2018 5:50:55 AM
BackupName						     : b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
BackupTime						     : 3/15/2018 5:50:55 AM
DatabaseName					     : database01
DatabaseDeletionTime			 :
Location						       : northeurope
ResourceId						     : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/resourcegroup01/providers/Microsoft.Sql/locations/northeurope/longTermRetentionServers/server01/longTermRetentionDatabases/database01/longTermRetentionBackups/b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2;131655666550000000
ServerName						     : server01
ServerCreateTime				   : 2/29/2018 12:12:19 AM
ResourceGroupName          : 
BackupStorageRedundancy		 : Geo
```

This command gets all backups with name that starts with "601061b7"

## PARAMETERS

### -BackupName
The name of the backup.

```yaml
Type: System.String
Parameter Sets: BackupName, GetBackupByResourceId, GetBackupByInputObject
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -DatabaseName
The name of the Azure SQL Database the backup is from.

```yaml
Type: System.String
Parameter Sets: ServerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: BackupName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseState
The state of the database whose backups you want to find, Alive, Deleted, or All.
Defaults to All

```yaml
Type: System.String
Parameter Sets: Location, ServerName, GetBackupsByResourceId, GetBackupsByInputObject
Aliases:
Accepted values: All, Deleted, Live

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -InputObject
The database object to get backups for.

```yaml
Type: Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel
Parameter Sets: GetBackupByInputObject, GetBackupsByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
The location of the backups' source server.

```yaml
Type: System.String
Parameter Sets: Location, ServerName, BackupName, GetBackupByResourceId, GetBackupsByResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlyLatestPerDatabase
Whether or not to only get the latest backup per database.
Defaults to false.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Location, ServerName, GetBackupsByResourceId, GetBackupsByInputObject
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The name of the resource group.

```yaml
Type: System.String
Parameter Sets: Location, ServerName, BackupName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
The database Resource ID to get backups for.

```yaml
Type: System.String
Parameter Sets: GetBackupByResourceId, GetBackupsByResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
The name of the Azure SQL Server the backups are under.

```yaml
Type: System.String
Parameter Sets: ServerName, BackupName
Aliases:

Required: True
Position: 1
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseLongTermRetentionBackupModel

## NOTES

## RELATED LINKS

[Update-AzSqlDatabaseLongTermRetentionBackup](./Update-AzSqlDatabaseLongTermRetentionBackup.md)

[Copy-AzSqlDatabaseLongTermRetentionBackup](./Copy-AzSqlDatabaseLongTermRetentionBackup.md)

[Remove-AzSqlDatabaseLongTermRetentionBackup](./Remove-AzSqlDatabaseLongTermRetentionBackup.md)

[Get-AzSqlDatabaseBackupLongTermRetentionPolicy](./Get-AzSqlDatabaseBackupLongTermRetentionPolicy.md)

[Set-AzSqlDatabaseBackupLongTermRetentionPolicy](./Set-AzSqlDatabaseBackupLongTermRetentionPolicy.md)

[SQL Database Documentation](https://learn.microsoft.com/azure/sql-database/)
