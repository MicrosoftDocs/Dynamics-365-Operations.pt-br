---
title: Mensagens de ação
description: Uma mensagem de ação é uma sugestão gerada pelo sistema para alterar uma ordem planejada ou firmada existente.
author: t-benebo
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
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2acba2ba12f933c085de15eadbf4d433944c2cf3
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469440"
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