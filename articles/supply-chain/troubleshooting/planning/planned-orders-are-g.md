---
title: O planejamento principal gera pedidos planejados para produtos fantasmas
description: Pedidos planejados são gerados para produtos fantasmas depois que o planejamento principal é executado.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026276"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>O planejamento principal gera pedidos planejados para produtos fantasmas

Número da base de dados de conhecimento: 4614729

## <a name="symptoms"></a>Sintomas

Pedidos planejados são gerados para produtos fantasmas depois que o planejamento principal é executado.

## <a name="resolution"></a>Resolução

A configuração da opção **Fantasma** para produtos liberados determina o tipo de linha padrão na lista de materiais (BOM). Quando a opção **Fantasma** for definida como *Sim*, o sistema ainda criará pedidos planejados para o item, mas a opção **Requisito derivado diretamente** para cada pedido planejado será definida como *Sim*. Portanto, o pedido de produção planejado não pode ser realizado por si só. Em vez disso, ele sempre será incluído automaticamente quando o pedido de produto principal for firmado. Além disso, as linhas da BOM do pedido fantasma planejado serão incluídas na BOM do pedido de produção principal.
