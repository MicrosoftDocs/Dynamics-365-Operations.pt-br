--- 
title: Criar uma ordem de compra a partir de uma ordem de venda
description: "Este procedimento mostra como criar uma ordem de compra que é baseada em uma ordem de venda."
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
ms.openlocfilehash: 412a8c7acca06fc1be073019f91144e2a3f1c94b
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Criar uma ordem de compra a partir de uma ordem de venda

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar uma ordem de compra que é baseada em uma ordem de venda. As quantidades do produto na ordem de compra são designadas para atender a demanda da ordem de venda original. Atender a demanda de vendas desta forma é uma alternativa a um método mais abrangente e mais otimizado de Planejamento de requisitos de distribuição. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Criar uma ordem de compra a partir de uma ordem de venda
1. Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Clique em OK.
6. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o PDV desejado.
    * Se você estiver usando USMF, é possível selecionar D0001.  
8. No campo Quantidade, insira um número.
9. Clique em Adicionar linha.
10. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize e selecione o PDV desejado.
    * Se você estiver usando USMF, é possível selecionar T0020.  
12. Na lista, clique no link na linha selecionada.
13. No campo Quantidade, insira um número.
14. Clique em Salvar.
15. No Painel de Ação, clique em Ordem de venda.
16. Clique em Ordem de compra.
    * A página Criar ordem de compra lista todas as linhas da ordem de venda abertas que foram copiadas da ordem de venda. Você pode revisar os detalhes da ordem e, se necessário, pode modificar os detalhes selecionados, como quantidade de compra e condições de preço, antes de criar as compras.  
17. Selecione a opção Incluir tudo.
    * Se quiser gerar ordens de compra para só um subconjunto de linhas da ordem de venda, selecione-as individualmente.  
    * O campo Conta de fornecedor poderá ou não ser preenchido com um número de fornecedor. Se o fornecedor padrão for configurado para o produto (na cobertura do Item associado), então este fornecedor será copiado para a linha. Caso contrário, você deverá inserir um fornecedor manualmente.  Nesta guia, independentemente de o campo Conta de fornecedor já ter ou não um valor, as seguintes etapas o instruem para selecionar um novo fornecedor que é diferente de cada linha.  
18. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
19. Na lista, localize e selecione o registro desejado.
20. Na lista, clique no link na linha selecionada.
21. Selecione a segunda linha de ordem.
22. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
23. Na lista, localize e selecione o registro desejado.
24. Na lista, clique no link na linha selecionada.
25. Clique em Validar.
26. Clique em OK.
    * A mensagem informa que uma ou mais ordens de compra foram criadas. O sistema gera uma ordem de compra separada para cada fornecedor especificado nas linhas da ordem de venda. Isso significa que se várias linhas de ordens de venda forem fornecidas pelo mesmo fornecedor, uma única ordem de compra com várias linhas será gerada.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Revise as ordens de compra criadas das ordens de venda
1. No Painel de Ação, clique em Geral.
2. Clique em Ordens relacionadas.
    * A página Ordens relacionadas lista as ordens que foram criadas a partir da ordem de venda. Neste exemplo, há duas ordens de compra geradas para dois fornecedores diferentes, respectivamente.  
3. Clique para seguir o link no campo Ordem de compra.
    * Cada linha da ordem de compra é associada à linha da ordem de venda que gerou a compra. A relação com a ordem de venda é indicada na guia Produto na Guia Rápida Detalhes da linha, nos campos Tipo de referência, Número de referência e Lote de referência.  
4. Expandir ou recolher a seção Detalhes de linha.
5. Clique na guia de Produto.
    * O Lote de referência garante que os custos da compra atual sejam cobrados na ordem de venda anexada.  
    * Você pode navegar na ordem de venda original ao abrir o link no campo Número de referência.  


