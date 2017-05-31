---
title: Reservar o mesmo lote para uma ordem de venda
description: "Este artigo explica como configurar um produto para permitir a reserva de estoque em relação a um único lote de estoque."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1b63173d1efe45bf048b9c2eed4dc6250c9ee9f1
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="reserve-the-same-batch-for-a-sales-order"></a>Reservar o mesmo lote para uma ordem de venda

[!include[banner](../includes/banner.md)]


Este artigo explica como configurar um produto para permitir a reserva de estoque em relação a um único lote de estoque.

A reserva de mesmo lote permite reservar estoque para uma linha de ordem de venda para um único lote de estoque. Por exemplo, um cliente que encomende papel de parede pode solicitar que a ordem inteira seja atendida pelo mesmo lote a fim de evitar diferenças entre os rolos. Para configurar um produto para usar a mesma reserva de lote, as configurações a seguir devem estar ativas no grupo de modelos de item, no grupo de dimensões de rastreamento e no grupo de dimensões de armazenamento atribuídos ao produto:

-   **Grupos de modelos de itens** – o grupo de modelos de itens deve ter os campos **Seleção de mesmo lote** e **Consolidar necessidade** selecionados no grupo de campos **Reserva** para políticas de estoque.
-   **Grupos de dimensões de rastreamento** – o grupo de dimensões de rastreamento deve ter o campo **Plano de cobertura por dimensão** selecionado para o número do lote.
-   **Grupos de dimensões de armazenamento** – o grupo de dimensões de armazenamento deve ter o campo **Plano de cobertura por dimensão** selecionado para **Local** e **Depósito**.

Ao reservar estoque para um produto em uma linha da ordem de venda configurada para a seleção de mesmo lote, o Microsoft Dynamics 365 for Operations tenta reservar a quantidade encomendada de um único lote de estoque. Qualquer requisito específico do atributo de lote também será considerado. Se a quantidade não puder ser preenchida de um único lote, a página **Conflito de reserva de mesmo lote** será exibida. Essa página descreve os problemas e também as ações que você pode executar para proceder com a reserva. As seguintes condições podem impedir que o lote seja reservado:

-   O código de disposição do lote tem **Bloquear reserva** da venda sinalizado como **Bloqueado**.
-   O lote expirou com base na data de vencimento e nos dias comercializáveis aplicáveis do cliente. O item ainda poderá ser considerado para reserva se o grupo de modelos de item for controlado pela data FEFO (primeiro a vencer, primeiro a sair) e se a data de validade for selecionada como critério de separação.
-   O lote não tem dias restantes de validade suficientes com base na data de vencimento e na data de validade, mais os dias comercializáveis do cliente.





