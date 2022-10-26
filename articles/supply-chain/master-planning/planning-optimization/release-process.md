---
title: Processo de liberação da Otimização de Planejamento e histórico de versões
description: Este artigo fornece informações sobre o processo de liberação e o histórico de versões da Otimização de Planejamento.
author: t-benebo
ms.date: 10/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: e2437214b4a2a850f121bb86272bf7dc3d313507
ms.sourcegitcommit: b3579ac62e1ea15664a114abcc2409cad76d4f19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2022
ms.locfileid: "9682551"
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
| <p>[Códigos de disposição em lotes](../../inventory/batch-disposition-codes.md)</p><p>Incluir parâmetros de estoque disponível e transação de estoque em planos mestres</p><p>Melhorias gerais de desempenho, qualidade e estabilidade</p> | Não é necessário gerenciamento de recursos | 10 a 14 de outubro de 2022 |
| <p>[Agendamento de recursos com capacidade finita](finite-capacity.md)</p><p>Melhorias gerais de desempenho, qualidade e estabilidade</p> | Não é necessário gerenciamento de recursos | 19 a 23 de setembro de 2022 |
| Melhorias gerais de desempenho, qualidade e estabilidade | Não é necessário gerenciamento de recursos | 29 de agosto a 3 de setembro de 2022 |
| <p>[Manutenção centralizada do calendário](../supply-chain-calendars-master-planning.md)</p><p>[Sugestões para otimizar fornecimento existente](../action-messages.md)</p><p>[Suporte para subcontratação](../../production-control/manage-subcontract-work-production.md)</p><p>Melhorias gerais de desempenho, qualidade e estabilidade</p> | Não é necessário gerenciamento de recursos | 7 a 11 de março de 2022 |
| Suporte a prioridades de planejamento para ordens de produção | Disponível com a versão 10.0.25 como parte do recurso denominado *Suporte ao MRP baseado em prioridade para a Otimização de Planejamento*. | 12-18 de novembro de 2021 |
| Melhorias gerais de desempenho, qualidade e estabilidade | Não é necessário gerenciamento de recursos | 12-18 de novembro de 2021 |
| <p>Suporte para fórmulas de cálculo do tempo de processamento, roteiro de produção com sobreposição e número da operação de produção em transações de requisito</p><p>Mensagens de erro avançadas para o plano de produção relacionado a tempo limite, capacidade não encontrada e roteiro cíclico</p><p>Maior consistência ao calcular datas de recebimento e datas de emissão em ordens planejadas e ordens confirmadas</p><p>Melhorias gerais de desempenho, qualidade e estabilidade</p> | Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento* | 22 a 27 de outubro de 2021 |
| <p>Suporte para considerar porcentagem de sucata no cálculo do tempo de processamento</p><p>Suporte ao número de operação e ao uso de materiais durante agendamento</p> | Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento* | 5 a 7 de outubro de 2021 |
| <p>Suporte a tipos de trabalho de roteiro de produção: **Fila antes**, **Fila depois** e **Tempo de transporte**</p><p>Melhorias gerais de desempenho, qualidade e estabilidade</p> | Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento* | 25 a 30 de setembro de 2021 |
| <p>Suporte para planos mestres com o **Método de agendamento** definido como *Plano de operações*</p><p>Na página **Grupos de roteiros**, respeite as configurações das caixas de seleção **Ativação**, **Horário de trabalho** e **Capacidade** para linhas com um **Tipo de roteiro/trabalho** de *Configuração* ou *Processo* </p><p>Melhorias gerais de desempenho, qualidade e estabilidade</p> | <p>O plano de operações está disponível no gerenciamento de recursos a partir da versão 10.0.20</p><p>Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento*</p> | 9 a 17 de setembro de 2021 |
| Melhorias gerais de desempenho, qualidade e estabilidade | Não é necessário gerenciamento de recursos | 25 a 30 de agosto de 2021 |
| <p>Adição do campo **Prazo de entrega** para ordens planejadas.</p><p>Melhorias gerais de desempenho, qualidade e estabilidade.</p> | Não é necessário gerenciamento de recursos | 12 a 17 de agosto de 2021 |
| <p>Adição de requisitos de tipo de recurso para agendamento de capacidade infinita</p><p>Melhoria de eficiência de recursos e eficiência de calendário para agendamento de capacidade infinita</p><p>Para obter mais informações, consulte [Agendar com capacidade infinita](infinite-capacity-planning.md)</p> | <p>Disponível no gerenciamento de recursos a partir da versão 10.0.20</p><p>Nome do recurso: *Agendamento da capacidade infinita para a Otimização do Planejamento*</p> | 6 a 12 de julho de 2021 |
| Melhorias de qualidade geral | Não é necessário gerenciamento de recursos | 6 a 12 de julho de 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
