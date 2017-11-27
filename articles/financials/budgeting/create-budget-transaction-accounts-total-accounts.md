---
title: "Criar orçamentos de contas de transação e de contas totais"
description: "Este artigo fornece uma visão geral do processo para criar orçamentos com base nas contas totais. Também explica como ativar o controle de orçamento para as contas totais, se o controle de orçamento for necessário."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3e3c86bd32a05a392fcb82a86f2c461cc3abfb03
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>Criar orçamentos de contas de transação e de contas totais

[!include[banner](../includes/banner.md)]


Este artigo fornece uma visão geral do processo para criar orçamentos com base nas contas totais. Também explica como ativar o controle de orçamento para as contas totais, se o controle de orçamento for necessário.

Ambos os documentos de entrada de plano de orçamento e de registro de orçamento permitem fazer o orçamento em contas principais com um tipo de conta principal **Total**. Os números reais só podem ser lançados para as contas principais transacionais. 

Para o processo periódico **Gerar plano de orçamento da Contabilidade**, na guia **Origem**, você pode especificar o tipo de conta principal **Total** como um critério. Nesse caso, cada conta principal total será incluída no plano de orçamento de destino, e o valor será igual ao valor total do intervalo de contas principais selecionadas. 

Você pode ativar o controle de orçamento para contas principais do tipo **Total**. Essa funcionalidade tem suporte por meio do uso de grupos orçamentários. Para cada conta principal total, o orçamento que deve ser controlado para um grupo orçamentário deverá ser criado na página **Configuração de controle de orçamento**. Os critérios especificados devem incluir a conta principal total e o intervalo de contas. Para agilizar o processo de criação de grupos orçamentários, é possível aproveitar as vantagens da entidade de dados de grupos de Controle de orçamento. 

Quando um orçamento é usado em relatórios, como em um demonstrativo financeiro, a soma do orçamento para a conta de total consiste nos seguintes valores:

-   Os orçamentos que são criados de cada conta contábil de transação no intervalo da conta de total.
-   O total do orçamento especificado diretamente na conta de totais.

Portanto, você pode criar orçamentos separados para as contas de transação mais significativas no intervalo da conta de total e adicionar o valor de orçamento disponível à conta de total.




