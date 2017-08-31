--- 
title: "Registrar comissões de vendas"
description: "Este procedimento mostra como comissões de vendas são calculadas e registradas."
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f1e22f15e98b563f7d2aae812aee3df1d454524c
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="register-sales-commissions"></a>Registrar comissões de vendas

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como comissões de vendas são calculadas e registradas. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Antes de iniciar este guia, faça o guia chamado "Configurar regras de comissão de venda" para se certificar de que você tem toda a configuração de cálculo de comissões necessária.

Anote os números de cliente e item que você escolheu para o processo de comissão e use-os quando for solicitada a criação de uma ordem de venda neste guia.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Faturar uma ordem de venda que qualifique um vendedor para uma comissão
1. Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o PDV desejado.
5. Na lista, clique no link na linha selecionada.
6. Clique em OK.
7. No Painel de Ação, clique em Opções.
8. Clique em Alterar exibição.
9. Clique em Exibição do cabeçalho.
10. Expandir a seção Instalação.
    * O valor no campo Grupo de vendas representa um grupo com um ou mais representantes de vendas atribuídos a ele. As pessoas no grupo são aquelas que receberão comissões quando a ordem é faturada, conforme distribuição e taxas predefinidas.   O valor é copiado do cartão Cliente, mas você pode alterá-lo se desejar.  O grupo de vendas também é copiado na linha da ordem de venda. Você pode alterá-lo para que ele possa ser diferente daquele no cabeçalho e/ou entre linhas.  
    * O valor no campo Grupo de comissões representa um grupo que você criou para um ou mais clientes com o objetivo de rastrear comissões.   O valor é copiado do cartão Cliente, mas você pode alterá-lo se desejar.   
11. No Painel de Ação, clique em Opções.
12. Clique em Alterar exibição.
13. Clique em Exibição em linha.
14. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
15. Na lista, selecione o item que você definiu para comissões. 
16. No campo Quantidade, insira um número.
    * Anote o valor líquido da linha. Ele representa a receita de vendas, que, nesse exemplo, é a base para o cálculo de comissões.  
17. Clique em Salvar.
18. No Painel de Ação, clique em Fatura.
19. Clique em Fatura.
20. Expanda a seção Parâmetros.
21. No campo Quantidade, selecione 'Tudo'.
22. Selecione Sim no campo Lançamento.
23. Clique em OK.
24. Clique em OK.
    * Pode levar um minuto ou mais para lançar a transação. Deixe que o processo seja concluído e não feche a página.  

## <a name="review-the-registered-sales-commissions"></a>Revisar as comissões de vendas registradas
1. No Painel de Ação, clique em Fatura.
2. Clique em Fatura.
3. No Painel de Ação, clique em Fatura.
4. Clique em Transações de comissão.
    * A guia Visão geral exibe linhas que representam os valores de comissões a serem pagos aos representantes de venda que estão associados com a ordem de venda faturada. Vamos revisar os detalhes.     
    * Se você usou o guia "Configurar regras de comissão de venda" para configurar o grupo de vendas por comissão, dois vendedores receberão comissões de vendas, e a comissão é dividida igualmente entre eles.  
    * Nesse exemplo, o valor total da comissão é calculado como uma porcentagem da receita de vendas (o valor líquido da linha da ordem).   
5. Feche a página.
6. Clique em Comprovante.
    * Você pode revisar as transações do comprovante quanto aos valores de comissão que foram lançados na despesa de comissão predefinida e nas contas de comissão a pagar.  


