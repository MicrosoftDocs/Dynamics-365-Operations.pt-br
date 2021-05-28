---
title: Os pedidos firmados derivados diretamente são processados por um fluxo de trabalho em análise
description: Os pedidos firmados derivados diretamente são processados por um fluxo de trabalho que tem o status Em análise.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d54985707d82df2b947a7cb615fc25f90aa31702
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026277"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a>Os pedidos firmados derivados diretamente são processados por um fluxo de trabalho em análise

Número da base de dados de conhecimento: 4612450

## <a name="symptoms"></a>Sintomas

Os pedidos firmados derivados diretamente são processados por um fluxo de trabalho que tem o status *Em análise*.

## <a name="resolution"></a>Resolução

Quando o Controle de Alterações está habilitado, o status de *Em análise* é atribuído aos pedidos derivados firmados (pedidos de compra do subcontrato). Portanto, se um pedido de compra for derivado (um pedido de compras do subcontrato), ele é enviado somente a um fluxo de trabalho. Se um pedido de compra for um pedido de compra planejado firmado, ele é automaticamente aprovado para garantir que o mecanismo de planejamento não crie novos pedidos planejados enquanto o pedido de compra ainda estiver no status *Rascunho*.
