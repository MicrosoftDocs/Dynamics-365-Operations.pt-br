---
title: Diferenças entre planejamento mestre interno e Otimização de Planejamento
description: Este tópico lista recursos para os quais a Otimização de Planejamento ainda não dá suporte e que não estão listados na página de análise de ajuste da Otimização de Planejamento.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c73587015d6714c409819ab19ad68685aaa71cf7
ms.sourcegitcommit: 70289a33b0a6ff3f9418d91a928db452cfd815bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2022
ms.locfileid: "8618250"
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
| Código de cobertura mín./máx. sem valores| Com o mecanismo de planejamento incorporado, ao usar um código de cobertura mín./máx. onde nenhum valor mínimo ou máximo é definido, o mecanismo de planejamento trata o código de cobertura como um requisito e cria uma ordem para cada requisito. Com a otimização de planejamento, o sistema criará uma ordem por dia para cobrir o valor total desse dia.  |
| Requisitos líquidos e ordens planejadas criadas manualmente | Com o mecanismo de planejamento incorporado, as ordens de fornecimento criadas manualmente para um item aparecem automaticamente entre os requisitos líquidos para aquele item. Por exemplo, ao criar uma ordem de compra a partir de uma ordem de venda, a ordem de compra aparece na página **Requisitos líquidos** sem exigir ações anteriores. Isso ocorre porque o mecanismo de planejamento integrado registra as transações de estoque na tabela do `inventLogTTS` e mostra as alterações na página **Requisitos líquidos** para planos dinâmicos. No entanto, com a Otimização de Planejamento, as ordens criadas manualmente não aparecerão entre os requisitos líquidos de um item até que a Otimização de Planejamento seja executada (usando um plano que inclui o item) ou até você selecionar **Atualizar \> Planejamento mestre** no Painel de Ações na página **Requisitos líquidos**, que executará o planejamento mestre para o item. Para obter mais informações sobre como trabalhar com a página **Requisitos líquidos**, consulte [Requisitos líquidos e informações de vinculação com a Otimização de Planejamento](net-requirements.md). |

## <a name="additional-resources"></a>Recursos adicionais

- [Análise de ajuste da Otimização do Planejamento](planning-optimization-fit-analysis.md)
- [Parâmetros não usados pela Otimização de Planejamento](not-used-parameters.md)
- [Parâmetros de data e hora usados pela Otimização de Planejamento](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
