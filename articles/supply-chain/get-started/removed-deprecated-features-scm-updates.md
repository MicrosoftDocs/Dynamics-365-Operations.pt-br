---
title: Recursos removidos ou obsoletos do Dynamics 365 Supply Chain Management
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção em Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: d4d2805e36f132660152370cbeee856862ad6faa
ms.sourcegitcommit: 069ed5789517b550065e5e2317658fec4027359e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "4689510"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Recursos removidos ou obsoletos do Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Este tópico será atualizado à medida que os novos recursos removidos ou obsoletos forem documentados para Dynamics 365 Supply Chain Management.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento.

> [!NOTE]
> Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Recursos removidos ou substituídos na versão 10.0.15 do Supply Chain Management

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Suporte do Internet Explorer 11 para Dynamics 365 foi substituído

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A partir de dezembro de 2020, o suporte do Internet Explorer 11 da Microsoft para todos os produtos Dynamics 365 é preterido e Internet Explorer 11 não receberá suporte depois de agosto de 2021.<br><br>Isso afetará os clientes que usam os produtos do Dynamics 365 projetados para serem usados por meio de uma interface do Internet Explorer 11. Depois de agosto de 2021, o Internet Explorer 11 não terá suporte para esses produtos do Dynamics 365. |
| **Substituída por outro recurso?**   | Recomendamos que os clientes façam a transição para o Microsoft Edge.|
| **Áreas afetadas do produto**         | Todos os produtos do Dynamics 365 |
| **Opção de implantação**              | Todas|
| **Status**                         | Preterido. Internet Explorer 11 não terá suporte depois de agosto de 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Uso do mecanismo de planejamento mestre do Supply Chain Management integrado para cenários de fabricação

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Para melhorar o desempenho e minimizar o carregamento do banco de dados SQL durante a execução do planejamento mestre, o mecanismo de planejamento mestre interno do Supply Chain Management está sendo substituído pela otimização do planejamento. A otimização do planejamento permite a execução de planejamentos rápidos que podem ser realizados mesmo durante o horário de expediente. Isso permite que os planejadores reajam imediatamente a alterações na demanda ou nos parâmetros de planejamento. |
| **Substituída por outro recurso?**   | Sim, a Otimização de Planejamento substituirá o mecanismo de planejamento mestre do Supply Chain Management interno. |
| **Áreas afetadas do produto**         | Supply Chain Management - Planejamento mestre |
| **Opção de implantação**              | Somente nuvem. A otimização de planejamento não é suportada com implantações locais. |
| **Status**                         | Preterido. A partir de 1 de outubro de 2021, cenários de fabricação não receberão mais suporte com o mecanismo de planejamento mestre interno do Dynamics 365 Supply Chain Management. Para cenários de fabricação, os clientes devem usar a otimização de planejamento para os cálculos de planejamento mestre. Para obter mais informações, consulte [Introdução à documentação da Otimização de Planejamento](https://go.microsoft.com/fwlink/?linkid=2105830). Os clientes com implantações locais do Dynamics 365 Supply Chain Management podem continuar a usar o mecanismo de planejamento mestre de gerenciamento de cadeia de fornecimento para cenários de fabricação depois de outubro de 2021. No entanto, não serão fornecidas mais melhorias de recursos. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Recursos removidos ou substituídos na versão 10.0.11 do Supply Chain Management

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Uso do mecanismo de planejamento mestre do Supply Chain Management integrado para cenários de distribuição

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Para melhorar o desempenho e minimizar o carregamento do banco de dados SQL durante a execução do planejamento mestre, o mecanismo de planejamento mestre interno do Supply Chain Management está sendo substituído pela otimização do planejamento. A otimização do planejamento permite a execução de planejamentos rápidos que podem ser realizados mesmo durante o horário de expediente. Isso permite que os planejadores reajam imediatamente a alterações na demanda ou nos parâmetros de planejamento. |
| **Substituída por outro recurso?**   | Sim, a Otimização de Planejamento substituirá o mecanismo de planejamento mestre do Supply Chain Management interno. |
| **Áreas afetadas do produto**         | Supply Chain Management - Planejamento mestre |
| **Opção de implantação**              | Somente nuvem. A otimização de planejamento não é suportada com implantações locais. |
| **Status**                         | Preterido. Em 1 de abril de 2021, os cenários de distribuição não receberão mais suporte com o mecanismo de planejamento mestre interno do Dynamics 365 Supply Chain Management. Para cenários de distribuição, os clientes devem usar a otimização de planejamento para os cálculos de planejamento mestre. Para obter mais informações, consulte [Introdução à documentação da Otimização de Planejamento](https://go.microsoft.com/fwlink/?linkid=2105830). Os clientes com implantações locais do Dynamics 365 Supply Chain Management podem continuar a usar o mecanismo de planejamento mestre de gerenciamento de cadeia de fornecimento para cenários de distribuição depois de 2021 de abril. No entanto, não serão fornecidas mais melhorias de recursos. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos

Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]