---
title: Ordens de lote consolidadas
description: Este artigo descreve o conceito das ordens de lotes consolidados.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: faeb90aa3366a58b746c0b397dd950bfb8c9024f
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979466"
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




