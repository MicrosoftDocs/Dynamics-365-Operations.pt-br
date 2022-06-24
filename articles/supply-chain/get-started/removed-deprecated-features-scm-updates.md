---
title: Recursos removidos ou preteridos do Dynamics 365 Supply Chain Management
description: Este artigo descreve os recursos que já foram removidos ou foram planejados para remoção no Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 949fa0df58bc3338c8bc84ecbd4f2ad17117dd12
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865256"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Recursos removidos ou preteridos do Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Este artigo será atualizado à medida que os novos recursos removidos ou obsoletos forem documentados para o Dynamics 365 Supply Chain Management.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento.

> [!NOTE]
> Informações detalhadas sobre objetos em aplicativos de Finanças e Operações podem ser encontradas nos [Relatórios de referência técnica](/dynamics/s-e/). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão de aplicativos de Finanças e Operações.


## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10019-release"></a>Recursos removidos ou substituídos na versão 10.0.19 do Supply Chain Management

### <a name="job-card-device"></a>Dispositivo de ficha de trabalho

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo para a reprovação/remoção** | O [dispositivo de ficha de trabalho](../production-control/config-job-card-device.md) está sendo substituído pela nova [interface de execução de piso de produção](../production-control/production-floor-execution-configure.md). |
| **Substituída por outro recurso?**   | Sim, o [dispositivo de ficha de trabalho](../production-control/config-job-card-device.md) será substituído pela nova [interface de execução de piso de produção](../production-control/production-floor-execution-configure.md). |
| **Áreas afetadas do produto** | Supply Chain Management - controle de produção |
| **Opção de implantação** | Nuvem e local |
| **Status** | Preterido. O dispositivo de ficha de trabalho receberá suporte com correções de segurança e bug, mas melhorias de recursos não serão mais fornecidas. Após abril de 2022, o dispositivo de ficha de trabalho não terá mais suporte e os clientes serão solicitados a migrar para a nova interface de execução de piso de produção. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Recursos removidos ou substituídos na versão 10.0.18 do Supply Chain Management

### <a name="dynamics-365-for-finance-and-operations---warehousing-the-warehouse-app"></a>Dynamics 365 for Finance and Operations - Warehousing (o aplicativo de depósito)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Em abril de 2021, o *Dynamics 365 for Finance and Operations - Warehousing* (o aplicativo de depósito) será preterido e só terá suporte até abril de 2022. Ele foi substituído pelo *aplicativo móvel de gerenciamento de depósito*, lançado com a versão 10.0.17 do Supply Chain Management. O novo aplicativo é uma substituição completa, mas usa a mesma estrutura subjacente, o que facilita a migração. Se necessário, os dois aplicativos poderão ser usados lado a lado para ajudar usuários no ajuste gradual à medida que aprendem a usar o novo aplicativo.<br><br>Para obter mais informações sobre o novo aplicativo móvel de gerenciamento de depósito, consulte [Aplicativo móvel de gerenciamento de depósito](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application) e [Instale e conecte o Aplicativo móvel de gerenciamento de depósito](../warehousing/install-configure-warehouse-management-app.md). |
| **Substituída por outro recurso?**   | Sim, substituído pelo novo aplicativo móvel de gerenciamento de depósito. |
| **Áreas afetadas do produto**         | Supply Chain Management - aplicativo de depósito |
| **Opção de implantação**              | Nuvem e local |
| **Status**                         | Preterido. O aplicativo de depósito receberá suporte com correções de segurança e bug, mas melhorias de recursos não serão mais fornecidas. Após abril de 2022, o aplicativo de depósito antigo não terá mais suporte e os clientes serão solicitados a migrar para o novo aplicativo móvel de gerenciamento de depósito. O aplicativo de depósito antigo será removido da Microsoft Store e do Google Play Store.  |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Recursos removidos ou substituídos na versão 10.0.15 do Supply Chain Management

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Suporte do Internet Explorer 11 para Dynamics 365 foi substituído

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A partir de dezembro de 2020, o suporte do Internet Explorer 11 da Microsoft para todos os produtos Dynamics 365 é preterido e Internet Explorer 11 não receberá suporte depois de agosto de 2021.<br><br>Isso afetará os clientes que usam os produtos do Dynamics 365 projetados para serem usados por meio de uma interface do Internet Explorer 11. Depois de agosto de 2021, o Internet Explorer 11 não terá suporte para esses produtos do Dynamics 365. |
| **Substituída por outro recurso?**   | Recomendamos que os clientes façam a transição para o Microsoft Edge.|
| **Áreas afetadas do produto**         | Todos os produtos do Dynamics 365 |
| **Opção de implantação**              | Todas|
| **Status**                         | Preterido. Internet Explorer 11 não terá suporte depois de agosto de 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Uso do mecanismo de planejamento mestre do Supply Chain Management integrado para cenários de fabricação

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Para melhorar o desempenho e minimizar o carregamento do banco de dados SQL durante a execução do planejamento mestre, o mecanismo de planejamento mestre interno do Supply Chain Management está sendo substituído pela otimização do planejamento. A otimização do planejamento permite a execução de planejamentos rápidos que podem ser realizados mesmo durante o horário de expediente. Isso permite que os planejadores reajam imediatamente a alterações na demanda ou nos parâmetros de planejamento. |
| **Substituída por outro recurso?**   | Sim, a Otimização de Planejamento substituirá o mecanismo de planejamento mestre do Supply Chain Management interno. |
| **Áreas afetadas do produto**         | Supply Chain Management - Planejamento mestre |
| **Opção de implantação**              | Somente nuvem. A otimização de planejamento não é suportada com implantações locais. |
| **Status**                         | Preterido. Até 1º de abril de 2022, os cenários de fabricação não serão mais oferecidos para o mecanismo de planejamento mestre interno do Supply Chain Management. A partir dessa data, a Microsoft interromperá todo o desenvolvimento ativo em cenários de fabricação para o mecanismo de planejamento interno, não lançará novos recursos e só lançará as correções críticas de erros. Após essa data, todas as empresas que necessitam de suporte para cenários de fabricação devem usar a otimização de planejamento para seus cálculos de planejamento mestre. Espera-se que a otimização do planejamento dê suporte total aos cenários de fabricação até outubro de 2022. Para obter mais informações, consulte a [documentação da Otimização de Planejamento](../master-planning/planning-optimization/planning-optimization-overview.md).<br><br>As empresas com implantações locais do Supply Chain Management podem continuar a usar o mecanismo de planejamento mestre interno para cenários de fabricação depois de abril de 2022. No entanto, não serão fornecidas mais melhorias de recursos. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Recursos removidos ou substituídos na versão 10.0.11 do Supply Chain Management

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Uso do mecanismo de planejamento mestre do Supply Chain Management integrado para cenários de distribuição

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Para melhorar o desempenho e minimizar o carregamento do banco de dados SQL durante a execução do planejamento mestre, o mecanismo de planejamento mestre interno do Supply Chain Management está sendo substituído pela otimização do planejamento. A otimização do planejamento permite a execução de planejamentos rápidos que podem ser realizados mesmo durante o horário de expediente. Isso permite que os planejadores reajam imediatamente a alterações na demanda ou nos parâmetros de planejamento. |
| **Substituída por outro recurso?**   | Sim, a Otimização de Planejamento substituirá o mecanismo de planejamento mestre do Supply Chain Management interno. |
| **Áreas afetadas do produto**         | Supply Chain Management - Planejamento mestre |
| **Opção de implantação**              | Somente nuvem. A otimização de planejamento não é suportada com implantações locais. |
| **Status**                         | Preterido. Em 1 de abril de 2021, os cenários de distribuição não receberão mais suporte com o mecanismo de planejamento mestre interno do Dynamics 365 Supply Chain Management. Para cenários de distribuição, os clientes devem usar a otimização de planejamento para os cálculos de planejamento mestre. Para obter mais informações, consulte [Introdução à documentação da Otimização de Planejamento](../master-planning/planning-optimization/planning-optimization-overview.md). Os clientes com implantações locais do Dynamics 365 Supply Chain Management podem continuar a usar o mecanismo de planejamento mestre de gerenciamento de cadeia de fornecimento para cenários de distribuição depois de 2021 de abril. No entanto, não serão fornecidas mais melhorias de recursos. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos

Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
