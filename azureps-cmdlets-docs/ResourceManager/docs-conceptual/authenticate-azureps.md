---
title: Anmelden mit Azure PowerShell
description: Anmelden mit Azure PowerShell
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: f6d249ca5bb09c4fe8445ba5b339ffa6012815ed
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2017
---
# <a name="log-in-with-azure-powershell"></a><span data-ttu-id="bcf7f-103">Anmelden mit Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcf7f-103">Log in with Azure PowerShell</span></span>

<span data-ttu-id="bcf7f-104">Azure PowerShell unterstützt mehrere Anmeldemethoden.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-104">Azure PowerShell supports multiple login methods.</span></span> <span data-ttu-id="bcf7f-105">Die einfachste Möglichkeit ist die interaktive Anmeldung über die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-105">The simplest way to get started is to log in interactively at the command line.</span></span>

## <a name="interactive-log-in"></a><span data-ttu-id="bcf7f-106">Interaktive Anmeldung</span><span class="sxs-lookup"><span data-stu-id="bcf7f-106">Interactive log in</span></span>

1. <span data-ttu-id="bcf7f-107">Geben Sie `Login-AzureRmAccount`ein.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-107">Type `Login-AzureRmAccount`.</span></span> <span data-ttu-id="bcf7f-108">Im daraufhin erscheinenden Dialogfeld werden Sie zur Eingabe Ihrer Azure-Anmeldeinformationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-108">You will get dialog box asking for your Azure credentials.</span></span>

2. <span data-ttu-id="bcf7f-109">Geben Sie die dem Konto zugeordnete E-Mail-Adresse und das zugehörige Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-109">Type the email address and password associated with your account.</span></span> <span data-ttu-id="bcf7f-110">Die Anmeldeinformationen werden von Azure authentifiziert und gespeichert, dann wird das Fenster geschlossen.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-110">Azure authenticates and saves the credential information, and then closes the window.</span></span>

## <a name="log-in-with-a-service-principal"></a><span data-ttu-id="bcf7f-111">Anmeldung mit einem Dienstprinzipal</span><span class="sxs-lookup"><span data-stu-id="bcf7f-111">Log in with a service principal</span></span>

<span data-ttu-id="bcf7f-112">Dienstprinzipale ermöglichen die Erstellung nicht interaktiver Konten für die Ressourcenbearbeitung.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-112">Service principals provide a way for you to create non-interactive accounts that you can use to manipulate resources.</span></span> <span data-ttu-id="bcf7f-113">Dienstprinzipale sind vergleichbar mit Benutzerkonten, auf die Sie mithilfe von Azure Active Directory Regeln anwenden können.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-113">Service principals are like user accounts to which you can apply rules using Azure Active Directory.</span></span> <span data-ttu-id="bcf7f-114">Indem Sie einem Dienstprinzipal nur die erforderlichen Mindestberechtigungen erteilen, können Sie Ihre Automatisierungsskripts noch sicherer machen.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-114">By granting the minimum permissions needed to a service principal, you can ensure your automation scripts are even more secure.</span></span>

1. <span data-ttu-id="bcf7f-115">Falls Sie noch nicht über einen Dienstprinzipal verfügen, [erstellen Sie einen](create-azure-service-principal-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="bcf7f-115">If you don't already have a service principal, [create one](create-azure-service-principal-azureps.md).</span></span>

2. <span data-ttu-id="bcf7f-116">Melden Sie sich mit dem Dienstprinzipal an.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-116">Log in with the service principal.</span></span>

    ```powershell
    Login-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
    ```

    <span data-ttu-id="bcf7f-117">Wenn Sie Ihre Mandanten-ID ermitteln möchten, melden Sie sich interaktiv an, und rufen Sie anschließend die Mandanten-ID aus Ihrem Abonnement ab.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-117">To get your TenantId, log in interactively and then get the TenantId from your subscription.</span></span>

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
    ```

## <a name="log-in-to-another-cloud"></a><span data-ttu-id="bcf7f-118">Anmelden bei einer anderen Cloud</span><span class="sxs-lookup"><span data-stu-id="bcf7f-118">Log in to another Cloud</span></span>

<span data-ttu-id="bcf7f-119">Azure-Clouddienste bieten unterschiedliche Umgebungen, die den Datenverarbeitungsvorschriften verschiedener Staaten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-119">Azure cloud services provide different environments that adhere to the data-handling regulations of various governments.</span></span> <span data-ttu-id="bcf7f-120">Wenn Ihr Azure-Konto in einer dieser staatsspezifischen Clouds enthalten ist, müssen Sie die Umgebung angeben, wenn Sie sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="bcf7f-120">If your Azure account is in one the government clouds, you need to specify the environment when you sign in.</span></span> <span data-ttu-id="bcf7f-121">Wenn Ihr Konto beispielsweise in der Cloud für China enthalten ist, melden Sie sich mit dem folgenden Befehl an:</span><span class="sxs-lookup"><span data-stu-id="bcf7f-121">For example, if you account is in the China cloud you sign on using the following command:</span></span>

```powershell
Login-AzureRmAccount -EnvironmentName AzureChinaCloud
```

<span data-ttu-id="bcf7f-122">Verwenden Sie den folgenden Befehl, um eine Liste der verfügbaren Umgebungen zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="bcf7f-122">Use the following command to get a list of available environments:</span></span>

```powershell
Get-AzureRmEnvironment | Select-Object Name
```

```
Name
----
AzureCloud
AzureChinaCloud
AzureUSGovernment
AzureGermanCloud
```

## <a name="learn-more-about-managing-azure-role-based-access"></a><span data-ttu-id="bcf7f-123">Weitere Informationen zum Verwalten des rollenbasierten Zugriffs in Azure</span><span class="sxs-lookup"><span data-stu-id="bcf7f-123">Learn more about managing Azure role-based access</span></span>

<span data-ttu-id="bcf7f-124">Weitere Informationen zur Authentifizierung und Abonnementverwaltung in Azure finden Sie unter [Verwalten von Konten, Abonnements und Administratorrollen](/azure/active-directory/role-based-access-control-configure).</span><span class="sxs-lookup"><span data-stu-id="bcf7f-124">For more information about authentication and subscription management in Azure, see [Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure).</span></span>

<span data-ttu-id="bcf7f-125">Azure PowerShell-Cmdlets für die Rollenverwaltung</span><span class="sxs-lookup"><span data-stu-id="bcf7f-125">Azure PowerShell cmdlets for role management</span></span>

* [<span data-ttu-id="bcf7f-126">Get-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="bcf7f-126">Get-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [<span data-ttu-id="bcf7f-127">Get-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="bcf7f-127">Get-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [<span data-ttu-id="bcf7f-128">New-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="bcf7f-128">New-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [<span data-ttu-id="bcf7f-129">New-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="bcf7f-129">New-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [<span data-ttu-id="bcf7f-130">Remove-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="bcf7f-130">Remove-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [<span data-ttu-id="bcf7f-131">Remove-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="bcf7f-131">Remove-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [<span data-ttu-id="bcf7f-132">Set-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="bcf7f-132">Set-AzureRmRoleDefinition</span></span>](/powershell/moduel/AzureRM.Resources/Set-AzureRmRoleDefinition)
