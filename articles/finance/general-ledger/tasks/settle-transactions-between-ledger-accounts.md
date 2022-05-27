---
title: Liquidar transações entre contas contábeis
description: Este procedimento mostra como liquidar transações entre contas contábeis e cancelar uma liquidação do razão.
author: aprilolson
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a871e379826626edbad2434b11281fce5e29e14e
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717296"
---
# <a name="settle-transactions-between-ledger-accounts"></a>Liquidar transações entre contas contábeis

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como liquidar transações entre contas contábeis e cancelar uma liquidação do razão. Este procedimento usa a empresa de dados de demonstração USMF.


## <a name="settle-transaction-between-ledger-accounts"></a>Liquidar transação entre contas contábeis
1. Acesse **Contabilidade > Tarefas periódicas > Liquidações do razão**.
2. Na lista, localize a transação que você deseja liquidar.
   > [!NOTE]
   > O saldo do valor deve ser zero.  
3. Clique em **Incluir**.
4. Clique em **Aceitar**.

## <a name="cancel-a-ledger-settlement"></a>Cancelar uma liquidação do razão

1. Acesse **Contabilidade > Consultas e relatórios > Balancete**.
2. Clique em **Parâmetros** para abrir o diálogo suspensa.
3. Clique em **Atualizar**.
4. Na lista, localize a conta com a transação liquidada.
5. Clique em **Todas as transações**.
6. Use um filtro para encontrar facilmente a transação na lista.
7. Clique em **Liquidações do razão**.
8. Na lista, marque a linha selecionada.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
