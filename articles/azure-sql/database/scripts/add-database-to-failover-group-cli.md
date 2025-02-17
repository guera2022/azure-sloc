---
title: "Azure CLI example: Add a database to a failover group" 
description: Use this Azure CLI example script to create a database in Azure SQL Database, add it to an auto-failover group, and test failover. 
services: sql-database
ms.service: sql-database
ms.subservice: high-availability
ms.custom: sqldbrb=1, devx-track-azurecli
ms.devlang: azurecli
ms.topic: sample
author: emlisa
ms.author: emlisa
ms.reviewer: kendralittle, mathoma
ms.date: 12/23/2021
---

# Use Azure CLI to add a database to a failover group

[!INCLUDE[appliesto-sqldb](../../includes/appliesto-sqldb.md)]

This Azure CLI script example creates a database in Azure SQL Database, creates a failover group, adds the database to it, and tests failover.

If you choose to install and use Azure CLI locally, this topic requires that you are running Azure CLI version 2.0 or later. Run `az --version` to find the version. If you need to install or upgrade, see [Install Azure CLI](/cli/azure/install-azure-cli).

> [!IMPORTANT]
> When running Bash on Windows, run this script from within a Docker container.

## Sample script

### Launch Azure Cloud Shell

The Azure Cloud Shell is a free interactive shell that you can use to run the steps in this article. It has common Azure tools preinstalled and configured to use with your account.

To open the Cloud Shell, just select **Try it** from the upper right corner of a code block. You can also launch Cloud Shell in a separate browser tab by going to [https://shell.azure.com](https://shell.azure.com).

When Cloud Shell opens, verify that **Bash** is selected for your environment. Subsequent sessions will use Azure CLI in a Bash environment, Select **Copy** to copy the blocks of code, paste it into the Cloud Shell, and press **Enter** to run it.

### Sign in to Azure

Cloud Shell is automatically authenticated under the initial account signed-in with. Use the following script to sign in using a different subscription, replacing `<Subscription ID>` with your Azure Subscription ID.  [!INCLUDE [quickstarts-free-trial-note](../../../../includes/quickstarts-free-trial-note.md)]

```azurecli-interactive
subscription="<subscriptionId>" # add subscription here

az account set -s $subscription # ...or use 'az login'
```

For more information, see [set active subscription](/cli/azure/account#az_account_set) or [log in interactively](/cli/azure/reference-index#az_login)

### Run the script

:::code language="azurecli" source="~/azure_cli_scripts/sql-database/failover-groups/add-single-db-to-failover-group-az-cli.sh" range="4-47":::

### Clean up resources

Use the following command to remove the resource group and all resources associated with it using the [az group delete](/cli/azure/vm/extension#az_vm_extension_set) command- unless you have additional needs for these resources. Some of these resources may take a while to create, as well as to delete.

```azurecli
az group delete --name $resourceGroup
```

## Sample reference

This script uses the following commands. Each command in the table links to command-specific documentation.

| Command | Description |
|---|---|
| [az sql db](/cli/azure/sql/db) | Database commands. |
| [az sql failover-group](/cli/azure/sql/failover-group) | Failover group commands. |

## Next steps

For more information on Azure CLI, see [Azure CLI documentation](/cli/azure).

Additional SQL Database CLI script samples can be found in the [Azure SQL Database documentation](../az-cli-script-samples-content-guide.md).
