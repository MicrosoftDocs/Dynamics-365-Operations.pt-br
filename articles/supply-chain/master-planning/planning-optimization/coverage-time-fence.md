---
title: Limites de tempo de cobertura
description: Este tópico descreve como configurar limites de tempo de cobertura quando você estiver usando a otimização de planejamento. Um limite de tempo de cobertura indica o horizonte e o limite de planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 01/18/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-18
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 2b52a49109274c9be9ed8aa069517b175ea6281c
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501309"
---
# <a name="coverage-time-fences"></a>Limites de tempo de cobertura

Este tópico descreve como configurar *limites de tempo de cobertura* quando você estiver usando a otimização de planejamento. Os planejadores podem definir o horizonte de planejamento (o limite de tempo de cobertura em dias) e excluir o fornecimento e a demanda que estiverem fora desse horizonte. Portanto, os limites de tempo de cobertura ajudam a evitar o "ruído" que é causado por fornecer sugestões para as quais você não precisa reagir durante meses. Os exemplos incluem a previsão do ano seguinte e as ordens de cliente que estão programadas para muito depois do prazo de entrega normal.

Um limite de tempo de cobertura é o número de dias após a data de hoje (ou, mais precisamente, a data em que você executa o planejamento) em que o fornecimento e a demanda são excluídas. Para ajudar a evitar atrasos, você deve garantir que o limite de tempo de cobertura seja mais longo que o prazo de entrega total. O valor padrão do sistema é 100 dias.

Você pode especificar um limite de tempo de cobertura em cada um dos seguintes níveis:

- **Grupo de cobertura** – É possível definir um limite de tempo de cobertura padrão para cada grupo de cobertura.
- **Cobertura do item** – Você pode substituir o limite de tempo de cobertura herdado do grupo de cobertura atribuído a um item.
- **Plano mestre** – Você pode substituir o limites de tempo de cobertura herdados do grupo de cobertura atribuído às configurações de cobertura de um grupo e um item.

As seções a seguir explicam como especificar um grupo de cobertura em cada nível.

## <a name="set-a-coverage-time-fence-for-a-coverage-group"></a>Definir o limite de tempo de cobertura para um grupo de cobertura

Ao especificar um limite de tempo de cobertura para um grupo de cobertura, a configuração é aplicada a todos os itens (produtos) que pertencem a esse grupo. No entanto, você pode substituir a configuração para itens específicos ou planos mestre específicos.

Para especificar um limite de tempo de cobertura para um grupo de cobertura, siga estas etapas.

1. Vá para **Planejamento mestre \> Configuração \> Cobertura \> Grupos de cobertura**.
1. Selecione um grupo de cobertura existente na lista ou crie um novo grupo de cobertura.
1. Na guia rápida **Geral**, defina o campo **Limite de tempo de cobertura (dias)** como o número de dias que você deseja usar de limite de tempo de cobertura para o grupo de cobertura.

## <a name="set-a-coverage-time-fence-for-a-specific-item"></a>Definir o limite de tempo de cobertura para um item específico

Cada item (produto) pertence a um grupo de cobertura. Se nenhum grupo de cobertura for explicitamente atribuído a um item, um grupo de cobertura padrão será aplicado. Cada item herda um limite de tempo de cobertura de seu grupo de cobertura. No entanto, você pode substituir esse limite de tempo para itens específicos conforme necessário.

Para especificar um limite de tempo de cobertura para um item específico, siga estas etapas.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione um produto na grade.
1. Selecione o item e, depois, no Painel de Ações, na guia **Plano**, clique em **Cobertura** e selecione **Cobertura do item**.
1. Na página **Cobertura do item**, na guia **Visão geral**, selecione ou crie uma linha para o site em que você deseja definir um limite de tempo de cobertura.
1. Selecione a guia **Geral** para abrir as configurações do site selecionado.
1. Marque a caixa de seleção **Substituir configurações do grupo de cobertura**.
1. Defina o campo **Limite de tempo de cobertura (dias)** como o número de dias que você deseja usar de limite de tempo de cobertura para o item.

## <a name="set-a-coverage-time-fence-for-a-specific-master-plan"></a>Definir o limite de tempo de cobertura para um plano mestre

Você pode especificar um limite de tempo de cobertura no nível do plano mestre. Dessa forma, você define o número de dias que o cálculo do plano mestre abrange para um plano mestre. Essa configuração substitui as configurações de tempo de cobertura definidas para cada item e grupo de cobertura relevantes.

Para especificar um limite de tempo de cobertura para um plano mestre específico, siga estas etapas.

1. Vá para **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione um plano mestre existente na lista ou crie um novo plano mestre.
1. Na guia rápida **Limites de tempo em dias**, defina a opção **Cobertura** como *Sim*. No campo abaixo da opção, insira o número de dias que você deseja usar de limite de tempo de cobertura para o plano mestre.

## <a name="considerations-for-coverage-time-fences"></a>Considerações sobre limites de tempo de cobertura

Quando você estiver configurando limites de tempo de cobertura, considere os seguintes pontos:

- Os limites de tempo de cobertura afetam somente os dados de entrada para o plano mestre. Se ocorrerem atrasos, as ordens planejadas resultantes podem ter uma data posterior à data de hoje mais o limite de tempo de cobertura.
- Os limites de tempo de cobertura são especificados em dias corridos. Os calendários que usam dias úteis não afetarão o cálculo do limite de tempo. Por exemplo, uma semana é sempre considerada sete dias, mesmo que os finais de semana sejam configurados como dias fechados no calendário útil.
- As transações de necessidade não serão geradas para qualquer fornecimento e demanda que esteja fora do limite de tempo de cobertura.
- Se qualquer fornecimento e demanda aprovados ficar fora do limite de tempo de cobertura, ele não será carregado no mecanismo. Portanto, isso não acionará nenhum reabastecimento e os atrasos não serão calculados. No entanto, esse fornecimento e demanda não devem ser apagados do sistema.
- As variações nas quantidades de estoque de segurança (de chaves mínimas) serão ignoradas se estiverem fora do limite de tempo de cobertura.
- A demanda intercompanhia será ignorada se a data de remessa solicitada calculada não estiver dentro do limite de tempo de cobertura. Observe que, para planejamento mestre interno, a demanda intercompanhia não é limitada pelo limite de tempo de cobertura.
- As previsões de demanda serão ignoradas se a data de orçamento não estiver dentro do limite de tempo de cobertura. Observe que, para planejamento mestre interno, as previsões de demanda não são limitadas pelo limite de tempo de cobertura.
- A otimização do planejamento reconhece o fuso horário. Ele considera o fuso horário nos sites de fornecimento e demanda e o tempo de execução do planejamento. Por exemplo, o planejamento mestre é acionado às 11h de 15 de outubro de um site na Dinamarca (fuso horário GMT+1) e um limite de tempo de cobertura de dez dias é usado. Neste caso, o fornecimento e a demanda de um site em Seattle (fuso horário GMT-8) é incluído até 2h de 25 de outubro (= 10 dias de 24h após o planejamento mestre ter sido acionado, menos a diferença de fuso horário de nove horas). Observe que o mecanismo de planejamento mestre interno considera somente a data do limite de tempo. Portanto, o resultado pode ser diferente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]