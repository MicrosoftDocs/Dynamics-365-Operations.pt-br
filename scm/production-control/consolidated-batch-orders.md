---
title: Ordens de lote consolidadas
description: Este artigo descreve o conceito das ordens de lotes consolidados.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 3359f1cd5c3f1ecf25c3f28a366c022826cf895e
ms.lasthandoff: 03/31/2017


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





