---
title: Liquidar um cheque pré-datado de um cliente
description: É possível liquidar um cheque pré-datado após o cheque ter sido liberado pelo banco.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab591fc3ac529e65c15ee083377954a83363edd528861aff9bc449bfc10c7735
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771719"
---
# <a name="settle-a-postdated-check-from-a-customer"></a>Liquidar um cheque pré-datado de um cliente

[!include [banner](../../includes/banner.md)]

É possível liquidar um cheque pré-datado após o cheque ter sido liberado pelo banco. Esta transação financeira também libera a transação da conta de ponte do cheque pré-datado. 

As tarefas a seguir devem ser concluídas antes de iniciar esta.

1) Configurar cheques pré-datados

2) Registrar e lançar um cheque pré-datado para um cliente 



A função desta guias de tarefas é Tesoureiro.



Este procedimento usa a empresa de dados de demonstração USMF.

1. Acesse Crédito e cobranças > Consultas e relatórios > Pagamentos > Cheques pré-datados do cliente.
2. Clique em Liquidar.
3. Clique em Liquidar entradas de compensação.
    * Liquide a conta do cliente para a transação do cheque.  
4. Feche a página.
5. Ir para Contabilidade > Entradas de diários > Diários gerais.
6. No campo Mostrar, selecione uma opção.
7. Marque ou desmarque a caixa de seleção Mostrar apenas os que foram criados por usuário.
8. Na lista, localize e selecione o PDV desejado.
9. Clique em Linhas.
10. Clique em Comprovante.
11. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]