---
title: "Ordens de cliente híbrido"
description: "Um ordem de cliente híbrido é uma única ordem que contém os produtos que podem ser retirados da loja pelo cliente, além produtos a serem retirados ou enviados posteriormente."
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

# <a name="hybrid-customer-orders"></a>Ordens de cliente híbrido

[!include[banner](includes/banner.md)]


Um ordem de cliente híbrido é uma única ordem que contém os produtos que podem ser retirados da loja pelo cliente, além produtos a serem retirados ou enviados posteriormente.

No Microsoft Dynamics 365 para Operações - Varejo selecione executar todos os produtos ou executar produtos selecionados para uma ordem de cliente. As linhas do produto que estão marcadas como executadas são faturadas automaticamente depois que a ordem é criada, o mesmo ocorre, para uma ordem que deve ser separada depois que a ordem é criada. O valor devido em ordens híbridas é determinado pela adição da porcentagem de depósito nas linhas de produtos de separação e de remessa com o valor total das linhas da execução. Para ordens híbridas, o sistema alterna entre o modo da ordem de cliente e o modo cash and carry, como segue:

-   Se todos os produtos no carrinho forem definidos como **Realizar entrega**, a ordem será manipulada como uma transação Cash and Carry.
-   Se algumas ou todas as linhas forem definidas como **Separação** ou **entrega**, a ordem será tratada como transação de ordem do Cliente.

Se uma linha do carrinho for selecionada e a opção **Separação selecionada**, **Envio selecionado** ou **Execução selecionada** for selecionada, somente a linha específica do carrinho é definida com esse método de entrega. Nesse caso, o fluxo downstream da operação continua normalmente. Porém, se a opção **Separação selecionada**, **Envio selecionado** ou **Execução selecionada** for escolhida, será aberta uma nova página que listará todas as linhas do carrinho. Nessa tela, você pode selecionar várias linhas imediatamente para definir o método de entrega. Quando você usar esse método para selecionar linhas qualquer método anterior de entrega que for atribuído à linha será substituído.

<a name="see-also"></a>Consulte também
--------

[Visão geral de ordens de cliente](customer-orders-overview.md)



