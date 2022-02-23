---
title: Criar uma ordem de compra a partir de uma ordem de venda
description: Este procedimento mostra como criar uma ordem de compra que é baseada em uma ordem de venda.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4576e442c2f270932e20472a6c340dcac6d45246
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422582"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Criar uma ordem de compra a partir de uma ordem de venda

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar uma ordem de compra que é baseada em uma ordem de venda. As quantidades do produto na ordem de compra são designadas para atender a demanda da ordem de venda original. Atender a demanda de vendas desta forma é uma alternativa a um método mais abrangente e mais otimizado de Planejamento de requisitos de distribuição. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Criar uma ordem de compra de uma ordem de venda
1. Vá para **Painel de navegação > Módulos > Vendas e marketing > Ordens de venda > Todas as ordens de venda**.
2. Clique em **Novo**.
3. No campo **Conta do cliente**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Clique em **OK**.
6. No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o PDV desejado. Se você estiver usando USMF, é possível selecionar D0001.  
8. No campo **Quantidade.**, insira um número
9. Clique em **Adicionar linha**.
10. No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize e selecione o PDV desejado. Se você estiver usando USMF, é possível selecionar T0020.  
12. Na lista, clique no link na linha selecionada.
13. No campo **Quantidade.**, insira um número
14. Clique em **Salvar**.
15. No **Painel de Ação**, clique em **Ordem de venda**.
16. Clique em **Ordem de compra**. A página **Criar ordem de compra** lista todas as linhas da ordem de venda abertas que foram copiadas da ordem de venda. Você pode revisar os detalhes da ordem e, se necessário, pode modificar os detalhes selecionados, como quantidade de compra e condições de preço, antes de criar as compras. 
17. Selecione a opção **Incluir tudo**.
    - Se quiser gerar ordens de compra para só um subconjunto de linhas da ordem de venda, selecione-as individualmente.  
    - O campo **Conta de fornecedor** poderá ou não ser preenchido com um número de fornecedor. Se o fornecedor padrão for configurado para o produto (na cobertura do Item associado), então este fornecedor será copiado para a linha. Caso contrário, você deverá inserir um fornecedor manualmente.  Nesta guia, independentemente de o campo **Conta de fornecedor** conter um valor, as seguintes etapas o instruem para selecionar um novo fornecedor que é diferente para cada linha.  
18. No campo **Conta de fornecedor**, clique no botão suspenso para abrir a pesquisa.
19. Na lista, localize e selecione o registro desejado.
20. Na lista, clique no link na linha selecionada.
21. Selecione a segunda linha de ordem.
22. No campo **Conta de fornecedor**, clique no botão suspenso para abrir a pesquisa.
23. Na lista, localize e selecione o registro desejado.
24. Na lista, clique no link na linha selecionada.
25. Clique em **Validar**.
26. Clique em **OK**. A mensagem informa que uma ou mais ordens de compra foram criadas. O sistema gera uma ordem de compra separada para cada fornecedor especificado nas linhas da ordem de venda. Isso significa que se várias linhas de ordens de venda forem fornecidas pelo mesmo fornecedor, uma única ordem de compra com várias linhas será gerada.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Revise as ordens de compra criadas das ordens de venda
1. No **Painel de Ações**, clique em **Geral**.
2. Clique em **Ordens relacionadas**. A página **Ordens relacionadas** lista as ordens criadas com base na ordem de venda. Neste exemplo, há duas ordens de compra geradas para dois fornecedores diferentes, respectivamente. 
3. Clique para seguir o link no campo **Ordem de compra**. Cada linha da ordem de compra é associada à linha da ordem de venda que gerou a compra. A relação com a ordem de venda é indicada na guia **Produto** na Guia Rápida **Detalhes da linha**, nos campos **Tipo de referência**, **Número de referência** e **Lote de referência**.  
4. Expanda ou recolha a seção **Detalhes da linha**.
5. Clique na guia **Produto**.
    - O **Lote de referência** garante que os custos da compra atual sejam cobrados na ordem de venda anexada.  
    - Você pode navegar até a ordem de venda de origem abrindo o link no campo **Número de referência**.  

