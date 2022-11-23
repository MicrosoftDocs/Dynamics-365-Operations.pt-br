---
title: Criar faturas de ordem de venda
description: Este artigo descreve como faturar uma ordem de venda, incluindo mesclagem de faturas e processamento em lotes.
author: ShivamPandey-msft
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ff76eac54da6621d999d9b629fac920ba8de294
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778375"
---
# <a name="create-sales-order-invoices"></a>Criar faturas de ordem de venda

[!include [banner](../../includes/banner.md)]

Este artigo descreve como faturar uma ordem de venda, incluindo mesclagem de faturas e processamento em lotes. Este procedimento usa a empresa de dados de demonstração USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>Criar uma fatura de uma ordem de venda
1. Acesse **Painel de navegação > Módulos > Contas a receber > Ordens > ordens de vendas enviadas, mas não faturadas**.
2. Selecione uma ordem de venda na lista. 
3. No **Painel de Ação**, clique em **Fatura > Gerar > Fatura**. Observe que a ordem de venda tem várias guias de remessa associadas a ela. Só mostrará a palavra *múltiplo* em vez do número de guia de remessa.  
4. Expanda a seção **Parâmetros**.
    - O lançamento deve ser definido como **Sim** para lançar a fatura. Também é possível desativar o lançamento e imprimir apenas a nota fiscal. No entanto, você pode realizar o mesmo resultado criando uma nota fiscal do formulário em vez de uma nota fiscal.  
    - Essa opção é usada para trabalhos em lotes. A consulta será executada quando o trabalho em lotes for executado.
5. No campo **imprimir**, selecione **Após**.
6. Selecione **Sim** para **Imprimir fatura**. O gerenciamento de impressão pode imprimir várias cópias da fatura e também enviar a fatura por email como um arquivo PDF.  
7. No campo **Imprimir encargos**, selecione **Resumir**.
8. No campo **Verificar limite de crédito**, selecione **Saldo**.
9. Clique em **Cancelar**.

## <a name="combine-orders-into-a-single-invoice"></a>Combinar ordens em uma única nota fiscal
1. Acesse **Painel de navegação > Módulos > Contas a receber > Ordens > Todas as ordens de venda**.
2. Localize um cliente que tem várias notas fiscais abertas.
3. Selecione várias ordens de venda abertas do mesmo cliente.
4. No **Painel de Ação**, clique em **Fatura > Gerar > Fatura**.
5. Expanda a seção **Parâmetros**.
6. No campo **Quantidade**, selecione **Todas**. Observe que há duas notas fiscais listadas na seção da visão geral. Deixe-nos agora mescla-los em uma única nota fiscal.  
7. No campo **Atualização resumida de**, selecione **Conta de Fatura**.
8. Clique em **Organizar** para mesclar as ordens de venda em uma única fatura. As dois ordens de venda são mescladas agora em uma única nota fiscal.   
9. Clique em **Cancelar**.
10. Clique em **Sim**.

## <a name="post-invoices-in-a-batch"></a>Lançar notas fiscais em um lote
1. Acesse **Painel de Navegação > Módulos > Contas a receber > Faturas > Faturamento em lote > Fatura**.
2. Clique em **Selecionar**.
3. Clique em **OK**.
4. Clique em **Lote**.
5. Selecione **Sim** em **Processamento em lotes**.
6. Clique em **Recorrência**.
7. Selecione **Dias**.
8. Clique em **OK**.
9. Clique em **OK**.
10. Clique em **Cancelar**.
11. Clique em **Sim**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
