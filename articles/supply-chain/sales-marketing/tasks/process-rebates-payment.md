--- 
title: Processar reembolsos para pagamento
description: "Este procedimento demonstra como converter reembolsos de cliente aprovados e processados para notas de crédito."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 791ec304b9ea7c49fbea506d73c4daffd4478739
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="process-rebates-for-payment"></a>Processar reembolsos para pagamento

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento demonstra como converter reembolsos de cliente aprovados e processados para notas de crédito. Você pode utilizar esse guia na empresa demonstrativa USMF. A pré-condição para essa guia é ter uma ou mais reivindicações de reembolso com status Marcar. Se você estiver utilizando USMF você deve executar o guia "Gerar e processar reembolsos de cliente" antes de iniciar esse guia.


## <a name="convert-rebate-claims-to-credit-note"></a>Converter reivindicações de reembolso para nota de crédito.
1. Vá para Todos os clientes.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. No Painel de Ação, clique em Coletar.
5. Clique em Liquidar transações.
6. Clique em Funções.
7. Clique em Programa de reembolso.
    * A página Reembolso lista as reivindicações de reembolso que você processou na bancada de reembolso de cliente e que estão com status Marcar.    
8. Clique em Editar.
    * Defina marcas de verificação no campo Marcar para as reivindicações que você deseja incluir na nota de crédito.   
9. Clique em Funções.
10. Clique em Criar nota de crédito.
    * Uma mensagem aparece para informá-lo que um diário foi lançado (Esse é o Diário de consumo de contas a receber, como especificado na página Parâmetros de contas a receber). Isso faz com o valor real da dívida (crédito) seja movimentado para o saldo do cliente. Isso significa que a conta do cliente foi creditada, e a Conta de provisão de reembolso foi debitada.  
11. Feche a página.
12. Clique em Cancelar.
    * Isso atualiza a página para que você possa ver as atualizações.  
13. No Painel de Ação, clique em Coletar.
14. Clique em Liquidar transações.
    * Observe que uma transação para valor negativo, representando o valor total do reembolso, sem referência de fatura foi adicionada ao saldo do cliente.   
15. Clique em Cancelar.


