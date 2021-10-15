---
title: Visão geral de planejamento mestre e funcionalidade multissite
description: O planejamento mestre leva em consideração as configurações de dimensões de estoque de local e de depósito.
author: ChristianRytt
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2434"
- intro-internal
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edcf35ea0a5be870d8a57cd782664d0a0b77de5c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575671"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>Visão geral de planejamento mestre e funcionalidade multissite

[!include [banner](../includes/banner.md)]

O planejamento mestre leva em consideração as configurações de dimensões de estoque de local e de depósito. 

A dimensão do site é obrigatória, e você pode definir a dimensão do depósito como obrigatória.

Quando uma dimensão é obrigatória, deve-se inserir um valor de dimensão em todas as transações de estoque. Assim, durante o planejamento mestre, o site e o depósito da demanda inicial são conhecidos. A dimensão do site também é consistente para que durante o detalhamento da demanda de nível inferior, o valor do site não seja alterado.

Quando o depósito não está definido como obrigatório, ele pode não ser conhecido na demanda inicial. O mecanismo de planejamento deve determinar qual depósito usar com base nas configurações definidas para o item, os depósitos individuais e os detalhes da linha de ordem.

Os tópicos a seguir descrevem como o mecanismo de planejamento funciona, quando configurações diferentes são feitas, para determinar o depósito a ser usado.

[Planejamento mestre para de site e cobertura de depósito, depósito obrigatório](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planejamento mestre para cobertura de site, depósito obrigatório](master-plan-site-coverage-warehouse-mandatory.md)

[Planejamento mestre para de site e cobertura de depósito, depósito não obrigatório](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planejamento mestre para cobertura de site, depósito não obrigatório](master-plan-site-coverage-warehouse-not-mandatory.md)

[Determinar a versão da BOM](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]