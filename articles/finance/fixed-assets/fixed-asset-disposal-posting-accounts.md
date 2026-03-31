---
title: Fixed asset disposal posting accounts
description: Learn how to set up General ledger posting accounts for disposing of assets. The ledger account is credited for the disposal value of the fixed assets.
author: moaamer
ms.author: moaamer
ms.topic: article
ms.date: 06/20/2017
ms.reviewer: kfend
audience: Application User
ms.search.region: Global
ms.search.validFrom: 2016-02-28
ms.search.form: AssetPosting
ms.dyn365.ops.version: AX 7.0.0
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
---

# Fixed asset disposal posting accounts

[!include [banner](../includes/banner.md)]

This article explains how to set up posting accounts when you dispose of fixed assets. It covers disposal by sale and disposal by scrap, including the disposal parameters that control how accounting entries are generated.

## Set up disposal posting accounts

To set up posting accounts for asset disposal, go to **Fixed assets \> Setup \> Fixed asset posting profiles**. On the **Ledger accounts** FastTab, select **Disposal – sale** or **Disposal – scrap** to define the accounts for each disposal method.

For both transaction types (sale and scrap), the ledger account is credited for the disposal value of the fixed asset. The debit is posted to an offset account, which might be, for example, a bank account. If a fixed asset is sold to a customer through a free text invoice, the customer account is used as the offset (debit) instead of a bank account. For more information, see [Dispose of a fixed asset using a free text invoice](tasks/dispose-fixed-asset-free-text-invoice.md).

### Disposal parameters

After you select **Disposal – sale** or **Disposal – scrap** in the posting profile, select **Disposal** and then **Sale** or **Scrap** to configure detailed disposal parameters. These parameters control how the system reverses the asset's net book value during disposal.

The following table describes the key fields on the **Disposal parameters** page.

| Field | Description |
|---|---|
| **Post value** | The transaction type that determines how the asset value is reversed during disposal. Available options include **Net book value**, **Acquisition value**, **Acquisition this year**, **Acquisition prior years**, **Depreciation (this year)**, **Depreciation (prior years)**, and other transaction types if applicable. |
| **Sales value type** | (Disposal – sale only) Controls how the system accounts for the sales price. Select **Net book value** to post the sale proceeds against the net book value, or **Acquisition value** to post the sale proceeds against the original acquisition value. |

### Post disposal transactions in detail

The **Post disposal transactions in detail** option on the **Fixed assets parameters** page (**Fixed assets \> Setup \> Fixed assets parameters**) determines the level of detail that the system uses for the accounting entries generated during disposal.

- **Yes** – The system generates separate accounting entries that differentiate acquisition values by year (**Acquisition this year** and **Acquisition prior years**) and depreciation by year (**Depreciation this year** and **Depreciation prior years**). You must define posting types for each of these on the **Fixed asset posting profiles** page. Posting fails if these accounts aren't defined.
- **No** – The system posts a single summarized entry that uses the **Acquisition value** posting type and the **Net book value** posting type that are defined in the disposal posting profile.

> [!NOTE]
> You can't define a main account for both **Acquisition value** and **Acquisition this year**/**Acquisition prior years** posting types for the same combination in the disposal posting profile. The system validates this and prevents duplicate setup.

## Derived books

If the disposed asset's book includes a derived book, the system automatically creates the corresponding disposal transaction in the derived book when the disposal is posted. The derived book transaction posts for the same amount and at the same time as the primary book transaction.

## Related articles

- [Dispose of a fixed asset as scrap](dispose-of-a-fixed-asset-as-scrap.md)
- [Dispose of a fixed asset using a free text invoice](tasks/dispose-fixed-asset-free-text-invoice.md)
- [Fixed assets integration with Accounts receivable](fixed-asset-integration.md#accounts-receivable)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
