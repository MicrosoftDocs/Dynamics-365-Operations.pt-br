---
title: Cartões-fidelidade do cliente e pontos de premiação
description: Este tópico descreve a integração de dados sobre cartões de fidelidade do cliente e pontos de recompensa entre aplicativos do Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: e7e67946930404ab7ba0c7fccf468722f723d675
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172960"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Cartões-fidelidade do cliente e pontos de premiação

[!include [banner](../../includes/banner.md)]



As empresas classificam os clientes e fornecem serviços sofisticados, com base nos padrões de compras e gastos dos clientes. No conjunto de aplicativos do Microsoft Dynamics 365, o Dynamics 365 Commerce possui a infraestrutura e as funções para facilitar e lidar com cartões de fidelidade do cliente, pontos de recompensa, preços com base na fidelidade e experiências de compra com base em recompensas. Quando dados sobre cartões de fidelidade do cliente e pontos de recompensa no Commerce são sincronizados com o Common Data Service, os aplicativos baseados em modelo no Dynamics 365 podem usar esses dados. Por exemplo, os usuários do Dynamics 365 Customer Service podem usar os dados para fornecer os mesmos serviços sofisticados por meio do suporte técnico.

## <a name="templates"></a>Modelos

| Aplicativos Finance and Operations | Aplicativos controlados por modelos no Dynamics 365 | descrição |
|-----------------------------|-----------------------------------|-------------|
| Cartão-fidelidade                | msdyn\_loyaltycards               | Este modelo sincroniza informações sobre cartões de fidelidade do cliente. |
| Pontos de premiação de fidelidade       | msdyn\_loyaltyrewardpoints        | Este modelo sincroniza informações sobre pontos de recompensa do cliente. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
