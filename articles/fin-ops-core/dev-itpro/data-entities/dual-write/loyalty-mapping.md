---
title: Cartões-fidelidade do cliente e pontos de premiação
description: Este tópico descreve a integração de dados sobre cartões de fidelidade do cliente e pontos de recompensa em gravação dupla.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 39e1d5b0a73b198b164e51a18222dbd985192070
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568019"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Cartões-fidelidade do cliente e pontos de premiação

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

As empresas classificam os clientes e fornecem serviços sofisticados, com base nos padrões de compras e gastos dos clientes. Por exemplo, o Dynamics 365 Commerce tem a infraestrutura e as funções para facilitar e lidar com cartões de fidelidade do cliente, pontos de recompensa, preços com base na fidelidade e experiências de compra com base em recompensas. Quando dados sobre cartões de fidelidade do cliente e pontos de recompensa no Commerce são sincronizados com o Dataverse, os aplicativos de participação do cliente podem usar esses dados. Por exemplo, os usuários do Dynamics 365 Customer Service podem usar os dados para fornecer os mesmos serviços sofisticados por meio do suporte técnico.

## <a name="templates"></a>Modelos

| Aplicativos Finance and Operations | Aplicativos controlados por modelos no Dynamics 365 | descrição |
|-----------------------------|-----------------------------------|-------------|
| Cartão-fidelidade                | msdyn\_loyaltycards               | Este modelo sincroniza informações sobre cartões de fidelidade do cliente. |
| Pontos de premiação de fidelidade       | msdyn\_loyaltyrewardpoints        | Este modelo sincroniza informações sobre pontos de recompensa do cliente. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]