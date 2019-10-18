---
title: Receber itens na ordem de compra da requisição de itens
description: Este tópico explica como receber itens em uma ordem de compra de uma requisição de itens.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7afdae65c5ae7e3196c6b9f142dd87aec39b5ea3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174411"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a>Receber itens na ordem de compra da requisição de itens

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como receber itens em uma ordem de compra de uma requisição de itens.

Usando uma requisição em vez de uma transação de itens, é possível planejar que entrega ocorra antes do item ser efetivamente usado, criar uma ordem de compra, incluir o item na estrutura do acordo comercial e incluir a requisição do item no planejamento da produção. 

Essa tarefa usa o conjunto de dados de USSI.

1. No Painel de navegação, acesse **Módulos > Gerenciamento e contabilidade do projeto > Projetos > Todos os projetos**.
2. Na lista, selecione o link na linha desejada.
3. No Painel de Ações, selecione **Plano**.
4. Selecione **Requisições de itens**.
5. Selecione **Novo**.
6. Na nova linha, insira ou selecione um valor no campo **Número do item**.
7. No campo **Quantidade.**, insira um número
8. Selecione **Salvar**.
9. No Painel de Ação, selecione **Gerenciar**.
10. Selecione **Funções**.
11. Selecione **Criar ordem de compra**.
12. Selecione a caixa de seleção **Incluir tudo**.
13. No campo **Conta de fornecedor**, insira ou selecione um valor.
14. Selecione **OK**.
15. No painel de navegação, vá para **Módulos > Contas a pagar > Ordens de compra > Todas as ordens de compra**.
16. Na lista, selecione o link na linha desejada.
17. No Painel de Ação, selecione **Compra**.
18. Selecione **Confirmar**.
19. No Painel de Ação, selecione **Receber**.
20. Selecione **Recebimento de produtos**.
21. No campo **Recebimento de produtos**, digite um valor.
22. Selecione **OK**.

