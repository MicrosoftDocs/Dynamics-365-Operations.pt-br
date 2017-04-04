---
title: Planos mestres
description: "Use vários planos mestres suportar trabalhando as operações diárias da empresa, simular diferentes estratégias de planejamento que você deseja monitorar, implementação e uma diretiva da empresa, como uma diretiva sobre o desempenho ou a satisfação de cliente interno."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7911
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 29bb560c11e63938bea73ed8471c27563b546f8f
ms.lasthandoff: 03/31/2017


---

# <a name="master-plans"></a>Planos mestres

Use vários planos mestres suportar trabalhando as operações diárias da empresa, simular diferentes estratégias de planejamento que você deseja monitorar, implementação e uma diretiva da empresa, como uma diretiva sobre o desempenho ou a satisfação de cliente interno. 

Você pode configurar planos mestres na página **Planos mestres**.

Há dois tipos de planos:
-   **Plano estático** - o cálculo do planejamento mestre usa os dados atuais para gerar um plano de requisições líquidas. Esse plano permanece inalterado até a próxima vez que você executar o planejamento mestre. É um plano de operações que várias pessoas da empresa, como um comprador ou planejador de produção, podem usar como base de suas decisões e para a realização de tarefas e atividades diárias.
-   **Plano dinâmico** - este plano é iniciado com o mesmo plano de requisições líquidas gerado pelo planejamento mestre. Contudo, é possível atualizar o plano dinâmico a cada vez que os dados mestres são alterados. Isso pode ocorrer na criação de uma nova ordem de venda, por exemplo. Isso permite que você monitore a rede de ordens em alteração e a disponibilidade do item sem atrapalhar o plano estático que outros usam para seus processos de trabalho.

Uma empresa pode optar por trabalhar apenas com um plano dinâmico ou usar tanto planos estáticos quanto dinâmicos. Além disso, é possível configurar qualquer plano mestre para refletir uma determinada estratégia ou abordar um problema. Os exemplos são os seguintes:
-   Configurar níveis de estoque maiores de modo a evitar o esgotamento do estoque.
-   Configurar margens de segurança maiores para proteção contra fornecedores não confiáveis.

Também é possível configurar o início do plano dinâmico para ser atualizado com o novo plano de requisições, cada vez que você executar o planejamento mestre. Você pode especificar essas configurações na página **Parâmetros de planejamento mestre**.



<a name="see-also"></a>Consulte também
--------

[Configurações de cobertura](coverage-settings.md)

[Separando o planejamento tático e operativo para o planejamento mestre (http://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)]

[Planejamento mestre: Use uma static e um plano mestre dinâmico ou use um plano?] (https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)


