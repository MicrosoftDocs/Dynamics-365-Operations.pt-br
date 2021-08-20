---
title: Cartões-fidelidade do cliente e pontos de premiação
description: Este tópico descreve a integração de dados sobre cartões de fidelidade do cliente e pontos de recompensa em gravação dupla.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: d20dca3e8f15d04b85bcdf102dda8794c68dc2d54acb65dbd0088da1e6c6cdc5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765089"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Cartões-fidelidade do cliente e pontos de premiação

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

As empresas classificam os clientes e fornecem serviços sofisticados, com base nos padrões de compras e gastos dos clientes. Por exemplo, o Dynamics 365 Commerce tem a infraestrutura e as funções para facilitar e lidar com cartões de fidelidade do cliente, pontos de recompensa, preços com base na fidelidade e experiências de compra com base em recompensas. Quando dados sobre cartões de fidelidade do cliente e pontos de recompensa no Commerce são sincronizados com o Dataverse, os aplicativos de participação do cliente podem usar esses dados. Por exemplo, os usuários do Dynamics 365 Customer Service podem usar os dados para fornecer os mesmos serviços sofisticados por meio do suporte técnico.

## <a name="templates"></a>Modelos

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement     | descrição
|-----------------------------|-----------------------------------|-------------|
[Cartão-fidelidade](mapping-reference.md#149) | msdyn_loyaltycards | Este modelo sincroniza informações sobre cartões de fidelidade do cliente. |
[Níveis de fidelidade](mapping-reference.md#226) | msdyn_loyaltylevels | Este modelo sincroniza informações sobre pontos de recompensa do cliente. |
[Pontos de premiação de fidelidade](mapping-reference.md#150) | msdyn_loyaltyrewardpoints | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
