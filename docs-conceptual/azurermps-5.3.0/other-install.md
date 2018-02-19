---
title: "Andere Installationsmöglichkeiten für Azure PowerShell | Microsoft-Dokumentation"
description: Hier erfahren Sie, wie Sie Azure PowerShell mithilfe des MSI-Pakets oder des Webplattform-Installers installieren.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 8a88cce312b4cca002c342c04e1f97b966ae3d2f
ms.sourcegitcommit: 72f56597f0329d35779a3ea4ccea6293f0fd2502
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="other-installation-methods"></a>Andere Installationsmethoden

Für Azure PowerShell stehen unterschiedliche Installationsmethoden zur Verfügung. Bevorzugt wird die Kombination aus „PowerShellGet“ und PowerShell-Katalog. Azure PowerShell kann mithilfe des Webplattform-Installers (WebPI) oder unter Verwendung der bei GitHub verfügbaren MSI-Datei unter Windows installiert werden. Azure PowerShell kann auch in einem Docker-Container installiert werden.

## <a name="install-on-windows-using-the-web-platform-installer"></a>Installieren unter Windows mit dem Webplattform-Installer

Die Vorgehensweise zum Installieren der neuesten Azure PowerShell-Version über WebPI hat sich im Vergleich zu früheren Versionen nicht geändert.
Laden Sie das [Azure PowerShell-WebPI-Paket](http://aka.ms/webpi-azps) herunter, und starten Sie die Installation.

> [!NOTE]
> Wenn Sie bereits Azure-Module aus dem PowerShell-Katalog installiert haben, entfernt das Installationsprogramm diese automatisch. Dadurch wird sichergestellt, dass nur eine einzelne Version von Azure PowerShell installiert ist, was Ihre Umgebung vereinfacht. Es gibt jedoch Szenarien, in denen mehrere gleichzeitig installierte Versionen benötigt werden.
>
> PowerShell-Katalogmodule werden unter `$env:ProgramFiles\WindowsPowerShell\Modules` installiert. Der WebPI-Installer installiert Azure-Module dagegen unter `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.
>
> Im Falle eines Installationsfehlers können Sie die Azure*-Ordner aus dem Ordner `$env:ProgramFiles\WindowsPowerShell\Modules` entfernen und die Installation wiederholen.

Nach Abschluss der Installation sollte Ihre `$env:PSModulePath` -Einstellung die Verzeichnisse mit den Azure PowerShell-Cmdlets enthalten. Mit dem folgenden Befehl können Sie überprüfen, ob Azure PowerShell ordnungsgemäß installiert wurde.

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> Es gibt ein bekanntes Problem, das bei der Installation per WebPI auftreten kann. Wenn Ihr Computer aufgrund von Systemupdates oder anderen Installationen neu gestartet werden muss, wird bei Updates für `$env:PSModulePath` unter Umständen der Installationspfad von Azure PowerShell nicht einbezogen.

Nach der Installation wird beim Ladevorgang oder beim Ausführen von Cmdlets möglicherweise folgende Fehlermeldung angezeigt:

```
PS C:\> Login-AzureRmAccount
Login-AzureRmAccount : The term 'Login-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Login-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Login-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

Starten Sie zum Beheben dieses Fehlers den Computer neu, oder importieren Sie das Modul unter Verwendung des vollqualifizierten Pfads. Beispiel: 

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-on-windows-using-the-msi-package"></a>Installieren unter Windows mithilfe des MSI-Pakets

Azure PowerShell kann mithilfe der bei [GitHub](https://aka.ms/azps-release) verfügbaren MSI-Datei installiert werden. Ältere installierte Versionen von Azure-Modulen werden vom Installationsprogramm automatisch entfernt. Das MSI-Paket installiert Module unter `$env:ProgramFiles\WindowsPowerShell\Modules`, erstellt aber keine versionsspezifischen Ordner.

## <a name="install-in-a-docker-container"></a>Installieren in einem Docker-Container

Wir behalten ein mit Azure PowerShell vorkonfiguriertes Docker-Image bei.

Führen Sie den Container mit `docker run` aus.

```powershell
docker run azuresdk/azure-powershell
```

Darüber hinaus behalten wir eine Teilmenge der Cmdlets als PowerShell Core-Container bei.

Verwenden Sie für Mac/Linux das `latest`-Image.

```bash
docker run azuresdk/azure-powershell-core:latest
```

Verwenden Sie für Windows das `nanoserver`-Image.

```powershell
docker run azuresdk/azure-powershell-core:nanoserver
```

Azure PowerShell wurde über `Install-Module` aus dem [PowerShell-Katalog](https://www.powershellgallery.com/) installiert.
