---
title: Verwalten von Azure-Abonnements mit Azure PowerShell | Microsoft-Dokumentation
description: Verwalten von Azure-Abonnements mit Azure PowerShell
keywords: Azure PowerShell, Abonnement
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/30/2017
ms.openlocfilehash: 68d03ec8d1a86fb3b270d02a4697bbf9af847f2d
ms.sourcegitcommit: 20af779cd523c758d40e23d60eb989a4ef982d5c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="manage-multiple-azure-subscriptions"></a><span data-ttu-id="614a9-104">Verwalten mehrerer Azure-Abonnements</span><span class="sxs-lookup"><span data-stu-id="614a9-104">Manage multiple Azure subscriptions</span></span>

<span data-ttu-id="614a9-105">Falls Sie noch keine Erfahrung mit Azure haben, verfügen Sie wahrscheinlich nur über ein einzelnes Abonnement.</span><span class="sxs-lookup"><span data-stu-id="614a9-105">If you are brand new to Azure, you probably only have a single subscription.</span></span> <span data-ttu-id="614a9-106">Wenn Sie Azure hingegen schon eine Weile verwenden, haben Sie möglicherweise bereits mehrere Azure-Abonnements erstellt.</span><span class="sxs-lookup"><span data-stu-id="614a9-106">But if you have been using Azure for a while, you may have created multiple Azure subscriptions.</span></span> <span data-ttu-id="614a9-107">Sie können Azure PowerShell so konfigurieren, dass Befehle für ein bestimmtes Abonnement ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="614a9-107">You can configure Azure PowerShell to execute commands against a particular subscription.</span></span>

1. <span data-ttu-id="614a9-108">Rufen Sie eine Liste mit allen Abonnements in Ihrem Konto ab.</span><span class="sxs-lookup"><span data-stu-id="614a9-108">Get a list of all subscriptions in your account.</span></span>

    ```powershell
    Get-AzureRmSubscription
    ```

    ```
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Production Subscription
    CurrentStorageAccount :

    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My DevTest Subscription
    CurrentStorageAccount :

    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Demos
    CurrentStorageAccount :
    ```

2. <span data-ttu-id="614a9-109">Legen Sie das Standardabonnement fest.</span><span class="sxs-lookup"><span data-stu-id="614a9-109">Set the default.</span></span>

    ```powershell
    Select-AzureRmSubscription -SubscriptionName "My Demos"
    ```

3. <span data-ttu-id="614a9-110">Überprüfen Sie die Änderung durch Ausführen des Cmdlets `Get-AzureRmContext`.</span><span class="sxs-lookup"><span data-stu-id="614a9-110">Verify the change by running the `Get-AzureRmContext` cmdlet.</span></span>

    ```powershell
    Get-AzureRmContext
    ```

    ```
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Demos
    CurrentStorageAccount :
    ```

<span data-ttu-id="614a9-111">Nachdem Sie Ihr Standardabonnement festgelegt haben, werden alle weiteren Azure PowerShell-Befehle für dieses Abonnement ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="614a9-111">Once you set your default subscription, all subsequent Azure PowerShell commands run against this subscription.</span></span>
