---
title: "Modelagem da organização de lean manufacturing"
description: "O artigo fornece informações sobre os conceitos principais modelagem em uma organização simples."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c8e24234cfa54dcbbf3638c31ced7fb83881bb9f
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="modeling-a-lean-organization"></a>Modelagem da organização de lean manufacturing

[!include [banner](../includes/banner.md)]

O artigo fornece informações sobre os conceitos principais modelagem em uma organização simples. 

Geralmente, um cenário de lean manufacturing normalmente é mais do que apenas uma coleção de regras kanban não relacionadas ou de políticas de fornecimento de material. O fluxo de material e de produtos em células de trabalho e as localizações de um cenário de produção ou fornecimento específico podem ser descritos como uma sequência ou uma rede pequena do processo ou de atividades de transferência. Esta sequência ou rede são conhecidas como um fluxo de produção.

## <a name="production-flows-in-lean-manufacturing"></a>Fluxos de Produção em Lean Manufacturing
Os cenários de produção baseados em ordens de produção, o material é emitido para uma ordem de produção específica. Durante uma sequência de operações, com base em uma lista de materiais (BOM) e nos roteiros, os produtos são criados e finalmente recebidos na localização fornecida. As horas de produtividade das ordens de produção variam em intervalos de minutos a semanas. Todo o custo, material e trabalho relacionados são acumulados na ordem de produção. 

Para reduzir prazos de entrega e o estoque excedente entre os centros de trabalho causados pela produção de lote, o lean manufacturing apresenta o reabastecimento do kanban e supermercados na fabricação e no reabastecimento do depósito. Isso geralmente interrompe a produção de ciclos parcialmente independentes do kanban. O reabastecimento de um kanban para um produto semiacabado não é mais disparado por uma ordem para um produto acabado. 

Para restabelecer um contexto de produção e custo para os vários cenários do kanban propostos no Microsoft Dynamics 365 for Finance and Operations, os fluxos de produção baseados em atividade são apresentados como a base do lean manufacturing. Todas as regras kanban se referem a essa estrutura predefinida. O módulo com base em atividade suporta a configuração de uma variação maior de cenários que as versões anteriores de lean manufacturing para Dynamics AX suportavam. No entanto, este módulo não adiciona a complexidade para trabalhadores de chão de fábrica, como todos os cenários usam a mesma interface do usuário com base na atividade.

## <a name="semi-finished-products-non-bom-levels"></a>Produtos semiacabados (em níveis não BOM)
O Lean Manufacturing para Dynamics AX integra os kanbans para produtos inventariados e semiacabados em uma única estrutura, oferecendo uma experiência de usuário unificada para todos os casos. Devido a essa arquitetura, os níveis adicionais de BOM não precisam ser introduzidos para habilitar os kanbans a serem usados para produtos semiconcluídos. A arquitetura também ajuda a reduzir transações de estoque para um mínimo.

## <a name="products-and-material-in-work-in-progress"></a>Produtos e material no trabalho em andamento
A redução de tamanhos de lote até o estado ideal de um único fluxo em lean manufacturing pode causar um aumento acentuado de transações de estoque se cada processo de separação ou registro do kanban gera transações para os itens consumidos. A arquitetura do fluxo de produção permite a transferência de material para o fluxo de produção com os kanbans de retirada em tamanhos da unidade de manuseio de armazenamento ou de transporte. O valor do material emitido é adicionado à conta de WIP relacionada ao fluxo de produção. Esse comportamento é parecido com o comportamento do material que será emitido em uma ordem de produção. O mesmo princípio pode ser aplicado a produtos e produtos semiacabados. A menos que esses produtos sejam criados, transferidos ou consumidos em um fluxo de produção, as transações de estoque são opcionais. Após os produtos serem lançados no estoque, a conta WIP do fluxo de produção é reduzida através da dedução dos custos padrão relacionados.

## <a name="value-streams-and-value-stream-mapping"></a>Fluxos de valor e mapeamento do fluxo de valor
A arquitetura de Lean Manufacturing do Dynamics AX for inspirada nos cinco princípios de Lean Manufacturing formulados por Womack e Jones: valor do cliente, fluxo de valor, fluxo, recebimento e perfeição. Um método aprovado para implementar soluções de fabricação tendenciosa no mundo de fabricação física é o mapeamento de fluxo de valor. Este método é apresentado por Rother e Shook em sua publicação "Aprender pra ver" no Instituto Lean Manufacturing. 

No Dynamics AX, o fluxo de valor de estado futuro pode ser modelado como uma versão do fluxo de produção. Todos os processos do fluxo de valor são modelados como atividades do processo. Os movimentos ou transferências podem ser modelados como atividades de transferência se o status de transferência precisa ser registrado, ou se é necessária uma integração ao estoque através de envios de separação ou consolidados. 

O próprio fluxo de valor é modelado como uma unidade operacional no Dynamics AX. Consequentemente, o fluxo de valor pode ser usado como uma dimensão financeira.

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a>Custo do lean manufacturing com base no fluxo de produção
A consolidação periódica do custo de um fluxo de produção corrige a conta WIP relacionada e permite a determinação de variações dos produtos fornecidos pelo fluxo de produção.

## <a name="continuous-improvement"></a>Aperfeiçoamento contínuo
Para apoiar o aperfeiçoamento contínuo, os fluxos de produção são implementados em versões com eficiência de tempo. Consequentemente, uma versão do fluxo de produção existente, junto com todas as regras kanban relacionadas, pode ser copiada para uma versão futura do fluxo de produção. Além disso, o fluxo de produção de estado futuro pode ser modelado antes de ser validado e ativado para produção. Para garantir um fluxo de material completo na data de transição e depois, os kanbans existentes de versões do fluxo de produção antigas são automaticamente relacionados à nova versão.

## <a name="simplicity"></a>Simplicidade
Para a implementação de Lean manufacturing para o Dynamics AX, escolhemos uma abordagem de fluxo de produção e atividade que permite modelar cenários de produção simples e complexos em uma única arquitetura escalonável. Uma análise atenta do conceito de atividade revela uma nova simplicidade para aqueles usuários que realmente precisam dela: o chão de fábrica e o pessoal de logística. Ao relatar trabalhos com base em atividades, e não em transações de estoque, uma interface do usuário unificada para todas as variantes de lean manufacturing transfere a complexidade dos negócios da interface do usuário ao qual pertence: o fluxo de produção como a base do lean manufacturing.




