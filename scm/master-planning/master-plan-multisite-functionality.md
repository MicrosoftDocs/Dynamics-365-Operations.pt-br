---
title: Planejamento mestre e funcionalidade multissite
description: "O planejamento mestre leva em consideração as configurações de dimensões de estoque de local e de depósito."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 19eeee753c15cf2670948ce2c615a112813c16ad
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-and-multisite-functionality"></a>Planejamento mestre e funcionalidade multissite

O planejamento mestre leva em consideração as configurações de dimensões de estoque de local e de depósito. 

A dimensão do site é obrigatória, e você pode definir a dimensão do depósito como obrigatória.

Quando uma dimensão é obrigatória, deve-se inserir um valor de dimensão em todas as transações de estoque. Assim, durante o planejamento mestre, o site e o depósito da demanda inicial são conhecidos. A dimensão do site também é consistente para que durante o detalhamento da demanda de nível inferior, o valor do site não seja alterado.

Quando o depósito não está definido como obrigatório, ele pode não ser conhecido na demanda inicial. O mecanismo de planejamento deve determinar qual depósito usar com base nas configurações definidas para o item, os depósitos individuais e os detalhes da linha de ordem.

Os artigos wiki a seguir descrevem como o mecanismo de planejamento funciona, quando configurações diferentes são feitas, para determinar o depósito a ser usado.

[Planejamento mestre - cobertura de site e depósito, depósito obrigatório](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planejamento mestre - cobertura de site, depósito obrigatório](master-plan-site-coverage-warehouse-mandatory.md)

[Planejamento mestre - cobertura de site e depósito, depósito não obrigatório](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planejamento mestre - cobertura de site, depósito não obrigatório](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planejamento mestre – como a versão da BOM é determinada](master-plan-bom-version-determined.md)

