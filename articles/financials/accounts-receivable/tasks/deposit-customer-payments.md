---
title: Depositar pagamentos de cliente
description: Depositar pagamentos de cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f58cebce20e8516dc918e0bad1e020ffd7f791ee
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "313373"
---
# <a name="deposit-customer-payments"></a>Depositar pagamentos de cliente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Depositar pagamentos de cliente. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contas a receber > Pagamentos > Diário de pagamentos.
2. Clique em Novo.
3. No campo Nome, clique no botão suspenso para abrir a pesquisa.
4. Selecione o diário de pagamentos. 
5. Clique em Linhas.
6. No campo Conta, selecione o Cliente para o qual você está registrando o pagamento.
7. No campo Crédito, insira o valor do pagamento.
    * Você pode optar por manter o valor em branco, e fazer com que o sistema o calcule selecionando as faturas que foram pagas.  
8. No campo Referência de pagamento, digite um valor.
    * A referência de pagamento pode ser o número do cheque para pagamento que você está inserindo. A referência do pagamento é necessária para incluir o pagamento em um comprovante de pagamento.  
9. Marque a caixa Usar uma guia de depósito.
    * Se o pagamento for incluído no depósito, altere essa configuração para Sim.  
10. Clique em Novo.
11. No campo Conta, selecione o Cliente para o próximo pagamento.
12. No campo Crédito, insira o valor do pagamento.
13. No campo Referência de pagamento, digite um valor.
14. Marque a caixa Usar uma guia de depósito.
15. Clique em Lançar.
    * Os pagamentos devem ser lançados antes que a guia de depósito possa ser gerada. Isso garante que os pagamentos não se alterem depois que a guia de depósito for gerada.  
16. Clique em Funções.
17. Clique em guia de depósito.
18. Clique em OK.
    * A primeira página é usada para criar a guia de depósito.  
19. Clique em OK.
    * A segunda etapa é imprimir a guia de depósito, mas essa etapa não é necessária.  

