---
title: "Princípios de liberação"
description: "Este tópico descreve os quatro princípios de liberação usados para o consumo de matéria-prima."
author: johanhoffmann
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgShopSupervisorReleaseOrders
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 54d438de096b0ff317d94a03d8ae572e6350a865
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="controlling-raw-material-consumption-by-using-flushing-principles"></a>Controle do consumo de matéria-prima usando princípios de liberação

[!include[banner](../includes/banner.md)]

Os princípios de liberação refletem diferentes estratégias de consumo de matérias-primas usadas nos processos de produção. O consumo é o processo que deduz o material do estoque disponível e define o valor dos materiais consumidos como **Trabalho em andamento** (WIP) para ordens de produção e ordens de lote. As matérias-primas normalmente são consumidas de um local configurado para o processo que consome o material. Esse local é conhecido como o local de entrada da produção.

Antes do consumo do material, os materiais serão movidos para o local de entrada. A ilustração a seguir mostra o processo.

[![scenario4a](./media/scenario4a.png)](./media/scenario4a.png)

1. Depósito de material
2. Separação de matéria-prima
3. Local de entrada de produção
4. Consumo de matéria-prima
5. Processo de produção

O consumo de material é controlado por estes quatro princípios de liberação:

- Manual
- Início
- Concluir
- Disponível no local

Os princípios de liberação são configurados em uma hierarquia de valores padrão. A hierarquia começa no produto liberado, onde o princípio de liberação tem o valor **Inicial**. Na lista de materiais (BOM) ou na linha da fórmula, o princípio de liberação do produto pode ser substituído. O princípio de liberação padrão nas linhas de BOM de produção ou nas linhas da fórmula de ordem de lote é obtido do produto ou do valor substituído na BOM ou nas fórmulas.

## <a name="description-of-the-flushing-principles"></a>Descrição dos princípios de liberação

### <a name="manual"></a>Manual
O princípio de liberação Manual indica que o registro de consumo de materiais é uma operação manual. Esse princípio será relevante, por exemplo, se você quiser controlar o tempo e se a quantidade de números de lote ou números de série tiver de ser contabilizada para fins de rastreamento. O consumo manual é registrado em um diário de lista de separação de produção. Para os itens habilitados para processos avançados de depósito, um fluxo portátil poderá ser aplicado.

### <a name="start"></a>Início
O princípio de liberação Inicial indica se o material será consumido automaticamente quando a ordem de produção for iniciada. O valor do material consumido é proporcional à quantidade iniciada. Quando o princípio de liberação Inicial for usado com o sistema de execução de fabricação, também poderá ser usado para liberar materiais quando uma operação ou um trabalho de processo for iniciado. Esse princípio será relevante, por exemplo, se a variação no consumo for baixa, se os materiais forem de baixo valor, se não houver requisitos de rastreamento ou se houver um tempo de execução curto em operações. 

### <a name="finish"></a>Concluir
O princípio de liberação Final indica se o material será automaticamente consumido quando a ordem de produção for relatada como concluída, ou quando uma operação configurada para consumir os materiais for registrada como concluída. O valor do material consumido é proporcional à quantidade relatada como concluída. Quando o princípio de liberação Final for usado com o sistema de execução de fabricação, também poderá ser usado para liberar materiais quando uma operação ou um trabalho de processo for concluído. Esse princípio será relevante nas mesmas situações do princípio Inicial. Entretanto, o princípio Final destina-se a operações que tenham um tempo de execução mais longo, onde os materiais não devem ser definidos como WIP antes da conclusão da operação. 

### <a name="available-at-location"></a>Disponível no local
O princípio de liberação Disponível no local indica se o material será automaticamente consumido quando for registrado como separado para produção. O material é registrado como separado do local quando o trabalho da separação de matéria-prima é concluído ou quando o material está disponível no local de entrada de produção e a linha de material é liberada para o depósito. A lista de separação gerada durante o processo é lançada em um trabalho em lotes. Esse princípio será relevante se, por exemplo, você tiver diversas atividades de separação em uma ordem de produção. Nesse caso, você não precisará atualizar a lista de separação manualmente e poderá obter uma exibição atual do saldo WIP.

