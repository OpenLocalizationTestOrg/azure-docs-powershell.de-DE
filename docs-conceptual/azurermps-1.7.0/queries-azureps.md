---
title: Abfragen von Azure-Ressourcen und Formatieren der Ergebnisse | Microsoft-Dokumentation
description: Hier erfahren Sie, wie Sie in Azure Ressourcenabfragen ausführen und die Ergebnisse formatieren.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/30/2017
ms.openlocfilehash: 93a031ce90352286bb1a5e01dc65e6db7cbe5c7e
ms.sourcegitcommit: 5f0013981fcea1d689649b9a2b2ffe84ae842e56
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="querying-for-azure-resources"></a>Abfragen von Azure-Ressourcen

Abfragen können in PowerShell mithilfe integrierter Cmdlets ausgeführt werden. Cmdlet-Namen haben in PowerShell das Format **_Verb-Nomen_**. Die Abfrage-Cmdlets sind am Verb **_Get_** zu erkennen. Bei den Cmdlet-Nomen handelt es sich um die Arten von Azure-Ressourcen, für die eine dem Cmdlet-Verb entsprechende Aktion ausgeführt wird.


## <a name="selecting-simple-properties"></a>Auswählen einfacher Eigenschaften

In Azure PowerShell ist für jedes Cmdlet eine Standardformatierung definiert. Die am häufigsten verwendeten Eigenschaften für die einzelnen Ressourcentypen werden automatisch in einer Tabelle oder Liste angezeigt. Weitere Informationen zum Formatieren der Ausgabe finden Sie unter [Formatieren von Abfrageergebnissen](formatting-output.md).

Fragen Sie mithilfe des Cmdlets `Get-AzureRmVM` eine Liste mit virtuellen Computern in Ihrem Konto ab.

```powershell
Get-AzureRmVM
```

Die Standardausgabe wird automatisch als Tabelle formatiert.

```
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

Mit dem Cmdlet `Select-Object` können Sie spezifische Eigenschaften auswählen, die für Sie von Interesse sind.

```powershell
Get-AzureRmVM | Select Name,ResourceGroupName,Location
```

```
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

## <a name="selecting-complex-nested-properties"></a>Auswählen komplexer geschachtelter Eigenschaften

Wenn sich die Eigenschaft, die Sie auswählen möchten, tief in der Struktur der JSON-Ausgabe befindet, müssen Sie den vollständigen Pfad zu dieser geschachtelten Eigenschaft angeben. Das folgende Beispiel zeigt, wie Sie den VM-Namen und den Betriebssystemtyp auf der Grundlage des Cmdlets `Get-AzureRmVM` auswählen.

```powershell
Get-AzureRmVM | Select Name,@{Name='OSType'; Expression={$_.StorageProfile.OSDisk.OSType}}
```

```
Name           OSType
----           ------
MyUnbuntu1610   Linux
MyWin2016VM   Windows
```

## <a name="filter-result-using-the-where-object-cmdlet"></a>Filtern von Ergebnissen mithilfe des Cmdlets „Where-Object“

Mit dem Cmdlet `Where-Object` können Sie das Ergebnis auf der Grundlage eines beliebigen Eigenschaftswerts filtern. Im folgenden Beispiel wählt der Filter nur virtuelle Computer aus, deren Name „RGD“ enthält.

```powershell
Get-AzureRmVM | Where ResourceGroupName -like RGD* | Select ResourceGroupName,Name
```

```
ResourceGroupName  Name
-----------------  ----
RGDEMO001          KBDemo001VM
RGDEMO001          KBDemo020
```

Im nächsten Beispiel werden die virtuellen Computer zurückgegeben, bei denen „vmSize“ den Wert „Standard_DS1_V2“ besitzt.

```powershell
Get-AzureRmVM | Where vmSize -eq Standard_DS1_V2
```

```
ResourceGroupName          Name     Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----     --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610   westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM   westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```
