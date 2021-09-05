---
title: Diferenças entre planejamento mestre interno e Otimização de Planejamento
description: Este tópico lista recursos para os quais a Otimização de Planejamento ainda não dá suporte e que não estão listados na página de análise de ajuste da Otimização de Planejamento.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a102f1d77362f650c060ce5d0aee5b62d2102532
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344945"
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
| Sequências numéricas para ordens planejadas | Não há suporte para sequências numéricas para ordens planejadas. Os números de ordens planejadas são gerados no lado do serviço. |
| Planejar cópia, excluir plano e limpeza da versão do plano | <p>Os itens a seguir estão desabilitados em **Planejamento mestre: \> Planejamento mestre: \> Manter planos** no painel de navegação:</p><ul><li>Planejar cópia</li><li>Excluir plano</li><li>Planejar limpeza da versão</li></ul> |
| Ordens de Devolução | As ordens de devolução não são consideradas. |
| Recursos relacionados ao agendamento | Para obter detalhes, consulte [Agendamento com capacidade infinita](infinite-capacity-planning.md#limitations). |
| Calendários de transporte | O valor na coluna **Calendário de transporte** na página **Modos de entrega** é ignorado. |

## <a name="additional-resources"></a>Recursos adicionais

- [Análise de ajuste da Otimização do Planejamento](planning-optimization-fit-analysis.md)
- [Parâmetros não usados pela Otimização de Planejamento](not-used-parameters.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
