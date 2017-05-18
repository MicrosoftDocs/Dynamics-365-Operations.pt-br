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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: c37e536e2070c21bfb19bb4281f3892ec55777ea
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="resource-capabilities"></a>Capacidades do recurso

[!include[banner](../includes/banner.md)]


Este artigo fornece informações sobre os recursos de recurso. Um recurso é a capacidade de um recurso de operações de executar uma atividade específica. O artigo explica como os recursos e os conceitos relacionados, como o nível de proficiência e a prioridade, são usados para selecionar recursos apropriados para uma atividade.

Um recurso é a capacidade de um recurso de operações de executar uma atividade específica. Um recurso de operações pode ter mais de uma capacidade atribuída a ele, e uma capacidade pode ser atribuída a mais de um recurso. Você pode atribuir capacidades temporárias a recursos, definindo uma data de início e uma data de vencimento na atribuição de capacidade. Quando a capacidade para um recurso expira, o recurso não pode ser agendado para um projeto ou uma produção que exija esse recurso. Uma capacidade vencida pode ser renovada. Você pode excluir capacidades, desde que elas não estejam em uma relação de roteiro ou em parte de um roteiro de produção de uma ordem de produção ativa. Em geral, tome cuidado ao excluir capacidades. Ajuste a data de vencimento dos recursos que têm a capacidade. As capacidades podem ser atribuídas a todos os tipos de recursos: ferramenta, fornecedor, computador, local, instalação ou RH.

## <a name="level"></a>Nível
Muitos recursos costumam ter a mesma capacidade funcional, mas em diferentes níveis de proficiência (por exemplo, força, velocidade de processamento ou precisão). Portanto, quando você atribui uma capacidade a um recurso, pode especificar um valor de **Nível**. O nível é um valor numérico simples. Se você especificar que uma capacidade é uma requisição de recurso para um roteiro de produção, também poderá especificar um valor **Nível mínimo necessário** para esse recurso. O mecanismo de agendamento seleciona apenas os recursos com a capacidade necessária em um nível que equivale ou excede o nível mínimo especificado na requisição de recurso.

## <a name="priority"></a>Prioridade
Os recursos de operações com as mesmas capacidades podem receber uma prioridade. Em seguida, se vários recursos tiverem capacidades que satisfaçam os requisitos de agendamento no nível exigido e tenham capacidade livre, o mecanismo de agendamento pode selecionar entre esses recursos. Se **Prioridade** estiver selecionado no campo **Seleção de recurso primário** na página **Parâmetros de planejamento**, o recurso que tiver mais prioridade (o valor numérico mais baixo no campo **Prioridade**) é selecionado primeiro durante o planejamento.

## <a name="resource-requirements"></a>Requisitos de recursos
Ao definir requisitos de recursos para um roteiro de produção, você pode especificar uma ou mais capacidades como requisitos. Durante o agendamento da produção, as capacidades definidas nos requisitos de recursos na operação de roteiro são combinadas com as capacidades definidas para os recursos. Os recursos com capacidades que atendem aos requisitos são selecionados. Se vários recursos têm a mesma capacidade funcional, mas proficiências diferentes (como força, velocidade de processamento ou precisão), você pode definir várias capacidades ou usar o nível de capacidade para qualificar a capacidade do recurso. Veja a seguir um exemplo:

-   Em um roteiro, o tempo de processamento de perfuração é definido como 10 unidades por hora, mas o requisito em si é definido como Perfuração.
-   Você tem duas máquinas furadeiras, M1 e M2.
-   A capacidade de perfuração é atribuída aos dois recursos, a máquina M1 e a máquina M2.
-   A máquina M1 pode perfurar duas unidades por hora, e a máquina M2 pode perfurar 11 unidades por hora.

Neste exemplo, a duas máquinas podem ser selecionadas pelo mecanismo de agendamento, pois ambas atendem ao requisito de capacidade básica (Perfuração). No entanto, a máquina M1 pode furar somente duas unidades por hora. Como a taxa é muito menor que as 10 unidades por hora especificadas no roteiro, a máquina M1 causará problemas de produção se for selecionada. Há duas maneiras de resolver esse problema e garantir que a máquina M2 seja selecionada:

-   Criar duas capacidades separadas: perfuração de baixa velocidade e perfuração de alta velocidade. Definir a perfuração de baixa velocidade como a perfuração com um tempo de processamento de 1 a 9 unidades por hora. Definir a perfuração de alta velocidade como a perfuração com um tempo de processamento de 10 a 19 unidades por hora. Em seguida, atribua à máquina M1 a capacidade de perfuração de baixa velocidade e atribua à máquina M2 a capacidade de perfuração de alta velocidade. Finalmente, altere o requisito de capacidade de recursos na rota para Perfuração de alta velocidade. O mecanismo de agendamento selecionará o computador correto (M2).
-   Use o nível de capacidade para qualificar a capacidade de perfuração que é atribuída às máquinas de perfuração. Especifique que a máquina M1 tem a capacidade de perfuração em um nível de 2.0 e que a máquina M2 tem a capacidade de perfuração em um nível de 11.0. Em seguida, especifique que 10.0 é o nível mínimo exigido para o requisito de capacidade de perfuração na rota. O mecanismo de agendamento determinará que apenas a máquina M2 atenda aos requisitos de recursos.

## <a name="competencies-for-human-resources"></a>Competências de recursos humanos
Quando você tem os recursos operacionais do tipo **Recursos humanos** que estão vinculados a trabalhadores de RH, também pode aproveitar as competências de trabalhadores quando define os requisitos de recursos para um roteiro de produção. Ou seja, você também pode especificar requisitos para habilidades, cursos, certificados ou títulos específicos. O mecanismo de agendamento pode selecionar os recursos que estão vinculados a trabalhadores. A seleção se baseará nas competências desses trabalhadores. As competências são configuradas em Recursos humanos, e não na página **Capacidades do recurso**. Quando você define habilidades, cursos, certificados ou títulos como requisitos de recurso, deve usar a funcionalidade Recursos humanos e vincular cada recurso do tipo **Recursos humanos** a um trabalhador correspondente. Se não estiver usando a funcionalidade Recursos humanos, você poderá definir capacidades na página **Capacidades do recurso** que lembrem ou dupliquem as competências de Recursos humanos. No entanto, a página **Capacidades do recurso** não contém a funcionalidade necessária para manter habilidades, cursos, certificações ou títulos.




