---
title: Ordens de lote consolidadas
description: Este artigo descreve o conceito das ordens de lotes consolidados.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d6ee4ea9c8af06c493d906887f5ed6f7874e703e
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="consolidated-batch-orders"></a>Ordens de lote consolidadas

[!include[banner](../includes/banner.md)]


Este artigo descreve o conceito das ordens de lotes consolidados.

Um item a granel produzido é considerado um item principal, enquanto um item embalado é considerado um item secundário. A relação entre o item a granel e o item embalado é expressa em uma conversão do item a granel. Essa conversão do item a granel é definida no próprio item a granel.  

Os itens embalados podem ser embalados em contêineres de um único tamanho ou de vários tamanhos considerados como uma unidade. Ao consolidar as ordens para um item a granel, você poderá ver todas as ordens do lote relacionadas em uma única exibição, que pode ajudar a determinar qualquer trabalho restante que tenha de ser concluído.  

Uma ordem de lote consolidada pode conter qualquer combinação das seguintes ordens:

-   Uma única ordem a granel e várias ordens embaladas
-   Várias ordens a granel e várias ordens embaladas
-   Várias ordens a granel e uma única ordem embalada
-   Somente ordens embaladas





