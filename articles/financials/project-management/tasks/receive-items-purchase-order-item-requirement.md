--- 
title: "Receber itens na ordem de compra da requisição de itens"
description: "Este procedimento mostra como receber itens em uma ordem de compra de uma requisição de itens."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 0fa70da5e06d1bc82fb9d2419bb0a7c8dd0da467
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a>Receber itens na ordem de compra da requisição de itens

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como receber itens em uma ordem de compra de uma requisição de itens.

Usando uma requisição em vez de uma transação de itens, é possível planejar que entrega ocorra antes do item ser efetivamente usado, criar uma ordem de compra, incluir o item na estrutura do acordo comercial e incluir a requisição do item no planejamento da produção. 

Essa tarefa usa o conjunto de dados de USSI.

1. Vá para Gerenciamento e contabilidade de projeto > Projetos > Todos os projetos.
2. Na lista, clique no link na linha selecionada.
3. No Painel de Ação, clique em Plano.
4. Clique em Requisições de itens.
5. Clique em Novo.
6. Na lista, marque a linha selecionada.
7. No campo Número do item, insira ou selecione um valor.
8. No campo Quantidade, insira um número.
9. Clique em Salvar.
10. No Painel de Ação, clique em Gerenciar.
11. Clique em Funções.
12. Clique em Criar ordem de compra.
13. Selecione a caixa de seleção Incluir.
14. No campo Conta de fornecedor, insira ou selecione um valor.
15. Clique em OK.
16. Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.
17. Na lista, clique no link na linha selecionada.
18. No Painel de Ação, clique em Compra.
19. Clique em Confirmar.
20. No Painel de Ação, clique em Receber.
21. Clique em Recebimento de produtos.
22. Na lista, marque a linha selecionada.
23. No campo Recebimento de produtos, digite um valor.
24. Clique em OK.


