---
title: Bloqueios da ordem
description: "Este tópico descreve os bloqueios de ordens usando o recurso Varejo e comércio do Dynamics AX."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: 82a0354901a665480b8854ce2527e35490ac5562
ms.contentlocale: pt-br
ms.lasthandoff: 04/26/2017


---

# <a name="order-holds"></a>Bloqueios da ordem

[!include[banner](includes/banner.md)]


Este tópico descreve os bloqueios de ordens usando o recurso Varejo e comércio do Dynamics AX.

Uma ordem pode ser colocada em espera por vários motivos. Por exemplo, você pode colocar uma ordem em espera até que o endereço do cliente ou o método de pagamento seja verificado ou até que um gerente possa revisar o limite de crédito do cliente. Durante o processo de vendas, há momentos em que as ordens de venda devem ser colocadas em espera. Por exemplo, uma ordem de venda pode ser colocada em espera devido a problemas com o pagamento do cliente, por suspeita de fraude ou porque um gerente deve analisar a ordem. Quando uma ordem de venda é colocada em espera, um código de bloqueio da ordem é atribuído à ordem de venda para indicar o motivo do bloqueio. Os códigos de bloqueio da ordem de venda são configurados em **Vendas e marketing** &gt; **Configuração** &gt; **Ordens de venda** &gt; **Códigos de bloqueio de ordem**. Uma ordem de venda pode ser colocada em espera manualmente no momento da criação da ordem ou posteriormente. Além disso, uma ordem pode ser colocada em espera automaticamente, com base nas regras de fraude. Enquanto uma ordem de venda estiver em espera, você possivelmente precisará atualizá-la com mais informações. Se desejar, você poderá fazer o check-out da ordem de venda enquanto trabalha nela. Você pode fazer o check-out de uma ordem de venda, fazer o check-in novamente e até mesmo substituir o check-out de outro usuário usando a bancada de bloqueio da ordem (**Comércio e varejo** &gt; **Clientes** &gt; **Bloqueios de ordem**). Quando uma ordem estiver pronta para ser concluída, você deverá remover o bloqueio antes de poder concluir o processo da ordem.




