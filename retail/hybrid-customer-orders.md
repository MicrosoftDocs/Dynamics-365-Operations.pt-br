---
title: "Ordens de cliente híbrido"
description: "Um ordem de cliente híbrido é uma única ordem que contém os produtos que podem ser retirados da loja pelo cliente, além produtos a serem retirados ou enviados posteriormente."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 52a16be4b07eafb493c7fd7ad52a6d9d1bb9ee89
ms.openlocfilehash: e748c6fb788f4ec00ab2a0ef62e139a6180089be
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017

---

# <a name="hybrid-customer-orders"></a>Ordens de cliente híbrido

[!include[banner](includes/banner.md)]


Um ordem de cliente híbrido é uma única ordem que contém os produtos que podem ser retirados da loja pelo cliente, além produtos a serem retirados ou enviados posteriormente.

No Microsoft Dynamics 365 for Retail, selecione executar todos os produtos ou executar produtos selecionados para uma ordem do cliente. As linhas do produto que estão marcadas como executadas são faturadas automaticamente depois que a ordem é criada, o mesmo ocorre, para uma ordem que deve ser separada depois que a ordem é criada. O valor devido em ordens híbridas é determinado pela adição da porcentagem de depósito nas linhas de produtos de separação e de remessa com o valor total das linhas da execução. Para ordens híbridas, o sistema alterna entre o modo da ordem de cliente e o modo cash and carry, como segue:

-   Se todos os produtos no carrinho forem definidos como **Realizar entrega**, a ordem será manipulada como uma transação Cash and Carry.
-   Se algumas ou todas as linhas forem definidas como **Separação** ou **entrega**, a ordem será tratada como transação de ordem do Cliente.

Se uma linha do carrinho for selecionada e a opção **Separação selecionada**, **Envio selecionado** ou **Execução selecionada** for selecionada, somente a linha específica do carrinho é definida com esse método de entrega. Nesse caso, o fluxo downstream da operação continua normalmente. Porém, se a opção **Separação selecionada**, **Envio selecionado** ou **Execução selecionada** for escolhida, será aberta uma nova página que listará todas as linhas do carrinho. Nessa tela, você pode selecionar várias linhas imediatamente para definir o método de entrega. Quando você usar esse método para selecionar linhas qualquer método anterior de entrega que for atribuído à linha será substituído.

<a name="see-also"></a>Consulte também
--------

[Visão geral de ordens de cliente](customer-orders-overview.md)




