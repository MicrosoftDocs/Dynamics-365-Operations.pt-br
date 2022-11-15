---
title: Diferenças entre Otimização de Planejamento e mecanismo de planejamento mestre preterido
description: Este artigo lista recursos para os quais a Otimização de Planejamento ainda não dá suporte e que não estão listados na página de análise de ajuste da Otimização de Planejamento.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6e1671a508b85a94ac9687af15e898d885ea94c1
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745352"
---
# <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>Diferenças entre Otimização de Planejamento e mecanismo de planejamento mestre preterido

[!include [banner](../../includes/banner.md)]

Os resultados da Otimização de Planejamento podem ser diferentes dos resultados do mecanismo de planejamento mestre preterido. As diferenças podem ser causadas por recursos pendentes. Este artigo lista recursos para os quais a Otimização do Planejamento ainda não dá suporte e que não estão listados na página **[Análise de ajuste da Otimização do Planejamento](planning-optimization-fit-analysis.md)**].

| Recurso | Comportamento atual na Otimização de Planejamento |
|---|---|
| Produtos de peso variável | Os produtos de peso variável são considerados produtos usuais.|
| Dimensões extensíveis | Não há suporte a dimensões extensíveis pela Otimização de Planejamento. Ao usar a Otimização de Planejamento, as dimensões extensíveis estarão vazias nas ordens planejadas, mesmo quando a caixa de seleção **Plano de cobertura por dimensão** estiver marcada na página **Grupos de dimensão de armazenamento** ou **Grupos de dimensão de rastreamento**. |
| Execuções de produção filtradas | Para obter detalhes, consulte [Planejamento de produção — filtros](production-planning.md#filters). |
| Planejamento de previsão | O planejamento de previsão não tem suporte. Recomendamos que você use o planejamento mestre em que um modelo de previsão é atribuído ao plano mestre. |
| Sequências numéricas para ordens planejadas | Não há suporte para sequências numéricas para ordens planejadas. Os números de ordens planejadas são gerados no lado do serviço. O número da ordem planejada normalmente é mostrado com 10 dígitos, mas a sequência é criada de fato em 20 caracteres, com 10 dígitos alocados para a contagem de execuções de planejamento e os outros 10 dígitos para a contagem de ordens planejadas. |
| Planejar cópia, excluir plano e limpeza da versão do plano | <p>Os itens a seguir estão desabilitados em **Planejamento mestre: \> Planejamento mestre: \> Manter planos** no painel de navegação:</p><ul><li>Planejar cópia</li><li>Excluir plano</li><li>Planejar limpeza da versão</li></ul> |
| Ordens de Devolução | As ordens de devolução não são consideradas. |
| Recursos relacionados ao agendamento | Para obter detalhes, consulte [Agendamento com capacidade infinita](infinite-capacity-planning.md#limitations). |
| Atendimento de estoque de segurança | A otimização de planejamento sempre usa a opção *Data atual + tempo de aquisição* para o campo **Mínimo de preenchimento** na página **Cobertura de item**. Isso ajuda a evitar ordens planejadas não desejadas e outros problemas porque, se o tempo de aquisição não for incluído no estoque de segurança, as ordens planejadas criadas para o estoque baixo sempre estarão atrasadas por conta do prazo de entrega. |
| Vinculação e requisitos líquidos de estoque de segurança | O tipo de requisito *Estoque de segurança* não está incluído e não é exibido na página **Requisitos líquidos**. O estoque de segurança não representa a demanda e não tem uma data de requisito associada. Em vez disso, ele define uma restrição sobre a quantidade de estoque que deve estar sempre presente. No entanto, o valor do campo **Mínimo** ainda é considerado ao calcular ordens planejadas durante o planejamento mestre. Sugerimos que você inspecione a coluna **Quantidade acumulada** na página **Requisitos líquidos** para ver que esse valor foi considerado. Como a vinculação é diferente, ações diferentes podem ser sugeridas. |
| Calendários de transporte | O valor na coluna **Calendário de transporte** na página **Modos de entrega** é ignorado. |
| Código de cobertura mín./máx. sem valores| Com o mecanismo de planejamento mestre preterido, ao usar um código de cobertura mín./máx. onde nenhum valor mínimo ou máximo é definido, o mecanismo de planejamento trata o código de cobertura como um requisito e cria uma ordem para cada requisito. Com a otimização de planejamento, o sistema criará uma ordem por dia para cobrir o valor total desse dia.  |
| Requisitos líquidos e ordens planejadas criadas manualmente | Com o mecanismo de planejamento mestre preterido, as ordens de fornecimento criadas manualmente para um item aparecem automaticamente entre os requisitos líquidos para aquele item. Por exemplo, ao criar uma ordem de compra a partir de uma ordem de venda, a ordem de compra aparece na página **Requisitos líquidos** sem exigir ações anteriores. Isso ocorre porque o mecanismo de planejamento mestre preterido registra as transações de estoque na tabela do `inventLogTTS` e mostra as alterações na página **Requisitos líquidos** para planos dinâmicos. No entanto, com a Otimização de Planejamento, as ordens criadas manualmente não aparecerão entre os requisitos líquidos de um item até que a Otimização de Planejamento seja executada (usando um plano que inclui o item) ou até você selecionar **Atualizar \> Planejamento mestre** no Painel de Ações na página **Requisitos líquidos**, que executará o planejamento mestre para o item. Para obter mais informações sobre como trabalhar com a página **Requisitos líquidos**, consulte [Requisitos líquidos e informações de vinculação](net-requirements.md). |
| Atribuição de recursos | Ao trabalhar com capacidade infinita, o mecanismo de planejamento mestre preterido atribui todas as ordens planejadas ao mesmo recurso em um determinado grupo de recursos. A Otimização de Planejamento melhora isso selecionando os recursos aleatoriamente, de forma que diferentes ordens de produção possam usar diferentes recursos. Se quiser usar o mesmo recurso para todas as ordens planejadas, você deverá especificar o recurso no roteiro. |
| Tipos de dados estendidos (EDTs) | A otimização de planejamento é incompatível com alterações na precisão de EDTs. Isso significa que esse processo não recebe suporte oficial e não é garantido que funcione. |
| Atendimento de estoque de segurança | A otimização de planejamento sempre usa um **Mínimo de preenchimento** de  *Data de hoje + tempo de aquisição*. Isso prepara o sistema para usar uma configuração de planejamento simplificada no futuro e fornece um resultado acionável. Se o tempo de compras não for incluído no estoque de segurança, as ordens planejadas criadas para o estoque baixo sempre estarão atrasadas por conta do prazo de entrega. Esse comportamento pode causar um ruído significativo e ordens planejadas indesejadas. A prática recomendada é alterar a configuração para usar *Data de hoje + tempo de aquisição*. Atualize os dados mestres para evitar avisos. |
| Copiar plano estático para dinâmico | A otimização de planejamento não copia planos estáticos para planos dinâmicos, independentemente da configuração na página **Parâmetros do planejamento mestre**. Em geral, essa operação é menos relevante devido à velocidade e à regeneração completa que a otimização do planejamento oferece. Se dois ou mais planos forem usados, o planejamento mestre deverá ser disparado para cada plano. |

## <a name="additional-resources"></a>Recursos adicionais

- [Análise de ajuste da Otimização do Planejamento](planning-optimization-fit-analysis.md)
- [Parâmetros não usados pela Otimização de Planejamento](not-used-parameters.md)
- [Parâmetros de data e hora usados pela Otimização de Planejamento](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
