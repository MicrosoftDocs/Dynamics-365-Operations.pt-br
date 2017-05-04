---
title: "Visão geral das competências"
description: "Este artigo descreve competências, e fornece informações sobre como configurá-las e criar transações."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 328a4a7bef32ee8634e4a9f4854ebe78fcc99f6d
ms.lasthandoff: 03/31/2017


---

# <a name="accruals-overview"></a>Visão geral das competências

[!include[banner](../includes/banner.md)]


Este artigo descreve competências, e fornece informações sobre como configurá-las e criar transações.

As competências são usadas em regime de competência para rastrear a receita que é reconhecida no período em que é gerada, não quando o pagamento é recebido e para rastrear as despesas (custo) que são reconhecidas quando ocorrem, não quando o pagamento é efetuado.

## <a name="accrual-schemes"></a>Esquemas de competência
Os esquemas das competências são usados para configurar a receita e os custos diferidos e o mesmo esquema de competências pode ser usado para as receitas e os custos. As competências do razão redistribuem os custos ou as receitas de uma linha de diário para serem reconhecidos nos períodos apropriados. Na página **Esquema de competência**, você especifica o débito e as contas de crédito que serão usados quando o esquema de competência é aplicado.

-   **Débito** – A conta principal que você define substituirá a conta principal do débito na linha do comprovante do diário. Essa conta será usada também para a reversão de adiamento, com base nas transações de competência do razão.
-   **Crédito** – A conta principal definida substituirá a conta principal do crédito na linha do comprovante do diário. Essa conta será usada também para a reversão de adiamento, com base nas transações de competência do razão.

Depois que você determina quais contas usar, é possível especificar como o número do comprovante é criado quando as transações de competência são criadas. Você também pode especificar com que frequência as transações ocorrerão, o número de vezes em que as transações são criadas e quando as transações são lançadas. Depois que o esquema de competência foi criado, é possível usá-lo em qualquer um dos diários usando a função de competências do razão.

## <a name="ledger-accruals"></a>Competências do razão
Quando você insere um diário, é possível clicar em **Competências do razão** no menu **Funções**. Em seguida, quando você seleciona o esquema de competência, você verá o valor base do diário que será dividido durante o período, conforme determinado pelo esquema de competência. Por exemplo, se você pagar o seguro de um funcionário para todo o ano em janeiro e o valor for 12.000, você deve reconhecer as despesas todos os meses. Você pode selecionar a data de início. Você também pode especificar se o valor que é acumulado é baseado na conta ou na conta de compensação. Depois das seleções, clique em **Transações** para exibir todas as transações que foram criadas com base no esquema de competência. Por exemplo, se você tiver 12.000 em despesas de seguro durante o ano, você verá 1.000 para cada mês. Depois de lançar o diário, você pode exibir as transações usando a página de consulta **Transações de comprovante**. Se não for possível aplicar um esquema de competência (por exemplo, quando uma fatura de ordem de venda ou uma fatura de ordem de compra for envolvida), você pode creditar o valor pago antecipadamente e debitar o valor de despesas. Você pode selecionar **Contrapartida** ao aplicar o esquema de competência.




