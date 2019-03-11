---
title: Criar faturas de ordem de venda
description: Este guia descreve a tarefa de uma ordem de venda, incluindo mescla de notas fiscais e processamento em lotes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a57d204c0dcb44cbce7a0cc4d2f00b75b57e219
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "353301"
---
# <a name="create-sales-order-invoices"></a>Criar faturas de ordem de venda

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia descreve a tarefa de uma ordem de venda, incluindo mescla de notas fiscais e processamento em lotes. Este procedimento usa a empresa de dados de demonstração USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>Criar uma fatura de uma ordem de venda
1. Vá para Contas a receber > Ordens > Ordens de venda enviadas mas não faturadas.
2. Selecione uma ordem de venda na lista. 
3. No Painel de Ação, clique em Fatura.
4. Clique em Fatura.
    * Observe que a ordem de venda tem várias guias de remessa associadas a ela. Ela mostrará apenas a palavra <multiple>, em vez do número da guia de remessa.  
5. Expanda a seção Parâmetros.
    * O lançamento deve ser definido como Sim para lançar a fatura. Também é possível desativar o lançamento e imprimir apenas a nota fiscal. No entanto, você pode realizar o mesmo resultado criando uma nota fiscal do formulário em vez de uma nota fiscal.  
    * Essa opção é usada para trabalhos em lotes. A consulta será executada quando o trabalho em lotes for executado.    
6. No campo Imprimir, selecione 'Depois'.
7. Selecione Sim para imprimir nota fiscal.
    * O gerenciamento de impressão pode imprimir várias cópias de notas fiscais e também enviar a nota fiscal por email como um arquivo PDF.  
8. No campo Imprimir cobranças, selecione 'Resumir'.
9. No campo Limite de crédito do cheque, selecione 'Saldo'.
10. Clique em Cancelar.

## <a name="combine-orders-into-a-single-invoice"></a>Combinar ordens em uma única nota fiscal
1. Vá para Contas a receber > Ordens > Todas as ordens de venda.
2. Localize um cliente que tem várias notas fiscais abertas.
3. Selecione uma ordem de venda aberta.
4. Selecionar outra ordem de venda aberta para o mesmo cliente.
5. No Painel de Ação, clique em Fatura.
6. Clique em Fatura.
7. Expanda a seção Parâmetros.
8. No campo Quantidade, selecione 'Tudo'.
    * Observe que há duas notas fiscais listadas na seção da visão geral. Deixe-nos agora mescla-los em uma única nota fiscal.  
9. No campo Atualização de conteúdo, seleciona 'Contabilidade de fatura'.
10. Clique em Organizar para mesclar as ordens de venda em uma única fatura.
    * As dois ordens de venda são mescladas agora em uma única nota fiscal.   
11. Clique em Cancelar.
12. Clique em Sim.

## <a name="post-invoices-in-a-batch"></a>Lançar notas fiscais em um lote
1. Vá para Contas a receber > Faturas > Faturamento em lote > Fatura.
2. Clique em Selecionar.
3. Clique em OK.
4. Clique em Lote.
5. Clique em Sim para ativar o processamento em lotes.
6. Clique em Recorrência.
7. Selecionar dias
8. Clique em OK.
9. Clique em OK.
10. Clique em Cancelar.
11. Clique em Sim.

