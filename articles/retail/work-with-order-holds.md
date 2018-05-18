---
title: Bloqueios da ordem
description: "Este tópico descreve os bloqueios de ordens usando o Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8b4c8ecbef1dc667d3b60411a53f0c63686529c2
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="order-holds"></a>Bloqueios da ordem

[!include [banner](includes/banner.md)]

Este tópico descreve os bloqueios de ordens usando o Dynamics 365 for Retail.

Uma ordem pode ser colocada em espera por vários motivos. Por exemplo, você pode colocar uma ordem em espera até que o endereço do cliente ou o método de pagamento seja verificado ou até que um gerente possa revisar o limite de crédito do cliente. Durante o processo de vendas, há momentos em que as ordens de venda devem ser colocadas em espera. Por exemplo, uma ordem de venda pode ser colocada em espera devido a problemas com o pagamento do cliente, por suspeita de fraude ou porque um gerente deve analisar a ordem. Quando uma ordem de venda é colocada em espera, um código de bloqueio da ordem é atribuído à ordem de venda para indicar o motivo do bloqueio. Os códigos de bloqueio da ordem de venda são configurados em **Vendas e marketing** &gt; **Configuração** &gt; **Ordens de venda** &gt; **Códigos de bloqueio de ordem**. Uma ordem de venda pode ser colocada em espera manualmente no momento da criação da ordem ou posteriormente. Além disso, uma ordem pode ser colocada em espera automaticamente, com base nas regras de fraude. Enquanto uma ordem de venda estiver em espera, você possivelmente precisará atualizá-la com mais informações. Se desejar, você poderá fazer o check-out da ordem de venda enquanto trabalha nela. Você pode fazer o check-out de uma ordem de venda, fazer o check-in novamente e até mesmo substituir o check-out de outro usuário usando a bancada de bloqueio da ordem (**Varejo** &gt; **Clientes** &gt; **Bloqueios de ordem**). Quando uma ordem estiver pronta para ser concluída, você deverá remover o bloqueio antes de poder concluir o processo da ordem.




