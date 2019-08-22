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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: afbf74d1cf3dc87e97dda0873115b5c7fa49ca3d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834454"
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

