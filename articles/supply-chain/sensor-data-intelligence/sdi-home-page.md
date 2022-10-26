---
title: Página inicial do Sensor Data Intelligence
description: Este artigo oferece uma visão geral do Sensor Data Intelligence. As organizações podem usar esse recurso para impulsionar os processos comerciais no Microsoft Dynamics 365 Supply Chain Management, com base nos sinais da Internet das Coisas (IoT) de máquinas e equipamentos no chão de produção.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: ba030364056db8b0524de22aacbc6528ef77813b
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689848"
---
# <a name="sensor-data-intelligence-home-page"></a>Página inicial do Sensor Data Intelligence

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

O Sensor Data Intelligence para Microsoft Dynamics 365 Supply Chain Management permite que as organizações impulsionam processos comerciais no Supply Chain Management, com base nos sinais da Internet das Coisas (IoT) de máquinas e equipamentos no chão de produção. É uma versão atualizada e renomeada do recurso *Inteligência de IoT* que estava disponível anteriormente para o Supply Chain Management.

O Sensor Data Intelligence permite executar as seguintes tarefas:

- Coletar detalhes de máquinas e equipamentos para atualizar os valores do contador de ativos de manutenção no Supply Chain Management e impulsionar a manutenção preditiva.
- Configure a solução usando um assistente de integração simples em vez de instalar e configurar manualmente os componentes no Microsoft Dynamics Lifecycle Services (LCS).
- Implante componentes em sua própria assinatura, para que você tenha mais flexibilidade para gerenciar componentes do Azure.
- Configure, dimensione e estenda a solução como lógica comercial que é executada nos componentes do Azure. Os componentes agora são gerenciados em sua própria assinatura. Portanto, você pode personalizá-los conforme necessário para satisfazer suas necessidades comerciais específicas.

## <a name="business-scenarios"></a>Cenários de negócios

O Sensor Data Intelligence permite vários tipos de funcionalidade, cada um deles é representado por um *cenário* específico no sistema. Cada cenário fornece um conjunto especializado de opções de configuração no sistema, conforme detalhado na tabela a seguir.

| Cenário | Descrição |
|---|---|
| [Inatividade do ativo](sdi-scenario-asset-downtime.md) | Rastreie precisamente a eficiência dos ativos de máquina usando os dados do sensor para rastrear o tempo de inatividade da máquina. |
| [Manutenção de ativos](sdi-scenario-asset-maintenance.md) | Minimize o custo de manutenção e amplie a vida útil do ativo melhorando os planos de manutenção com base nas leituras de sensor de pontos de controle críticos para ativos de máquina. |
| [Status da máquina](sdi-scenario-equipment-downtime.md) | Garanta a eficiência da operação usando leituras de sensor para notificar os planejadores sobre as paralisações da máquina e fornecer opções para reduzir os possíveis atrasos. |
| [Qualidade do produto](sdi-scenario-product-quality.md) | Garanta a qualidade dos lotes de produtos, comparando as leituras do sensor das propriedades reais de cada lote de produtos, como umidade, temperatura ou métricas de qualidade personalizadas. O sistema notificará os usuários quando ocorrerem desvios. |
| [Atrasos na produção](sdi-scenario-production-delays.md) | Use as leituras do sensor para comparar o tempo de ciclo real com o tempo de ciclo planejado e notifique os supervisores quando a produção não for programada. Os supervisores podem intervir conforme necessário para garantir a eficiência máxima da operação. |

## <a name="architecture"></a>Arquitetura

O diagrama arquitetônico a seguir fornece uma visão geral da solução e dos componentes.

![Diagrama arquitetônico do Sensor Data Intelligence.](media/sdi-architecture.png "Diagrama arquitetônico do Sensor Data Intelligence")
