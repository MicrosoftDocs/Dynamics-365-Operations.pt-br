---
title: Alocação de dados do planejamento de orçamento
description: Este artigo descreve os vários métodos de alocação disponíveis no Microsoft Dynamics 365 for Finance and Operations e como eles podem ser usados.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a706b83bc091053a76be951778df0ad0442e27e1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834190"
---
# <a name="budget-planning-data-allocation"></a>Alocação de dados do planejamento de orçamento

[!include [banner](../includes/banner.md)]

Este artigo descreve os vários métodos de alocação disponíveis no Microsoft Dynamics 365 for Finance and Operations e como eles podem ser usados.  

Você pode distribuir os dados em um plano de orçamento de várias formas para retratar com precisão os valores projetados.

## <a name="allocation-methods"></a>Métodos de alocação
Três métodos de alocação (alocar entre períodos, Alocar para dimensões e Usar regras de alocação do razão) podem criar linhas de plano de orçamento baseadas nas linhas do mesmo plano de orçamento. Outros três métodos (Agregar, Distribuir e Copiar do plano de orçamento) podem criar linhas do plano de orçamento em outros planos de orçamento. Para todos os seis métodos de alocação, você especifica o cenário de destino. O cenário de destino pode ser igual ao cenário de origem ou diferente do cenário de origem. Além disso, você pode especificar se novas linhas são anexadas ao plano de orçamento, ou substituir as linhas atuais no plano de orçamento.

[![AllocateAcrossPeriods](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Alocar entre períodos** – uma categoria de alocação de período é usada para alocar as linhas do plano de orçamento do cenário do plano de orçamento de origem entre períodos no cenário de destino. O valor de origem é atribuído a várias linhas no cenário de destino, com base na porcentagem e na data definidas na categoria de alocação de período.         

[![AllocateToDimensions](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Alocar para dimensões** – As linhas do plano de orçamento são alocadas do cenário de planejamento de orçamento de origem para uma ou mais linhas no cenário de destino, com base nas porcentagens e dimensões financeiras que são definidas em uma condição de alocação de orçamento selecionada.           

![AggregateChart](./media/aggregatechart-300x230.png)
**Agregar** – As linhas do plano de orçamento são agregadas do cenário do plano de orçamento de origem dos planos de orçamento associados (filhos) ao cenário de destino no plano de orçamento pai. Esse método permite que os valores de orçamento que são preparados em um nível inferior da organização sejam consolidados em um nível superior.          

[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Distribuir** – As linhas do plano de orçamento são distribuídas do cenário de planejamento de orçamento de origem no plano principal do orçamento para o cenário de destino nos planos de orçamento associados (filhos), com base nas dimensões financeiras das unidades organizacionais dos planos associados. Este método permite que os valores de orçamento que são preparados em um nível superior da organização sejam difundidos para uma análise mais localizada.           

[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Usar regras de alocação do razão** – As linhas do plano de orçamento são distribuídas do cenário de planejamento de orçamento de origem para o cenário de destino, com base na regra de alocação do razão selecionada. 

[![CopyFromBudgetPlan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Copiar do plano de orçamento** – Como no método Distribuir alocação, as linhas do plano de orçamento são criadas no destino, com base em linhas em um plano de orçamento relacionado. No entanto, neste método, o plano de orçamento de origem não precisa ser o pai, mas pode estar em um nível superior na hierarquia do plano de orçamento. Esse método de alocação é útil se os valores consolidados são orçados originalmente em um nível superior, e devem ser transferidos para um nível inferior da organização para análise e ajuste detalhados para poder receber a aprovação de nível superior.          

## <a name="using-allocation-methods-in-a-budget-plan"></a>Uso de métodos de alocação em um plano de orçamento
Para executar alocações na página do plano de orçamento, selecione as linhas para alocação e clique em **Alocar orçamento**.

[![AllocateBudgetButton](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

Em seguida, selecione um método de alocação. Os campos restantes são definidos com base no método selecionado. Esses campos incluem a origem e o destino dos dados do plano de orçamento, e uma opção que permite multiplicar a origem por um fator especificado quando os valores de destino são criados, para simplificar o ajuste em massa. Também é possível definir a opção **Acrescentar ao plano**. Selecione **Não** para substituir as linhas existentes do plano de orçamento, ou selecione **Sim** para reter as linhas existentes do plano de orçamento e adicionar novas linhas aos valores alocados.

## <a name="automating-allocations-during-a-workflow"></a>Automatização de alocações durante um fluxo de trabalho
Um recurso avançado permite que as alocações sejam executadas automaticamente, como parte de um fluxo de trabalho do planejamento de orçamento. Como um plano de orçamento se move no fluxo de trabalho, as tarefas automatizadas podem invocar uma alocação em uma fase específica de planejamento de orçamento. 

Para configurar a alocação automatizada, primeiro você deve criar uma agenda de alocação na página **Configuração de planejamento de orçamento**. A agenda de alocação define o método de alocação que será usado quando a alocação automatizada for executada, e os valores das várias opções de alocação (consulte a seção anterior para obter descrições). 

Em seguida, crie uma alocação de fase na página **Configuração de planejamento de orçamento**. A alocação de fase atribui uma agenda de alocação ao fluxo de trabalho e fase do planejamento de orçamento. 

Por fim, adicione uma tarefa automatizada para alocação de fase de planejamento de orçamento na fase de fluxo de trabalho desejada. No exemplo a seguir, duas alocações de fase de planejamento de orçamento (delineadas em vermelho) foram inseridas no fluxo de trabalho.

[![BudgetPlanningStageAllocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)



