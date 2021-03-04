---
title: Visão geral da Otimização de Planejamento
description: Este tópico mostra uma visão geral da Otimização de Planejamento
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 110045d4c7e4f32c29b73096dd4df3a09b5434ac
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421964"
---
# <a name="planning-optimization-overview"></a>Visão geral da Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

O Suplemento Otimização de Planejamento para o Microsoft Dynamics 365 Supply Chain Management permite que o cálculo de planejamento mestre ocorra fora do Dynamics 365 Supply Chain Management e do banco de dados SQL relacionado. Os benefícios associados à funcionalidade Otimização de Planejamento incluem o desempenho aprimorado e o impacto mínimo no banco de dados SQL durante as execuções do planejamento mestre. As execuções de planejamento rápido podem ser feitas mesmo durante o horário de expediente, para que os planejadores possam reagir imediatamente à demanda ou às alterações de parâmetro.

Para usar a Otimização de Planejamento, você deverá instalar o Suplemento Otimização de Planejamento do seu projeto no Microsoft Dynamics Lifecycle Services (LCS) e ativar a funcionalidade Otimização de Planejamento no Supply Chain Management. Para obter mais informações, consulte [Introdução à Otimização de Planejamento](get-started.md).

A ilustração a seguir mostra a vantagem da execução da Otimização de Planejamento no horário de expediente.

![Vantagem de executar a Otimização de planejamento durante o horário de expediente](media/PlanningOptimization1.png)

## <a name="improved-performance"></a>Desempenho aprimorado

A Otimização de Planejamento pode ser usada em cenários que envolvam planos mestres de execução longa. Ela foi especificamente projetada para cálculos muito rápidos envolvendo volumes de dados muito grandes. Como foi criada como um serviço multilocatário hiperescalável, várias instâncias podem trabalhar juntas simultaneamente para calcular o plano. Além disso, o serviço de planejamento remove a carga do planejamento mestre do sistema e trabalha com um fluxo de dados que minimiza a carga do servidor.

A Otimização de Planejamento pode ajudá-lo a atingir as seguintes metas:

- Aumentar o desempenho do planejamento com um runtime mais curto.
- Reduzir o impacto em outros processos durante a execução do planejamento mestre.
- Fazer execuções mais frequentes de planejamento. (Você não está limitado às execuções diárias).
- Ficar confiante de que o crescimento futuro dos negócios não sobrecarregará o sistema de planejamento.

## <a name="architecture-and-data-flow"></a>Arquitetura e fluxo de dados

Quando o Suplemento de Otimização de Planejamento for instalado do LCS, uma conexão segura para o serviço Otimização de Planejamento será estabelecida. O serviço está localizado no mesmo país ou região do data center da instância do Supply Chain Management relacionado. Após a configuração da Otimização de Planejamento, quando o planejamento mestre é executado, os dados mestre e os dados transacionais são enviados do Supply Chain Management para o serviço Otimização de Planejamento.

Se o Suplemento Otimização de Planejamento for desinstalado, todos os dados relacionados no serviço Otimização de Planejamento serão removidos.

### <a name="high-level-data-flow-for-regeneration-runs"></a>Fluxo de dados de alto nível para execuções de regeneração

1. O cliente do Supply Chain Management envia um sinal para solicitar uma execução de planejamento desde a Otimização de Planejamento.
2. A Otimização de Planejamento solicita os dados necessários por meio do conector integrado.
3. O banco de dados SQL envia as informações solicitadas sobre a configuração, os dados mestre e os dados transacionais para a Otimização de Planejamento por meio do conector. O conector converte as informações entre o Supply Chain Management e o serviço Otimização de Planejamento.
4. O serviço Otimização de Planejamento contém os dados relacionados ao planejamento em memória e faz os cálculos necessários.
5. O resultado do planejamento é enviado para o banco de dados do Supply Chain Management por meio do conector. Os resultados incluem informações como as ordens planejadas e as informações de vinculação. A Otimização de Planejamento envia um sinal para o Supply Chain Management para indicar que o planejamento foi concluído. Ele também envia as mensagens e avisos relevantes.

A ilustração a seguir mostra o fluxo de dados.

![Fluxo de dados para execuções de regeneração](media/PlanningOptimization2.png)

## <a name="related-resources"></a>Recursos relacionados

[Introdução à Otimização de Planejamento](get-started.md)

[Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)

[Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)

[Aplicar filtros a um plano](plan-filters.md)

[Cancelar um trabalho de planejamento](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]