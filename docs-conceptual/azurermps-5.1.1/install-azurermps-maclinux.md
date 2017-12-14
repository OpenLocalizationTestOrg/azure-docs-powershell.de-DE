---
title: Installieren und Konfigurieren von Azure PowerShell unter macOS und Linux | Microsoft-Dokumentation
description: "Hier erfahren Sie, wie Sie Azure PowerShell für die erste Verwendung unter macOS und Linux installieren und konfigurieren."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 94b39c18acaca7a4b17b5207feed025442665acc
ms.sourcegitcommit: 358d260a867c6ee2e8700b91f776ba4f1b0e24a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a>Installieren und Konfigurieren von Azure PowerShell unter macOS und Linux

Es ist jetzt möglich, PowerShell 6 (Beta) und Azure PowerShell auf anderen Plattformen als Windows zu installieren.
Die Installation von Azure PowerShell unter macOS und Linux unterscheidet sich nicht sehr von der Installation unter Windows, allerdings müssen Sie zuerst PowerShell 6 (Beta) installieren.

> [!NOTE]

> Derzeit liegt sowohl PowerShell 6 (Beta) als auch Azure PowerShell für .NET Core noch in der Betaversion vor.
> Der Support für diese Produkte ist eingeschränkt. Wenn Sie Probleme haben oder Fehler erkennen, melden Sie dies bitte in GitHub.
>
> * [Probleme mit PowerShell 6 (Beta)](https://github.com/PowerShell/PowerShell/issues)
> * [Probleme mit Azure PowerShell](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a>Schritt 1: Installieren von PowerShell 6 (Beta)

Die Installation von PowerShell 6 (Beta) variiert je nach Betriebssystem.
Es ist zwar möglich, PowerShell 6 (Beta) unter Windows zu installieren, doch Thema dieses Artikels ist die Installation unter macOS und Linux. Wenn Sie Azure PowerShell unter Windows verwenden möchten, lesen Sie den Artikel [Installieren und Konfigurieren von Azure PowerShell](./install-azurerm-ps.md) für Windows.

Um **PowerShell 6** (Beta) unter Linux oder macOS zu installieren, müssen Sie:

1. PowerShell für das jeweilige Betriebssystem und die Version von [GitHub](https://github.com/powershell/powershell#get-powershell) herunterladen
2. Die Installationsanweisungen befolgen
   - [Linux](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [macOS](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a>Schritt 2: Installieren von Azure PowerShell für .NET Core

In PowerShell 6 (Beta) ist das PowerShellGet-Modul bereits installiert. Dies vereinfacht die Installation eines beliebigen, im PowerShell-Katalog veröffentlichten Moduls. Um Azure PowerShell zu installieren, öffnen Sie eine neue PowerShell-Sitzung, und führen Sie den folgenden Befehl aus:

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a>Schritt 3: Laden des AzureRM.Netcore-Moduls

Nach der Installation des Moduls müssen Sie das Modul in der PowerShell-Sitzung laden. Module werden wie folgt mit dem Cmdlet `Import-Module` geladen:

```powershell
Import-Module AzureRM.Netcore
```

Nach Abschluss des Imports können Sie das neu installierte Modul testen, indem Sie versuchen, sich mithilfe des folgenden Befehls bei Azure anzumelden:

```powershell
Login-AzureRMAccount
```

Der obige Befehl sollte Sie auffordern, zu `https://aka.ms/devicelogin` zu wechseln und den bereitgestellten Code einzugeben.

## <a name="available-cmdlets"></a>Verfügbare Cmdlets

Die Azure PowerShell-Module für .NET Standard sind immer noch in der Entwicklungsphase. Diese Module bieten nicht den vollständigen Satz der Cmdlets, die für die Windows-Version der Module verfügbar sind. Die folgenden Funktionen werden in AzureRM.Netcore-Module implementiert:

* Kontoverwaltung
  - Melden Sie sich mit dem Microsoft-Konto, Unternehmenskonto oder einem Dienstprinzipal über Microsoft Azure Active Directory an.
  - Speichern Sie die Anmeldeinformationen mit Save-AzureRmContext auf einem Datenträger, und laden Sie gespeicherte Anmeldeinformationen mit Import-AzureRmContext.
* Environment
  - Abrufen der verschiedenen vorkonfigurierten Microsoft Azure-Umgebungen
  - Hinzufügen/Einrichten/Entfernen angepasster Umgebungen (z.B. Ihrer Azure Stack- oder Windows Azure Pack-Umgebungen)
* Cmdlets auf Verwaltungsebene für Azure-Dienste, die Resource Manager- und Service Management-Schnittstellen nutzen.
  - Virtual Machine
  - App Service (Websites)
  - SQL-Datenbank
  - Speicher
  - Netzwerk

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zur Verwendung von Azure PowerShell finden Sie im Artikel [Erste Schritte mit Azure PowerShell](get-started-azureps.md).
