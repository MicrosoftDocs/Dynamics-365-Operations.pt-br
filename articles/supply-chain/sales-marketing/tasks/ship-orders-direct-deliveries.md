---
title: Enviar ordens como entregas diretas
description: Este procedimento demonstra como criar uma entrega direta para uma ordem de venda.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchEditLines, PurchTableReferences, MCRDropShipWorkbench
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5cd68aa1c15672c702db887c08ecf9b3d63f2618
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557770"
---
# <a name="ship-orders-as-direct-deliveries"></a>Enviar ordens como entregas diretas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento demonstra como criar uma entrega direta para uma ordem de venda. Você usa a entrega direta quando quiser enviar mercadorias para o cliente diretamente do fornecedor, em vez de enviá-las para seu próprio depósito primeiro. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Para concluir com êxito a segunda subtarefa “Criar entregas diretas de bancada”, certifique-se de que o item que você escolhe na ordem de venda tem um Fornecedor padrão especificado na Guia Rápida Compra do mestre do produto Liberado.


## <a name="set-an-individual-order-for-direct-delivery"></a>Defina uma ordem individual para a entrega direta
1. Ir para Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta de cliente, insira ou selecione um valor.
    * Se você estiver usando USMF, é possível selecionar a conta US-001.  
4. Clique em OK.
5. No campo Número do item, insira ou selecione um valor.
    * Se você estiver usando USMF, é possível selecionar o item T0020.  
6. Clique em Salvar.
7. No Painel de Ação, clique em Ordem de venda.
8. Clique em Entrega direta.
    * A página Criar entrega lista todas as linhas da ordem de venda abertas como copiadas da ordem de venda. Você pode revisar os detalhes da ordem e, se necessário, pode modificar detalhes, como quantidade de compra e condições de preço de compra, antes de criar a entrega direta.  
9. Selecione Sim no campo Incluir tudo.
    * Se quiser gerar uma entrega direta só para um subconjunto de linhas da ordem de venda, selecione-as individualmente.  
    * O campo Conta de fornecedor poderá ou não ser preenchido com um número de fornecedor. Se o fornecedor padrão for configurado para o produto (na cobertura do Item associado), então este fornecedor será copiado para a linha. Caso contrário, você deverá inserir um fornecedor manualmente. Neste exemplo, vamos selecionar um novo fornecedor na próxima etapa, mesmo se uma já estiver preenchida.   
10. No campo Conta de fornecedor, insira ou selecione um valor.
    * Se você estiver usando USMF, é possível selecionar a conta 1001.  
11. Clique em OK.
    * A mensagem informa que a ordem de compra foi criada agora.   
12. Expanda a seção Detalhes da linha.
13. Clique na guia Entrega.
    * O campo Entrega direta é definido como Sim agora.  
    * O status de Entrega direta mostra a Ordem de compra criada.   
14. No Painel de Ação, clique em Geral.
15. Clique em Ordens relacionadas.
16. Clique para seguir o link no campo Ordem de compra.
17. Expanda a seção Detalhes da linha.
18. Clique na guia Endereço.
    * Observe que o endereço de entrega desta linha da ordem de compra é o endereço de entrega do cliente e não o endereço da empresa.  
    * Se você alterar o endereço de entrega na linha da ordem de compra ou na linha da ordem de venda original, o endereço na linha da ordem correspondente será atualizado automaticamente.  
19. Clique na guia Entrega.
    * Como a linha da ordem de venda, o tipo de linha da ordem de compra associada também é definido como Entrega direta.  
    * A data de entrega da linha da ordem de compra e a data de entrega Confirmada foram definidas como a Data de recebimento solicitada e a Data de recebimento confirmada da linha de ordem de venda original, respectivamente.   
    * Se você atualizar quaisquer uma dessas datas na linha de compra ou de vendas, as datas na ordem correspondente serão atualizadas automaticamente.     
    * A ordem de compra que é definida para entregar mercadorias diretamente ao cliente está vinculada à ordem de venda original, por meio de uma associação especial. Essa associação impõe a regra que a atualização da guia de remessa de ordem de venda não pode ser feita da própria ordem de venda e deve ser feita usando a ordem de compra. No entanto, o faturamento do cliente deve ser executado da ordem de venda.  
20. No Painel de Ação, clique em Compra.
21. Clique em Confirmação.
22. Clique em OK.
23. No Painel de Ação, clique em Receber.
24. Clique em Recebimento de produtos.
25. No campo Recebimento de produtos, digite um valor.
26. Clique em OK.
27. No Painel de Ação, clique em Geral.
28. Clique em Ordens relacionadas.
29. Na lista, marque a linha selecionada.
    * Depois que a ordem de compra foi atualizada como recebida, ou em outras palavras, depois que o fornecedor enviou as mercadorias ao endereço do cliente, o status da ordem de venda original é atualizado automaticamente como Entregue.  
    * A ordem de venda agora pode ser faturada.    
30. Clique em OK.
31. Feche a página.
32. Clique em OK.

## <a name="create-direct-deliveries-from-the-workbench"></a>Criar entregas diretas de bancada.
1. Feche a página.
2. Feche a página.
3. Ir para Todas as ordens de venda.
4. Clique em Novo.
5. No campo Conta de cliente, insira ou selecione um valor.
6. Clique em OK.
7. No campo Número do item, insira ou selecione um valor.
8. Expanda a seção Detalhes da linha.
9. Clique na guia Entrega.
    * Em vez de criar uma entrega direta como parte do processamento de ordem de venda como no procedimento anterior, você pode optar por ceder esta tarefa a um profissional de compra. Para incluir a linha da ordem de venda no processo de manuseio de entrega direta, você deve marcar a linha para a entrega direta.  
10. Selecione Sim no campo Entrega direta.
    *   Se o item já foi configurado para a entrega direta por padrão, o campo será automaticamente definido como Sim na entrada da linha da ordem. Você pode configurar um item da entrega direta no mestre do produto Liberado, definindo a opção de Entrega direta como Sim e selecionando um depósito de Entrega direta padrão.  
    * Como a ordem de compra ainda não foi criada, o status de Entrega direta é definido como Para ter entrega direta.   
11. Feche a página.
12. Feche a página.
13. Vá para Entrega direta.
    * A página Entrega direta atua como uma bancada que fornece ao agente de compras uma visão geral de todas as linhas da ordem de venda que terão entrega direta e permite que sejam criadas as respectivas ordens de compra. Além disso, as ordens de entrega direta abertas e as ordens confirmadas podem ser exibidas nas guias Confirmação e Entrega.   
14. Clique em Criar entrega direta.
15. Clique na guia Confirmação.
    * Depois de criar uma ordem de entrega direta, ela é movida automaticamente para a guia Confirmação. Você pode optar por confirmar a ordem diretamente nessa página. Quando a compra for confirmada, ela será movida automaticamente para a guia Entrega, onde você pode registrar seu recibo.  

