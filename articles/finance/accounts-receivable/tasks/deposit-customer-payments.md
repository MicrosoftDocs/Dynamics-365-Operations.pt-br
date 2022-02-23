---
title: Depositar pagamentos de cliente
description: Depositar pagamentos de cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
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
ms.openlocfilehash: 1d903f557fbaeb720dd4a34dc1c772be0dcb56eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440344"
---
# <a name="deposit-customer-payments"></a>Depositar pagamentos de cliente

[!include [banner](../../includes/banner.md)]

Depositar pagamentos de cliente. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para **Painel de Navegação > Módulos > Contas a receber > Pagamentos > Diário de pagamentos**.
2. Selecione **Novo**.
3. No campo **Nome**, selecione **CustPay** no menu suspenso.
4. Selecione **Linhas**.
5. No campo **Conta**, selecione o cliente para o qual você está registrando o pagamento.
6. No campo **Crédito**, insira o valor do pagamento. Você pode optar por manter o valor em branco, e fazer com que o sistema o calcule selecionando as faturas que foram pagas.  
7. No campo **Referência de pagamento**, digite um valor. A referência de pagamento pode ser o número do cheque para pagamento que você está inserindo. A referência do pagamento é necessária para incluir o pagamento em um comprovante de pagamento.  
8. Marque a caixa Usar uma guia de depósito. Se o pagamento for incluído no depósito, altere essa configuração para Sim.  
9. Selecione **Novo**.
10. No campo **Conta**, selecione o cliente para o próximo pagamento.
11. No campo **Crédito**, insira o valor do pagamento.
12. No campo **Referência de pagamento**, digite um valor.
13. Marque a caixa **Usar uma guia de depósito**.
14. Selecione **Lançar**. Os pagamentos devem ser lançados antes que a guia de depósito possa ser gerada. Isso garante que os pagamentos não se alterem depois que a guia de depósito for gerada.  
15. Selecione **Funções**.
16. Selecione **Guia de depósito**.
17. Selecione **OK**. A primeira página é usada para criar a guia de depósito.  
18. Selecione **OK**. A segunda etapa é imprimir a guia de depósito, mas essa etapa não é necessária.  

