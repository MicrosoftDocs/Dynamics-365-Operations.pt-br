---
title: Visão geral de planos mestres
description: Use diversos planos mestre para oferecer suporte a operações de produção diárias da empresa, simular diferentes estratégias de planejamento que deseja monitorar e implementar uma política corporativa, por exemplo, com relação ao desempenho interno ou à satisfação do cliente.
author: roxanadiaconu
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "7911"
- intro-internal
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 022b5dcab8ef431edbed308660f92b841eb972cdb7a53095f057e6718880ceed
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759542"
---
# <a name="master-plans-overview"></a>Visão geral de planos mestres

[!include [banner](../includes/banner.md)]

Use diversos planos mestre para oferecer suporte a operações de produção diárias da empresa, simular diferentes estratégias de planejamento que deseja monitorar e implementar uma política corporativa, por exemplo, com relação ao desempenho interno ou à satisfação do cliente. 

Você pode configurar planos mestres na página **Planos mestres**.

Há dois tipos de planos:
-   **Plano estático** - o cálculo do planejamento mestre usa os dados atuais para gerar um plano de requisições líquidas. Esse plano permanecerá inalterado até a próxima vez que você executar o planejamento mestre ou alterar manualmente o plano. É um plano de operações que várias pessoas da empresa, como um comprador ou planejador de produção, podem usar como base de suas decisões e para a realização de atividades diárias.
-   **Plano dinâmico** - este plano é iniciado com o mesmo plano de requisições líquidas gerado pelo planejamento mestre. Contudo, é possível atualizar o plano dinâmico a cada vez que os dados mestres são alterados. Isso pode ocorrer na criação de uma nova ordem de venda, por exemplo. Isso permite que você monitore a rede de ordens em alteração e a disponibilidade do item sem atrapalhar o plano estático que outros usam para seus processos de trabalho.

Uma empresa pode optar por trabalhar apenas com um plano dinâmico ou usar tanto planos estáticos quanto dinâmicos. Além disso, é possível configurar qualquer plano mestre para refletir uma determinada estratégia ou abordar um problema. Os exemplos são os seguintes:
-   Configurar níveis de estoque maiores de modo a evitar o esgotamento do estoque.
-   Configurar margens de segurança maiores para proteção contra fornecedores não confiáveis.

Também é possível configurar o início do plano dinâmico para ser atualizado com o novo plano de requisições, cada vez que você executar o planejamento mestre. Você pode especificar essas configurações na página **Parâmetros de planejamento mestre**.



## <a name="additional-resources"></a>Recursos adicionais

[Configurações de cobertura](coverage-settings.md)

[Separando planejamento tático e operador para agendamento mestre](https://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)

[Planejamento mestre: Usar um Plano Mestre estático e dinâmico ou usar um plano?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]