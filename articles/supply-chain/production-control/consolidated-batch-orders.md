---
title: Ordens de lote consolidadas
description: Este artigo descreve o conceito das ordens de lotes consolidados.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e15c7def40abdccc7686b0eb34448c951402809
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570312"
---
# <a name="consolidated-batch-orders"></a>Ordens de lote consolidadas

[!include [banner](../includes/banner.md)]

Este artigo descreve o conceito das ordens de lotes consolidados.

Um item a granel produzido é considerado um item principal, enquanto um item embalado é considerado um item secundário. A relação entre o item a granel e o item embalado é expressa em uma conversão do item a granel. Essa conversão do item a granel é definida no próprio item a granel.  

Os itens embalados podem ser embalados em contêineres de um único tamanho ou de vários tamanhos considerados como uma unidade. Ao consolidar as ordens para um item a granel, você poderá ver todas as ordens do lote relacionadas em uma única exibição, que pode ajudar a determinar qualquer trabalho restante que tenha de ser concluído.  

Uma ordem de lote consolidada pode conter qualquer combinação das seguintes ordens:

-   Uma única ordem a granel e várias ordens embaladas
-   Várias ordens a granel e várias ordens embaladas
-   Várias ordens a granel e uma única ordem embalada
-   Somente ordens embaladas






[!INCLUDE[footer-include](../../includes/footer-banner.md)]