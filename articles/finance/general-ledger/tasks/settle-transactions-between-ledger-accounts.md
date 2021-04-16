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
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2594b90ed58a1e7f12c8a94d3c48266faef557f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817044"
---
# <a name="settle-transactions-between-ledger-accounts"></a>Liquidar transações entre contas contábeis

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como liquidar transações entre contas contábeis e cancelar uma liquidação do razão. Este procedimento usa a empresa de dados de demonstração USMF.


## <a name="settle-transaction-between-ledger-accounts"></a>Liquidar transação entre contas contábeis
1. Vá para Contabilidade > Tarefas periódicas > Liquidações do razão.
2. Na lista, localize a transação que você deseja liquidar.
   > [!NOTE]
   > O saldo do valor deve ser zero.  
3. Clique em Incluir.
4. Clique em Aceitar.

## <a name="cancel-a-ledger-settlement"></a>Cancelar uma liquidação do razão

1. Vá para Contabilidade > Consultas e relatórios > Balancete.
2. Clique em Parâmetros para abrir a caixa de diálogo suspensa.
3. Clique em Atualizar.
4. Na lista, localize a conta com a transação liquidada.
5. Clique em Todas as transações.
6. Use um filtro para encontrar facilmente a transação na lista.
7. Clique em Liquidações do razão.
8. Na lista, marque a linha selecionada.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]