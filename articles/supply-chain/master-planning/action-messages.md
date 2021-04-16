---
title: Mensagens de ação
description: Uma mensagem de ação é uma sugestão gerada pelo sistema para alterar uma ordem planejada ou firmada existente.
author: ChristianRytt
ms.date: 10/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea565a8935151235e4c3b103dd86b7131711a4a2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816571"
---
# <a name="action-messages"></a>Mensagens de ação

[!include [banner](../includes/banner.md)]

Uma mensagem de ação é uma sugestão gerada pelo sistema para alterar uma ordem planejada ou firmada existente.

## <a name="introduction"></a>Introdução

As mensagens de ação são geradas pelo cálculo do planejamento mestre em resposta a requisitos modificados. Por exemplo, a data de remessa ou a quantidade podem ter sido alteradas em uma ordem de venda para a qual você já criou uma ordem de compra para atender à demanda. Nesse caso, uma ou vários as mensagens de ação são gerada pelo cálculo do planejamento mestre para atualizar a ordem de compra. Você decide se deseja fazer as alterações propostas.

É possível configurar a forma como as mensagens de ação são calculadas para um grupo de cobertura que é vinculado a um item.

## <a name="select-action-messages"></a>Selecionar mensagens de ação

Na página **Grupos de cobertura**, é possível selecionar as mensagens de ação a serem geradas pelo sistema, e os grupos de cobertura ou os itens aos quais as mensagens se aplicam. É possível selecionar as seguintes mensagens de ação.

| Mensagem             | Descrição                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Adiantar**         | Se você selecionar esta mensagem, o sistema irá gerar mensagens de ação, conforme necessário, para mover as ordens para uma data anterior. No campo **Margem de adiantamento**, também é possível especificar o número máximo de dias entre o recebimento e a saída sem ação antecipada. |
| **Adiar**        | Se você selecionar esta mensagem, o sistema irá gerar mensagens de ação, conforme necessário, para mover as ordens para uma data posterior. No campo **Margem de adiamento**, é possível especificar o número máximo de dias entre o recebimento e a saída sem ação de adiamento.       |
| **Diminuir**        | Se você selecionar esta mensagem, as ordens de produção, ordens de compra, e outras transações de recebimento devem ser reduzidas para evitar níveis de estoque excessivos.                                                                                                   |
| **Aumentar**        | Se você selecionar esta mensagem, as ordens de produção, ordens de compra, e outras transações de recebimento devem ser aumentadas para evitar escassez no estoque.                                                                                                    |
| **Ações derivadas** | Se você selecionar esta mensagem, as mensagens de ação são criadas para os requisitos derivados, por exemplo, ações para as ordens de componente que atendem à produção.                                                                                                   |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]