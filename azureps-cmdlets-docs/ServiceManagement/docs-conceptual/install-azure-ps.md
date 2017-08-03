---
title: Installieren und Konfigurieren des Azure PowerShell-Dienstverwaltungsmoduls | Microsoft-Dokumentation
description: "Hier erfahren Sie, wie Sie Azure PowerShell für die erste Verwendung installieren und konfigurieren."
services: azure
author: sdwheeler
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/06/2017
ms.openlocfilehash: 164af369d49e3044e5409c28d8b6145ebc067313
ms.sourcegitcommit: 020066d68d4ab68da162a4ae0cb4e239241f950f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2017
---
# <a name="installing-the-azure-powershell-service-management-module"></a>Installieren des Azure PowerShell-Dienstverwaltungsmoduls

Die Installation von Azure PowerShell aus dem [PowerShell-Katalog](https://www.powershellgallery.com/) ist die bevorzugte Installationsmethode.

## <a name="step-1-install-powershellget"></a>Schritt 1: Installieren von PowerShellGet

Für die Installation von Komponenten aus dem PowerShell-Katalog ist das PowerShellGet-Modul erforderlich. Stellen Sie sicher, dass Sie über die entsprechende Version von PowerShellGet verfügen und alle anderen Systemanforderungen erfüllt sind. Führen Sie den folgenden Befehl aus, um zu ermitteln, ob PowerShellGet auf Ihrem System installiert ist.

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

Eine Ausgabe wie die folgende sollte angezeigt werden:

```
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

Falls PowerShellGet nicht installiert ist, lesen Sie [Installieren von PowerShellGet](#how-to-get-powershellget).

## <a name="step-2-install-azure-powershell"></a>Schritt 2: Installieren von Azure PowerShell

Führen Sie über die Windows PowerShell-Konsole den folgenden Befehl als Administrator aus:

```powershell
Install-Module Azure
```

Das Azure-Modul ist ein Rollupmodul für die Azure Resource Manager-Cmdlets. Bei der Installation des AzureRM-Moduls werden alle noch nicht installierten Azure-Module aus dem PowerShell-Katalog heruntergeladen und installiert.

Das Azure-Dienstverwaltungsmodul nutzt zum Teil die gleichen Abhängigkeiten wie die Azure PowerShell Resource Manager-Module. Wenn Sie die Azure PowerShell Resource Manager-Module installiert haben, müssen Sie dem Installationsbefehl den Parameter `-AllowClobber` hinzufügen. So können diese gemeinsam genutzten Abhängigkeiten aktualisiert werden. Ohne den Parameter ist die Installation des Moduls nicht erfolgreich.

```powershell
Install-Module Azure -AllowClobber
```

Nach der Installation können Sie das Modul mithilfe des folgenden Befehls importieren:

```powershell
Import-Module Azure
```

## <a name="to-use-the-cmdlets"></a>So verwenden Sie die Cmdlets

Melden Sie sich zunächst bei Ihrem Azure-Konto an, bevor Sie die Cmdlets der Azure-Dienstverwaltung verwenden. Führen Sie dazu den folgenden Befehl aus:

```powershell
Add-AzureAccount
```

Nach der Anmeldung bei Azure erstellt Azure PowerShell einen Kontext für die Sitzung. Dieser Kontext enthält die Azure PowerShell-Umgebung, das Konto, den Mandanten und das Abonnement für alle Cmdlets innerhalb dieser Sitzung. Nun können Sie die folgenden Module verwenden.

## <a name="azure-service-management-cmdlets"></a>Cmdlets der Azure-Dienstverwaltung

Azure PowerShell-Module werden regelmäßig aktualisiert. Sollten Sie feststellen, dass die Cmdlet-Onlinehilfe Cmdlets oder Parameter enthält, die in Ihrem Modul nicht vorhanden sind, laden Sie die neueste Version des Moduls herunter, und installieren Sie sie. Geben Sie Folgendes ein, um die Version Ihres Moduls zu ermitteln: `(Get-Module Azure).Version`.

Beispielskripts zur Automatisierung einiger allgemeiner Aufgaben in Azure finden Sie im [Azure Script Center](http://www.windowsazure.com/documentation/scripts/).

Allgemeine Informationen zum Installieren, Kennenlernen, Verwenden und Anpassen von Windows PowerShell finden Sie unter [Skripterstellung mit Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).

### <a name="how-to-get-powershellget"></a>Installieren von PowerShellGet

|Betriebssystemversion|Installationsanleitung|
|---|---|
|Ich besitze Windows 10 oder Windows Server 2016.|In Windows Management Framework (WMF) 5.0 integriert (im Betriebssystem enthalten)|
|Ich möchte auf PowerShell 5 aktualisieren.|[Installieren Sie die aktuelle Version von WMF.](https://www.microsoft.com/en-us/download/details.aspx?id=54616)|
|Ich nutze eine Windows-Version mit PowerShell 3 oder PowerShell 4.|[Laden Sie die PackageManagement-Module herunter.](http://go.microsoft.com/fwlink/?LinkID=746217)|

<a id="helpmechoose"></a>
### <a name="checking-the-version-of-azure-powershell"></a>Überprüfen der Azure PowerShell-Version

Obwohl empfohlen wird, möglichst bald ein Upgrade auf die neueste Version auszuführen, werden verschiedene Azure PowerShell-Versionen unterstützt. Führen Sie zum Ermitteln der installierten Azure PowerShell-Version `Get-Module AzureRM` in der Befehlszeile aus:

```powershell
Get-Module AzureRM -list | Select-Object Name,Version,Path
```
