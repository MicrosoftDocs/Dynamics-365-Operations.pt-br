---
title: Diferenças entre planejamento mestre interno e Otimização de Planejamento
description: Este tópico lista recursos para os quais a Otimização de Planejamento ainda não dá suporte e que não estão listados na página de análise de ajuste da Otimização de Planejamento.
author: ChristianRytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: e271ddd3331d7b5de78f00a02b60a0479879c172
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2021
ms.locfileid: "7699996"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>Diferenças entre planejamento mestre interno e Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Os resultados da Otimização de Planejamento podem ser diferentes dos resultados do mecanismo de planejamento mestre integrado. As diferenças podem ser causadas por recursos pendentes. Este tópico lista recursos para os quais a Otimização do Planejamento ainda não dá suporte e que não estão listados na página **[Análise de ajuste da Otimização do Planejamento](planning-optimization-fit-analysis.md)**].

| Recurso | Comportamento atual na Otimização de Planejamento |
|---|---|
| Produtos de peso variável | Os produtos de peso variável são considerados produtos usuais.|
| Dimensões extensíveis | Dimensões extensíveis estão vazias em ordens planejadas, mesmo quando a caixa de seleção **Plano de cobertura por dimensão** é marcada na página **Grupos de dimensão de armazenamento** ou **Grupos de dimensão de rastreamento**. |
| Execuções de produção filtradas | Para obter detalhes, consulte [Planejamento de produção — filtros](production-planning.md#filters). |
| Planejamento de previsão | O planejamento de previsão não tem suporte. Recomendamos que você use o planejamento mestre em que um modelo de previsão é atribuído ao plano mestre. |
| Sequências numéricas para ordens planejadas | Não há suporte para sequências numéricas para ordens planejadas. Os números de ordens planejadas são gerados no lado do serviço. O número da ordem planejada normalmente é mostrado com 10 dígitos, mas a sequência é criada de fato em 20 caracteres, com 10 dígitos alocados para a contagem de execuções de planejamento e os outros 10 dígitos para a contagem de ordens planejadas. |
| Planejar cópia, excluir plano e limpeza da versão do plano | <p>Os itens a seguir estão desabilitados em **Planejamento mestre: \> Planejamento mestre: \> Manter planos** no painel de navegação:</p><ul><li>Planejar cópia</li><li>Excluir plano</li><li>Planejar limpeza da versão</li></ul> |
| Ordens de Devolução | As ordens de devolução não são consideradas. |
| Recursos relacionados ao agendamento | Para obter detalhes, consulte [Agendamento com capacidade infinita](infinite-capacity-planning.md#limitations). |
| Atendimento de estoque de segurança | A otimização de planejamento sempre usa a opção *Data atual + tempo de aquisição* para o campo **Mínimo de preenchimento** na página **Cobertura de item**. Isso ajuda a evitar ordens planejadas não desejadas e outros problemas porque, se o tempo de aquisição não for incluído no estoque de segurança, as ordens planejadas criadas para o estoque baixo sempre estarão atrasadas por conta do prazo de entrega. |
| Vinculação e requisitos líquidos de estoque de segurança | O tipo de requisito *Estoque de segurança* não está incluído e não é exibido na página **Requisitos líquidos**. O estoque de segurança não representa a demanda e não tem uma data de requisito associada. Em vez disso, ele define uma restrição sobre a quantidade de estoque que deve estar sempre presente. No entanto, o valor do campo **Mínimo** ainda é considerado ao calcular ordens planejadas durante o planejamento mestre. Sugerimos que você inspecione a coluna **Quantidade acumulada** na página **Requisitos líquidos** para ver que esse valor foi considerado. |
| Calendários de transporte | O valor na coluna **Calendário de transporte** na página **Modos de entrega** é ignorado. |

## <a name="additional-resources"></a>Recursos adicionais

- [Análise de ajuste da Otimização do Planejamento](planning-optimization-fit-analysis.md)
- [Parâmetros não usados pela Otimização de Planejamento](not-used-parameters.md)
- [Parâmetros de data e hora usados pela Otimização de Planejamento](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
