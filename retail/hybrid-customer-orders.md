---
title: "Ordens híbridos de cliente"
description: "Um ordem híbrido do cliente é, uma única ordem que contenha os produtos que podem ser realizados de armazenamento por cliente, além produtos a serem retirados enviados ou posterior."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1ddfc050cef94f4a31f5858b84c89eadfa726b95
ms.lasthandoff: 03/31/2017


---

# <a name="hybrid-customer-orders"></a>Ordens híbridos de cliente

Um ordem híbrido do cliente é, uma única ordem que contenha os produtos que podem ser realizados de armazenamento por cliente, além produtos a serem retirados enviados ou posterior.

No Microsoft Dynamics 365 para operações - venda para varejo, selecione executar todos os produtos ou executar produtos selecionados para uma ordem de cliente. As linhas do produto que estão marcadas como for faturadas automaticamente depois que a ordem é criada, de forma semelhante essas são as mesmas para uma ordem que deve ser separado - além depois que a ordem é criada. O valor devido em ordens híbridos - esta porcentagem de depósito nas linhas de produtos de separação e de remessa com o valor total das linhas da execução. Para ordens híbridos, o sistema de alternância entre o modo da ordem de cliente e o modo de pague-e-pegue maneira:

-   Se todos os produtos no carrinho serão definidos ** realize entrega **, a ordem será manipulado como uma transação de pague-e-pegue.
-   Se alguns ou todas as linhas são definidas no carrinho ou ** separação ** ou ** ** entrega de remessa, a ordem será manipulado como uma transação de ordem de cliente.

Se uma linha do carro está selecionada e ** separação selecionada ** **, navio selecionou **, ou Carry ** Out selecionada ** estiver selecionada, somente a linha específica móvel é definida com o método de entrega. Nesse caso, o fluxo a jusante de operação processa como de costume. Entretanto, se selecionou ** a separação ** **, navio selecionou **, ou Carry ** Out selecionada ** é selecionado sem uma linha do carro sendo selecionada, será aberto um novo página que liste todas as linhas do carro. Nessa tela, você pode selecionar várias linhas imediatamente para definir o método de entrega. Quando você usar esse método, selecionando linhas qualquer método anterior de entrega que é atribuído à linha será substituído.

<a name="see-also"></a>Consulte também
--------

[O cliente faz a visão geral (customer-orders-overview.md])


