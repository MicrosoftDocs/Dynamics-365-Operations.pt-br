---
title: Registrar comissões de vendas
description: Este tópico explica como comissões de vendas são calculadas e registradas.
author: omulvad
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee75f3a0c9dea7a7c4a4f927651aaab1d6bdb5c0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836365"
---
# <a name="register-sales-commissions"></a>Registrar comissões de vendas

[!include [banner](../../includes/banner.md)]

Este tópico explica como comissões de vendas são calculadas e registradas. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Antes de iniciar este guia, faça o guia chamado "Configurar regras de comissão de venda" para se certificar de que você tem toda a configuração de cálculo de comissões necessária.

Anote os números de cliente e item que você escolheu para o processo de comissão e use-os quando for solicitada a criação de uma ordem de venda neste guia.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Faturar uma ordem de venda que qualifique um vendedor para uma comissão
1. No painel de navegação, acesse **Módulos > Vendas e marketing > Ordens de venda > Todas as ordens de venda**.
2. Selecione **Novo**.
3. No campo **Conta do cliente**, selecione o registro desejado no menu suspenso.
4. Selecione **OK**.
5. No Painel de Ações, selecione **Opções**.
6. Selecione **Alterar exibição**.
7. Selecione **Exibição do cabeçalho**.
8. Expanda a seção **Instalação**.

    - O valor no campo **Grupo de vendas** representa um grupo com um ou mais representantes de vendas atribuídos a ele. As pessoas no grupo são aquelas que receberão comissões quando a ordem é faturada, conforme distribuição e taxas predefinidas.   
    - O valor é copiado do cartão Cliente, mas você pode alterá-lo se desejar.  
    - O grupo de vendas também é copiado na linha da ordem de venda. Você pode alterá-lo para que ele possa ser diferente daquele no cabeçalho e/ou entre linhas.  
    - O valor no campo **Grupo de comissões** representa um grupo que você criou para um ou mais clientes com o objetivo de rastrear comissões.   
    - O valor é copiado do cartão Cliente, mas você pode alterá-lo se desejar.   

9. No Painel de Ações, selecione **Opções**.
10. Selecione **Alterar exibição**.
11. Selecione **Exibição de linha**.
12. No menu suspenso do campo **Número do item**, selecione o item que você configurou em comissões. 
13. No campo **Quantidade.**, insira um número Anote o valor líquido da linha. Ele representa a receita de vendas, que, nesse exemplo, é a base para o cálculo de comissões.  
14. Selecione **Salvar**.
15. No Painel de Ação, selecione **Fatura**.
16. Selecione **Fatura**.
17. Expanda a seção **Parâmetros**.
18. No campo **Quantidade**, selecione **Todas**.
19. Selecione **Sim** no campo **Lançamento**.
20. Selecione **OK** e depois **OK** no próximo painel. Pode levar um minuto ou mais para lançar a transação. Deixe que o processo seja concluído e não feche a página.  

## <a name="review-the-registered-sales-commissions"></a>Revisar as comissões de vendas registradas
1. No painel de ações, selecione **Fatura** e depois **Fatura** novamente.
2. No painel de ações, selecione **Fatura** e depois **Transações de comissão**.

    - A guia **Visão geral** exibe linhas que representam os valores de comissões a serem pagos aos representantes de venda que estão associados com a ordem de venda faturada. Vamos revisar os detalhes.  
    - Se você usou o guia "Configurar regras de comissão de venda" para configurar o grupo de **vendas por comissão**, dois vendedores receberão comissões de vendas, e a comissão é dividida igualmente entre eles.  
    - Nesse exemplo, o valor total da comissão é calculado como uma porcentagem da receita de vendas (o valor líquido da linha da ordem).  
3. Feche a página.
4. Selecione **Comprovante**. Você pode revisar as transações do comprovante quanto aos valores de comissão que foram lançados na despesa de comissão predefinida e nas contas de comissão a pagar.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]