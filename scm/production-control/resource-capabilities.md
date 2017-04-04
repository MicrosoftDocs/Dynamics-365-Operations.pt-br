---
title: Capacidades do recurso
description: "Este artigo fornece informações sobre os recursos de recurso. Um recurso é a capacidade de um recurso de operações de executar uma atividade específica. O artigo explica como os recursos e os conceitos relacionados, como o nível de proficiência e a prioridade, são usados para selecionar recursos apropriados para uma atividade."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WrkCtrCapability, WrkCtrTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29961
ms.assetid: 30e38233-2a64-4070-911f-8ffd78dd8281
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4463ca8e11115eb83323716faa4ed6b38937a3e4
ms.lasthandoff: 03/31/2017


---

# <a name="resource-capabilities"></a>Capacidades do recurso

Este artigo fornece informações sobre os recursos de recurso. Um recurso é a capacidade de um recurso de operações de executar uma atividade específica. O artigo explica como os recursos e os conceitos relacionados, como o nível de proficiência e a prioridade, são usados para selecionar recursos apropriados para uma atividade.

Um recurso é a capacidade de um recurso de operações de executar uma atividade específica. Um recurso de operações pode ter mais de uma capacidade atribuída a ele, e uma capacidade pode ser atribuída a mais de um recurso. Você pode atribuir capacidades temporárias a recursos, definindo uma data de início e uma data de vencimento na atribuição de capacidade. Quando a capacidade para um recurso expira, o recurso não pode ser agendado para um projeto ou uma produção que exija esse recurso. Uma capacidade vencida pode ser renovada. Você pode excluir capacidades, desde que elas não estejam em uma relação de roteiro ou em parte de um roteiro de produção de uma ordem de produção ativa. Em geral, tome cuidado ao excluir capacidades. Ajuste a data de vencimento dos recursos que têm a capacidade. As capacidades podem ser atribuídas a todos os tipos de recursos: ferramenta, fornecedor, computador, local, instalação ou RH.

## <a name="level"></a>Nível
Muitos recursos costumam ter a mesma capacidade funcional, mas em diferentes níveis de proficiência (por exemplo, força, velocidade de processamento ou precisão). Portanto, quando você atribui uma capacidade a um recurso, pode especificar um valor de **Nível**. O nível é um valor numérico simples. Se você especificar que uma capacidade é uma requisição de recurso para um roteiro de produção, também poderá especificar um valor **Nível mínimo necessário** para esse recurso. O mecanismo de agendamento seleciona apenas os recursos com a capacidade necessária em um nível que equivale ou excede o nível mínimo especificado na requisição de recurso.

## <a name="priority"></a>Prioridade
Os recursos de operações com as mesmas capacidades podem receber uma prioridade. Depois, se vários recursos com os recursos que satisfazem os requisitos do plano a nível necessário, e tem capacidade livre, o mecanismo de planejamento pode selecionar entre esses recursos. ** Prioridade ** se está selecionado ** seleção principal de recurso ** o campo ** parâmetros de planejamento ** na página, o recurso que tem mais prioridade (menor valor numérico ** prioridade **) no campo é marcado primeiro durante o planejamento.

## <a name="resource-requirements"></a>Requisitos de recursos
Ao definir requisitos de recursos para um roteiro de produção, você pode especificar uma ou mais capacidades como requisitos. Durante o agendamento da produção, as capacidades definidas nos requisitos de recursos na operação de roteiro são combinadas com as capacidades definidas para os recursos. Os recursos com capacidades que atendem aos requisitos são selecionados. Se vários recursos têm a mesma capacidade funcional, mas proficiências diferentes (como força, velocidade de processamento ou precisão), você pode definir várias capacidades ou usar o nível de capacidade para qualificar a capacidade do recurso. Veja a seguir um exemplo:

-   Em um roteiro, o tempo de processamento de perfuração é definido como 10 unidades por hora, mas o requisito em si é definido como Perfuração.
-   Você tem duas máquinas furadeiras, M1 e M2.
-   A capacidade de perfuração é atribuída aos dois recursos, a máquina M1 e a máquina M2.
-   A máquina M1 pode perfurar duas unidades por hora, e a máquina M2 pode perfurar 11 unidades por hora.

Neste exemplo, a duas máquinas podem ser selecionadas pelo mecanismo de agendamento, pois ambas atendem ao requisito de capacidade básica (Perfuração). No entanto, a máquina M1 pode furar somente duas unidades por hora. Como a taxa é muito menor que as 10 unidades por hora especificadas no roteiro, a máquina M1 causará problemas de produção se for selecionada. Há duas maneiras de resolver esse problema e garantir que a máquina M2 seja selecionada:

-   Criar duas capacidades separadas: perfuração de baixa velocidade e perfuração de alta velocidade. Definir a perfuração de baixa velocidade como a perfuração com um tempo de processamento de 1 a 9 unidades por hora. Definir a perfuração de alta velocidade como a perfuração com um tempo de processamento de 10 a 19 unidades por hora. Atribuir ao computador M1 no recurso de baixa velocidade de perfuração, e atribua ao computador do recurso M2 de alta velocidade de perfuração. Finalmente, altere o requisito do recurso de recursos no roteiro da perfuração alta velocidade. O mecanismo de agendamento selecionará o computador correto (M2).
-   Use o nível de capacidade para qualificar a capacidade de perfuração que é atribuída às máquinas de perfuração. Especifica o computador tiver M1 o recurso de perfuração do nível 2.0, e se o computador tiver M2 do recurso de perfuração a nível de 11.0. Depois especifique que 10.0 é o nível mínimo necessário para a requisição do recurso de perfuração no roteiro. O mecanismo de agendamento determinará que apenas a máquina M2 atenda aos requisitos de recursos.

## <a name="competencies-for-human-resources"></a>Competências de recursos humanos
Quando você tem os recursos operacionais do tipo **Recursos humanos** que estão vinculados a trabalhadores de RH, também pode aproveitar as competências de trabalhadores quando define os requisitos de recursos para um roteiro de produção. Ou seja, você também pode especificar requisitos para habilidades, cursos, certificados ou títulos específicos. O mecanismo de agendamento pode selecionar os recursos que estão vinculados a trabalhadores. A seleção se baseará nas competências desses trabalhadores. As competências são configuradas em Recursos humanos, e não na página **Capacidades do recurso**. Quando você define habilidades, cursos, certificados, como títulos ou requisitos de recursos, você deve usar a funcionalidade recursos humanos e para vincular cada recurso de ** recursos humanos ** digite a um trabalhador correspondente. Se não estiver usando a funcionalidade recursos humanos, você pode definir os recursos ** recursos de recurso ** pagina que se assemelham duplicados ou se as competências de recursos humanos. No entanto, a página **Capacidades do recurso** não contém a funcionalidade necessária para manter habilidades, cursos, certificações ou títulos.


