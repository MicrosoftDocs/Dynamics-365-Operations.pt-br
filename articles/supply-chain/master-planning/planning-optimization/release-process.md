---
title: Processo de liberação e histórico de versões da Otimização de Planejamento
description: Este tópico fornece informações sobre o processo de liberação e o histórico de versões da Otimização de Planejamento.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: fd6ecb0b7bc1fcf85feab2588622a96cf43b6155
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407835"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Processo de liberação e histórico de versões da Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

A Microsoft atualiza a Otimização de Planejamento mensalmente. No entanto, com base nas necessidades comerciais, lançamos, ocasionalmente, atualizações adicionais entre as versões agendadas.

Cada liberação é publicada nas regiões individuais nas quais a Otimização de Planejamento está disponível. O processo normalmente leva três dias.

Enquanto a Otimização de Planejamento estiver sendo atualizada, o planejamento mestre poderá funcionar pouco mais devagar do que o normal.

Os ambientes que usam a Otimização de Planejamento recebem automaticamente a versão mais recente. Nenhuma ação do usuário é necessária: o serviço é atualizado automaticamente. No entanto, nenhuma funcionalidade de alteração de quebra é enviada automaticamente para os ambientes. Por padrão, as alterações que são consideradas quebradas são desativadas e devem ser explicitamente ativadas usando o [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Portanto, essas alterações só aparecerão nos ambientes depois que você optar por habilitá-las.

Como as notificações não são mostradas quando a Otimização do Planejamento é atualizada no seu ambiente, você pode revisar as notas de versão na tabela a seguir para determinar quando as alterações foram lançadas e quais recursos foram introduzidos. Esta tabela mostra as alterações que foram lançadas para a Otimização de Planejamento, se essas alterações estão associadas a um recurso do gerenciamento de recursos e a data da liberação.

| Alterações | Detalhes do gerenciamento de recursos | Datas de liberação |
|---|---|---|
| <p>Melhorias gerais de desempenho, qualidade e estabilidade.<p>Manutenção centralizada do calendário para otimização de planejamento<p>Planejando sugestões de otimização para otimizar fornecimento existente | O gerenciamento de recursos não é necessário. | 7 a 11 de março de 2022 |
| <p>Suporte a prioridades de planejamento adicionado para ordens de produção. | Disponível com a versão 10.0.25 como parte do recurso denominado *Suporte ao MRP baseado em prioridade para a Otimização de Planejamento*. | 12-18 de novembro de 2021 |
| <p>Melhorias gerais de desempenho, qualidade e estabilidade. | O gerenciamento de recursos não é necessário. | 12-18 de novembro de 2021 |
| <p>Suporte adicionado para fórmulas de cálculo do tempo de processamento, roteiro de produção com sobreposição e número da operação de produção em transações de requisito.</p><p>Mensagens de erro avançadas para o plano de produção relacionado a tempo limite, capacidade não encontrada e roteiro cíclico.</p><p>Maior consistência ao calcular datas de recebimento e datas de emissão em ordens planejadas e ordens confirmadas.</p><p>Melhorias gerais de desempenho, qualidade e estabilidade. | Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento* | 22 a 27 de outubro de 2021 |
| <p>Suporte adicionado para considerar porcentagem de sucata no cálculo do tempo de processamento.</p><p>Suporte adicionado ao número de operação e ao uso de materiais durante agendamento. | Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento* | 5 a 7 de outubro de 2021 |
| <p>Suporte adicionado a tipos de trabalho de roteiro de produção: **Fila antes**, **Fila depois** e **Tempo de transporte**.</p><p>Melhorias gerais de desempenho, qualidade e estabilidade. | Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento* | 25 a 30 de setembro de 2021 |
| <p>Suporte adicionado para planos mestres com o **Método de planejamento** definido como *Plano de operações*.</p><p>Na página **Grupos de roteiros**, respeite as configurações das caixas de seleção **Ativação**, **Período de trabalho** e **Capacidade** para linhas com um **Tipo de roteiro/trabalho** de *Configuração* ou *Processo*. </p><p>Melhorias gerais de desempenho, qualidade e estabilidade. | <p>O plano de operações está disponível no gerenciamento de recursos a partir da versão 10.0.20.</p><p>Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento*</p>  | 9 a 17 de setembro de 2021 |
| Melhorias gerais de desempenho, qualidade e estabilidade. | O gerenciamento de recursos não é necessário. | 25 a 30 de agosto de 2021 |
| <p>Adição do campo **Prazo de entrega** para ordens planejadas.</p><p>Melhorias gerais de desempenho, qualidade e estabilidade.</p> | O gerenciamento de recursos não é necessário. | 12 a 17 de agosto de 2021 |
| <p>Adição de requisitos de tipo de recurso para agendamento de capacidade infinita.</p><p>Melhoria de eficiência de recursos e eficiência de calendário para agendamento de capacidade infinita.</p><p>Para obter mais informações, consulte [Agendar com capacidade infinita](infinite-capacity-planning.md). | <p>Disponível no gerenciamento de recursos a partir da versão 10.0.20.</p><p>Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento*</p> | 6 a 12 de julho de 2021 |
| Melhorias gerais de qualidade. | O gerenciamento de recursos não é necessário. | 6 a 12 de julho de 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
