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
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1cb18e3275b8dcdf0a61531ee056995f6e8fbc8d
ms.lasthandoff: 03/31/2017


---

# <a name="order-holds"></a>Bloqueios da ordem

Este tópico descreve os bloqueios de ordens usando o recurso Varejo e comércio do Dynamics AX.

Uma ordem pode ser colocada em espera por vários motivos. Por exemplo, você pode colocar uma ordem em espera até que o endereço do cliente ou o método de pagamento seja verificado ou até que um gerente possa revisar o limite de crédito do cliente. Durante o processo de vendas, há momentos em que as ordens de venda devem ser colocadas em espera. Por exemplo, uma ordem de venda pode ser colocada em espera devido a problemas com o pagamento do cliente, por suspeita de fraude ou porque um gerente deve analisar a ordem. Quando uma ordem de venda é colocada em espera, um código de bloqueio da ordem é atribuído à ordem de venda para indicar o motivo do bloqueio. Os códigos de bloqueio da ordem de venda são configurados ** vendas e marketing ** &gt; ** em de instalação ** &gt; ** ordens de venda ** &gt; ** ordem retém ** códigos. Uma ordem de venda pode ser colocada em espera manualmente no momento da criação da ordem ou posteriormente. Além disso, uma ordem pode ser colocada em espera automaticamente, com base nas regras de fraude. Enquanto uma ordem de venda estiver em espera, você possivelmente precisará atualizá-la com mais informações. Se desejar, você poderá fazer o check-out da ordem de venda enquanto trabalha nela. Você pode fazer o check-out de um ordem de venda, verifique voltar em, e substituí-lo mesmo o check-out de outro usuário com a bancada de bloqueio da ordem (** varejo e comércio ** &gt; ** clientes ** &gt; ** bloqueios de ordem **). Quando uma ordem estiver pronta para ser concluída, você deverá remover o bloqueio antes de poder concluir o processo da ordem.


