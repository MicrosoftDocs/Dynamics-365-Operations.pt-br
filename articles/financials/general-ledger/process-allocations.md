---
title: "Processar alocações"
description: "Este artigo fornece informações sobre alocações, as opções de processamento no Microsoft Dynamics 365 for Finance and Operations, e como podem ser usadas no planejamento de orçamento. As alocações são usadas para distribuir valores nas várias combinações da conta contábil. Ajuda a garantir que as despesas ou a receita sejam carregadas ao objeto correto na contabilidade."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 26e7f607e070ac6c09a92d7809d65bac34d51f0b
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="process-allocations"></a>Processar alocações

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre alocações, as opções de processamento no Microsoft Dynamics 365 for Finance and Operations, e como podem ser usadas no planejamento de orçamento. As alocações são usadas para distribuir valores nas várias combinações da conta contábil. Ajuda a garantir que as despesas ou a receita sejam carregadas ao objeto correto na contabilidade.

O Microsoft Dynamics 365 for Finance and Operations fornece os seguintes recursos para dar suporte a esse processo:

-   Alocar valores de transações manualmente usando a ação dividida em distribuições contábeis, ou aplicando modelos padrão de dimensão financeira para um documento. Para obter mais informações, consulte [Distribuições contábeis.](../accounts-payable/accounting-distributions.md)
-   Alocar automaticamente os valores das transações com base nas condições de alocação definidas na lista principal individual. As entradas da conta de alocação serão geradas para cada diário com base na porcentagem e na conta contábil de destino sempre que uma entrada contábil atender aos critérios definidos como a conta contábil de origem.
-   Alocar automaticamente os saldos ou valores fixos do razão com base nas regras de alocação do razão. As regras de alocação do razão são processadas periodicamente usando diários de alocação. 

###  <a name="allocations-in-budget-planning"></a>Alocações no planejamento de orçamento

As regras de alocação do razão podem ser usadas para planos de orçamento. Quando você usa regras de alocação do razão no planejamento de orçamento, o trabalho regras de alocação funciona da mesma maneira que no razão, mas os dados de origem e destino são originários do plano de orçamento. Você pode selecionar manualmente as regras de alocação do razão a serem usadas para planos do orçamento. Como alternativa, você pode usar uma agenda de alocação que seja executada como parte de um processo de fluxo de trabalho.

> [!NOTE]
> Você não pode usar as regras de alocação do razão intercompanhia para o planejamento de orçamento.






