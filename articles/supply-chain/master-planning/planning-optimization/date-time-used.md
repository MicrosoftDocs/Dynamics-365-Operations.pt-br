---
title: Parâmetros de data e hora usados pela Otimização de Planejamento
description: Este tópico fornece informações sobre os parâmetros de data e hora que a Otimização de Planejamento usa durante a operação.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-09-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: dc44778dba0a5b914c524ff2ad026ab2f8eb88aa
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700174"
---
# <a name="date-and-time-parameters-used-by-planning-optimization"></a>Parâmetros de data e hora usados pela Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Este tópico fornece informações sobre os parâmetros de data e hora que a Otimização de Planejamento usa durante a operação.

Enquanto o mecanismo interno de planejamento mestre usa datas de transação em todos os cálculos, a Otimização de Planejamento funciona com valores de data e hora convertidos em datas. Essa diferença no comportamento pode levar a situações em que, por exemplo, as transações de previsão criadas à meia-noite no dia em que o planejamento mestre é executado não sejam incluídas porque a Otimização de Planejamento considera que elas foram criadas antes da data atual.

## <a name="parameters-for-issue-and-demand-transactions"></a>Parâmetros para transações de saída e de demanda

A tabela a seguir lista os parâmetros que a Otimização de Planejamento usa ao processar transações de saída e de demanda.

| Parâmetro | Nome do parâmetro na Otimização de Planejamento | Descrição | Campo equivalente no Microsoft Dynamics 365 Supply Chain Management (na tabela ReqTrans) |
|---|---|---|---|
| Hora planejada da saída | `PlannedIssueTime` | A data planejada atualmente para a saída. | **Data final** (`FuturesDate`) e **Atrasado para a hora** (`FuturesTime`) |
| Horário solicitado da saída | `RequestedIssueTime` | A data da saída que foi solicitada pelo usuário e definida no Supply Chain Management. Esse parâmetro é aplicável somente a ordens planejadas liberadas ou aprovadas. Para ordens planejadas, ele está em branco por padrão. | **Data solicitada** (`ReqDateDlvOrig`) |
| Horário necessário da saída | `RequiredIssueTime` | A data de saída necessária que é ajustada pela Otimização de Planejamento. Se a hora de emissão solicitada estiver no passado quando a Otimização de Planejamento for executada, a hora necessária de saída será ajustada para o primeiro dia em aberto que não seja anterior à data de hoje. Se a hora solicitada de saída for marcada como bloqueada no calendário, a hora necessária de saída será ajustada para o primeiro dia em aberto antes dessa data. | **Data da necessidade** (`ReqDate`) e **Tempo de necessidade** (`ReqTime`) |
| Atraso da hora de saída | `IssueTimeDelay` | A diferença de tempo entre a hora de saída planejada e a hora solicitada de saída para ordens aprovadas e liberadas ou a hora necessária de saída. | **Atraso (em dias)** (`FuturesDays`) |

## <a name="parameters-for-receipt-and-supply-transactions"></a>Parâmetros para transações de recebimento e de fornecimento

A tabela a seguir lista os parâmetros que a Otimização de Planejamento usa ao processar transações de recebimento e de fornecimento.

| Parâmetro | Nome do parâmetro na Otimização de Planejamento | Descrição | Campo equivalente no Supply Chain Management (na tabela ReqTrans ou ReqPO) |
|---|---|---|---|
| Tempo planejado de disponibilidade | `PlannedAvailabilityTime` | A data planejada de disponibilidade para o recebimento. | **Data da necessidade** (`ReqDate`) e **Tempo de necessidade** (`ReqTime`) |
| Hora planejada do recebimento | `PlannedReceiptTime` | A data em que o recebimento chegará no local. | **Data final** (`FuturesDate`), **Atrasado para a hora** (`FuturesTime`) e **Data de entrega** (`ReqDateDlv`) ou **Data solicitada** (`ReqDateDlvOrig`) se a ordem ainda não estiver liberada. |
| Tempo de disponibilidade necessário | `RequiredAvailabilityTime` | A data de disponibilidade necessária que é ajustada pela Otimização de Planejamento. | **Data da necessidade** (`ReqDate`) e **Tempo de necessidade** (`ReqTime`) |
| Hora prevista do recebimento | `ExpectedReceiptTime` | A data prevista de recebimento para um recebimento liberado. O valor é definido pelo usuário no Supply Chain Management e não é ajustado pela Otimização de Planejamento. Este parâmetro se aplica somente aos recebimentos liberados. | **Data solicitada** (`ReqDateDlvOrig`) |
| Tempo necessário para o recebimento | `RequiredReceiptTime` | A data de recebimento necessária que é ajustada pela Otimização de Planejamento. | **Data da necessidade** (`ReqDate`) e **Tempo de necessidade** (`ReqTime`) |
| Tempo planejado para a ordem | `PlannedOrderingTime` | A data da ordem que é calculada pela Otimização de Planejamento. | **Data da ordem** (`ReqDateOrder`) e **Hora da ordem** (`ReqTimeOrder`) |
| Hora de início planejada para a atividade | `PlannedActivityStartTime` | A data em que a atividade deste recebimento deve começar. | **Data de início** (`SchedFromDate`) |
| Atraso na hora de recebimento | `ReceiptTimeDelay` | A diferença de tempo entre a hora planejada do recebimento e o tempo necessário para o recebimento. | **Atraso (dias)** (`FuturesDays`) e **Atrasado para a hora** (`FuturesTime`) |

## <a name="examples-of-date-parameter-use-by-planning-optimization"></a>Exemplos de parâmetros de data usados pela Otimização de Planejamento

Os planos nas ilustrações a seguir estão no nível diário, mas a Otimização de Planejamento é executada em um nível mais detalhado. Por exemplo, como as margens podem ser em horas, o tempo para a ordem do planejamento pode ser 22 de Janeiro de 2021, às 11h35 e assim por diante.

### <a name="example-1-simple-scenario"></a>Exemplo 1: cenário simples

Uma ordem de venda que tenha um tempo solicitado de saída para 22 de janeiro é coberta por uma ordem de compra. As seguintes configurações são usadas:

- Nenhum prazo de entrega
- Nenhum calendário (todos os dias estão abertos.)
- Nenhuma margem

A ilustração a seguir mostra esse cenário. (Selecione a ilustração para abrir uma versão maior.)

[![Cenário simples.](media/planning-service-dates-1-small.png)](media/planning-service-dates-1.png)

### <a name="example-2-lead-time-scenario"></a>Exemplo 2: cenário de prazo de entrega

Uma ordem de venda que tenha um tempo solicitado de saída para 22 de janeiro é coberta por uma ordem de compra. As seguintes configurações são usadas:

- Três dias de prazo de entrega
- Nenhum calendário (todos os dias estão abertos.)
- Nenhuma margem

A ilustração a seguir mostra esse cenário. (Selecione a ilustração para abrir uma versão maior.)

[![Cenário de prazo de entrega.](media/planning-service-dates-2-small.png)](media/planning-service-dates-2.png)

### <a name="example-3-margin-scenario"></a>Exemplo 3: cenário de margem

Uma ordem de venda que tenha um tempo solicitado de saída para 22 de janeiro é coberta por uma ordem de compra. As seguintes configurações são usadas:

- Três dias de prazo de entrega
- Margem de ordem de quatro dias
- Margem de disponibilidade de cinco dias
- Nenhum calendário (todos os dias estão abertos.)

A ilustração a seguir mostra esse cenário. (Selecione a ilustração para abrir uma versão maior.)

[![Cenário de margem.](media/planning-service-dates-3-small.png)](media/planning-service-dates-3.png)

### <a name="example-4-delay-scenario"></a>Exemplo 4: cenário de atraso

Uma ordem de venda que tenha o tempo solicitado de saída para 22 de janeiro é coberta por uma ordem de compra. Este exemplo usa as mesmas configurações que o exemplo 3, mas a data de planejamento foi mudada para 15 de Janeiro. Há falha no planejamento regressivo (marcadores vermelhos) porque o tempo planejado para a ordem deve ser anterior à data de hoje. Portanto, o planejamento mestre deve avançar o agendamento, e ocorrem atrasos.

A ilustração a seguir mostra esse cenário. (Selecione a ilustração para abrir uma versão maior.)

[![Cenário de atraso.](media/planning-service-dates-4-small.png)](media/planning-service-dates-4.png)

### <a name="example-5-transfer-scenario"></a>Exemplo 5: cenário de transferência

Uma ordem de venda do depósito 1 que tenha um tempo solicitado de saída para 22 de Janeiro é coberta por uma ordem de transferência do depósito 2 coberta por uma ordem de compra planejada. As seguintes configurações são usadas:

- Três dias de prazo de entrega de transferência (depósito 1)
- Dois dias de prazo de entrega de compra (depósito 2)
- Nenhum calendário (todos os dias estão abertos.)

A ilustração a seguir mostra esse cenário. (Selecione a ilustração para abrir uma versão maior.)

[![Cenário de transferência.](media/planning-service-dates-5-small.png)](media/planning-service-dates-5.png)

### <a name="example-6-lead-time-with-calendars-scenario"></a>Exemplo 6: prazo de entrega com cenário de calendários

Uma ordem de venda que tenha um tempo solicitado de saída para 22 de janeiro é coberta por uma ordem de compra. As seguintes configurações são usadas:

- Três dias de prazo de entrega
- Calendário de saída (fechado na sexta-feira)
- Calendário de disponibilidade (fechado na quinta-feira e na sexta-feira)
- Calendário de recebimento (fechado na terça-feira, na quarta-feira e no domingo)
- Calendário de prazo de entrega (fechado na quinta-feira e na sexta-feira)
- Calendário de ordens (aberto na segunda-feira e no sábado)

A ilustração a seguir mostra esse cenário. (Selecione a ilustração para abrir uma versão maior.)

[![Prazo de entrega com cenário de calendários.](media/planning-service-dates-6-small.png)](media/planning-service-dates-6.png)

### <a name="example-7-delay-with-calendars-scenario"></a>Exemplo 7: Atraso com cenário de calendários

Uma ordem de venda que tenha um tempo solicitado de saída para 22 de janeiro é coberta por uma ordem de compra. Este exemplo usa as mesmas configurações que o exemplo 6, mas a data de planejamento foi mudada para 13 de Janeiro. Há falha no planejamento regressivo (marcadores vermelhos) porque o tempo planejado para a ordem deve ser anterior à data de hoje. Portanto, o planejamento mestre deve avançar o agendamento, e ocorrem atrasos.

A ilustração a seguir mostra esse cenário. (Selecione a ilustração para abrir uma versão maior.)

[![Atraso com cenário de calendários.](media/planning-service-dates-7-small.png)](media/planning-service-dates-7.png)
