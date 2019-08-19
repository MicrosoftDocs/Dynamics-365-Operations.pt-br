---
title: Enviar ordens como entregas diretas
description: Este tópico demonstra como criar uma entrega direta para uma ordem de venda.
author: omulvad
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchEditLines, PurchTableReferences, MCRDropShipWorkbench
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bce2674b321475bc516724f74bac2d3a648e257
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843352"
---
# <a name="ship-orders-as-direct-deliveries"></a>Enviar ordens como entregas diretas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico demonstra como criar uma entrega direta para uma ordem de venda. Você usa a entrega direta quando quiser enviar mercadorias para o cliente diretamente do fornecedor, em vez de enviá-las para seu próprio depósito primeiro. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Para concluir com êxito a segunda subtarefa “Criar entregas diretas de bancada”, certifique-se de que o item que você escolhe na ordem de venda tem um Fornecedor padrão especificado na Guia Rápida Compra do mestre do produto Liberado.

## <a name="set-an-individual-order-for-direct-delivery"></a>Defina uma ordem individual para a entrega direta
1. Vá para **Painel de navegação > Módulos > Contas a receber > Ordens > Todas as ordens de venda**.
2. Selecione **Novo**.
3. Insira ou selecione um valor no campo **Conta de cliente** e então selecione **OK**
4. Insira ou selecione valores nos campos **Número do item** e **Site**, então selecione **Salvar**.
5. No Painel de ação, selecione **Ordem de venda** e então **Entrega direta**. A página Criar entrega lista todas as linhas da ordem de venda abertas como copiadas da ordem de venda. Você pode revisar os detalhes da ordem e, se necessário, pode modificar detalhes, como quantidade de compra e condições de preço de compra, antes de criar a entrega direta.  
6. Selecione **Sim** no campo **Incluir tudo**.
    - Se quiser gerar uma entrega direta só para um subconjunto de linhas da ordem de venda, selecione-as individualmente.  
    - O campo **Conta de fornecedor** poderá ou não ser preenchido com um número de fornecedor. Se o fornecedor padrão for configurado para o produto (na cobertura do Item associado), então este fornecedor será copiado para a linha. Caso contrário, você deverá inserir um fornecedor manualmente. Neste exemplo, vamos selecionar um novo fornecedor na próxima etapa, mesmo se uma já estiver preenchida.   
7. Insira ou selecione um valor no campo **Conta de fornecedor** e então selecione **OK**. A mensagem informa que a ordem de compra foi criada agora.   
8. Expanda a seção **Detalhes da linha**.
9. Selecione a guia **Entrega** e verifique se o campo **Entrega direta** está definido como **Sim**.
10. No Painel de Ação, selecione **Geral**.
11. Selecione **Ordens relacionadas**.
12. Selecione o link no campo **Ordem de compra**.
13. Expanda a seção **Detalhes da linha** e selecione a guia **Endereço**.
    - O endereço de entrega desta linha da ordem de compra é o endereço de entrega do cliente e não o endereço da sua empresa.  
    - Se você alterar o endereço de entrega na linha da ordem de compra ou na linha da ordem de venda original, o endereço na linha da ordem correspondente será atualizado automaticamente.  
14. Selecione a guia **Entrega**.
    - Como a linha da ordem de venda, o tipo de linha da ordem de compra associada também é definido como Entrega direta.  
    - A data de entrega da linha da ordem de compra e a data de entrega Confirmada foram definidas como a Data de recebimento solicitada e a Data de recebimento confirmada da linha de ordem de venda original, respectivamente.   
    - Se você atualizar quaisquer uma dessas datas na linha de compra ou de vendas, as datas na ordem correspondente serão atualizadas automaticamente.     
    - A ordem de compra definida para entregar mercadorias diretamente ao cliente está vinculada à ordem de venda original por meio de uma associação especial. Essa associação impõe a regra que a atualização da guia de remessa de ordem de venda não pode ser feita da própria ordem de venda e deve ser feita usando a ordem de compra. No entanto, o faturamento do cliente deve ser executado da ordem de venda.  
15. No Painel de Ação, selecione **Compra**.
16. Selecione **Confirmação**.
17. Selecione **OK**.
18. No Painel de Ação, selecione **Receber**.
19. Selecione **Recebimento de produtos**.
20. No campo **Recebimento de produtos**, digite um valor.
21. Selecione **OK**.
22. No Painel de Ação, selecione **Geral**.
23. Selecione **Ordens relacionadas** e realce o registro desejado.
    - Depois que a ordem de compra foi atualizada como recebida, ou em outras palavras, depois que o fornecedor enviou as mercadorias ao endereço do cliente, o status da ordem de venda original é atualizado automaticamente como Entregue.  
    - A ordem de venda agora pode ser faturada.    
24. Selecione **OK**.
25. Feche a página.
26. Selecione **OK**. Feche as páginas e volte para a home page.

## <a name="create-direct-deliveries-from-the-workbench"></a>Criar entregas diretas de bancada.
1. Vá para **Navegação > Módulos > Contas a receber > Ordens > Todas as ordens de venda**.
2. Selecione **Novo**.
3. Insira ou selecione um valor no campo **Conta de cliente** e então selecione **OK**.
4. Insira ou selecione um valor nos campos **Número do item** e **site**.
5. Expanda a seção **Detalhes da linha**, então selecione a guia **Entrega**. Em vez de criar uma entrega direta como parte do processamento de ordem de venda como no procedimento anterior, você poderá delegar essa tarefa a um profissional de compra. Para incluir a linha da ordem de venda no processo de manuseio de entrega direta, você deve marcar a linha para a entrega direta.  
6. Selecione **Sim** no campo **Entrega direta**.
    - Se o item já foi configurado para a entrega direta por padrão, o campo será automaticamente definido como Sim na entrada da linha da ordem. Você pode configurar um item da entrega direta no mestre do produto Liberado, definindo a opção de Entrega direta como Sim e selecionando um depósito de Entrega direta padrão.  
    - Como a ordem de compra ainda não foi criada, o status de Entrega direta é definido como "Para ter entrega direta".   
7. Selecione **Salvar**.
8. Feche as páginas até voltar para a home page.
9. Insira `Direct delivery` na barra de pesquisa.
    - A página Entrega direta atua como uma bancada que fornece ao agente de compras uma visão geral de todas as linhas da ordem de venda que terão entrega direta e permite que sejam criadas as respectivas ordens de compra. Além disso, as ordens de entrega direta abertas e as ordens confirmadas podem ser exibidas nas guias Confirmação e Entrega.  
    - Depois de criar uma ordem de entrega direta, ela é movida automaticamente para a guia Confirmação. Você pode optar por confirmar a ordem diretamente nessa página. Quando a compra for confirmada, ela será movida automaticamente para a guia Entrega, onde você pode registrar seu recibo.  

