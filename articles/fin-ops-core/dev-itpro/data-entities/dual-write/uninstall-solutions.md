---
title: Desinstalar soluções de orquestração de aplicativos com gravação dupla
description: Este tópico descreve como desinstalar as soluções de orquestração de aplicativos com gravação dupla.
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: 781b2cb19a563d5712fa65718c93bfdc242f0c4a
ms.sourcegitcommit: abfaef124c8747827d6f297821f01f1f6fbca6b7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455315"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>Desinstalar soluções de orquestração de aplicativos com gravação dupla

[!include [banner](../../includes/banner.md)]

Este tópico descreve como desinstalar as soluções de orquestração de aplicativos com gravação dupla.

Alguns clientes instalam acidentalmente o pacote de orquestração de aplicativos com gravação dupla que instala várias soluções no ambiente do Microsoft Dataverse. A instalação das soluções estranhas no pacote pode causar problemas inesperados e indesejados.

Para corrigir problemas relacionados à instalação do pacote de orquestração de aplicativos com gravação dupla, desinstale as soluções com gravação dupla indesejadas na seguinte ordem:

1. Dynamics365FinanceAndOperationsAnchor_managed
1. msdyn_OneFSSCM_managed (if present)
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps_managed
1. Dynamics365Notes_managed (Para desinstalar essa solução, é necessário abrir um tíquete de suporte com a Microsoft.)
1. DualWriteCore_managed
1. Dynamics365AssetManagementApp_managed
1. Dynamics365AssetManagement_managed
1. Dynamics365SupplyChainExtended_managed
1. Dynamics365FinanceExtended_managed
1. HCMCommon_managed
1. Dynamics365FinanceAndOperationsCommon_managed
1. Dynamics365Company_managed
1. CurrencyExchangeRates_managed
1. msdyn_AssetCommon_managed
1. FieldServiceCommon_managed

Se as soluções de participante e de catálogo de endereços global tiverem sido instaladas, desinstale as soluções na seguinte ordem:

1. Dynamics365FinanceAndOperationsAnchor
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps
1. msdyn_DualWriteCore
1. Dynamics365AssetManagementApp
1. Dynamics365AssetManagement
1. Dynamics365SupplyChainExtended
1. Dynamics365FinanceExtended
1. HCMCommon
1. Dynamics365FinanceAndOperationsCommon
1. Participante
1. Dynamics365Company_managed
1. CurrencyExchangeRates
1. msdyn_AssetCommon
1. FieldServiceCommon
