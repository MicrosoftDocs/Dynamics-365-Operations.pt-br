---
title: Requisições de itens da ordem de serviço
description: Caso seja necessário reservar itens específicos para uma ordem de serviço, você poderá criar requisições de item de estoque para ele.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3ed17e968debf47d7d212a945975ae1cfaccdff4
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743224"
---
# <a name="service-order-item-requirements"></a>Requisições de itens da ordem de serviço   

[!include [banner](../includes/banner.md)]


Você pode criar uma ordem de serviço para rastrear e gerenciar os serviços que você presta para seus clientes. Caso seja necessário reservar itens específicos para uma ordem de serviço, você poderá criar requisições de item de estoque para ele. Uma requisição de item pode ser consumida imediatamente do estoque ou pode iniciar uma ordem de produção do item.

Usando uma requisição em vez de uma transação de itens, é possível planejar que entrega ocorra antes do item ser efetivamente usado, criar uma ordem de compra, incluir o item na estrutura do acordo comercial e incluir a requisição do item no planejamento da produção.

As requisições de itens para ordens de serviço são processadas através de um projeto. Para criar uma requisição de itens em uma ordem de serviço, a ordem de serviço deve ser anexada a um projeto.

Assim que uma requisição de itens é criada para uma ordem de serviço, ela pode ser exibida em **Projeto** na ordem de serviço individual ou através do formulário **Ordem de vendas**.

## <a name="view-an-item-requirement-from-a-service-order"></a>Exibir uma requisição de itens de uma ordem de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.

2.  Clique em **Expedição**, e depois clique em **Requisição de Itens** para abrir o formulário **Requisições de itens**.

3.  Clique na guia **Projeto** e verifique o campo **Ordem de serviço** para visualizar as ordens de serviço da requisição do item.

## <a name="delete-service-orders-with-item-requirements"></a>Excluir ordens de serviço com requisições de itens

Se uma requisição de itens for criada em uma ordem de serviço, não será possível excluir essa ordem. Você deve excluir a requisição de item antes de excluir a ordem de serviço.

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.

2.  Clique em **Expedição**, e depois clique em **Requisição de Itens** para abrir o formulário **Requisições de itens**. Este formulário lista as requisições de item que são criadas na ordem de serviço.

3.  Selecione a requisição de item a ser excluída e clique em **Excluir**.

–ou–

1.  Clique em **Gerenciamento e contabilidade de projeto** \> **Comum** \> **Projetos** \> **Todos os projetos**.

2.  Abra o projeto que possui a ordem de serviço na qual uma requisição de item é criada.

3.  No formulário **Projetos**, no painel direito, clique em **Requisições de itens**. O formulário **Requisições de itens** será aberto e listará as requisições de itens associadas ao projeto selecionado.

4.  Selecione a requisição de item a ser excluída e clique em **Excluir**.

## <a name="see-also"></a>Consulte também

[Requisições de itens (formulário)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))

