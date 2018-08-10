---
title: Manter ordens planejadas
description: "Este artigo oferece informações sobre como gerenciar ordens planejadas. Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3d7afda9371b4d21e58f2e56de3d477b1c9950a1
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="maintain-planned-orders"></a>Manter ordens planejadas

[!include [banner](../includes/banner.md)]

Este artigo oferece informações sobre como gerenciar ordens planejadas. Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada.

Você pode gerenciar ordens planejados no espaço de trabalho **Planejamento mestre**, na lista **Ordem planejada** ou nas listas **Ordens de produção planejadas**, **Ordens de compra planejadas** e **Transferência planejada**. Você pode usar o campo **Status** para ajudar a acompanhar seu progresso. Os seguintes valores são usados:

-   Quando o planejamento mestre gerar ordens planejadas, elas terão o status **Não processado**.
-   Se você optar por não confirmar uma ordem planejada, poderá atribuir a ela o status **Concluído**.
-   Quando você optar por confirmar uma ordem planejada, atribuirá a ela o status **Aprovado**. Esse status indica que você aprova a confirmação da ordem planejada, mas que ela ainda não foi confirmada.

**Observação:** uma ordem planejada aprovada é transferida, no estado atual, para o próximo cálculo do planejamento mestre. É possível confirmar uma ordem planejada clicando em **Confirmar**. As seguintes ordens planejadas podem ser confirmadas:

-   A ordem planejada selecionada.
-   Várias ordens planejadas.
-   Ordens planejadas geradas por um detalhamento da página **Detalhamento**. Clique em **Ordens planejadas**, selecione a ordem planejada e clique em **Confirmar**.

Ao ser confirmada, uma ordem planejada é movida para a seção de ordens do módulo relevante. **Observação:** você pode clicar com o botão direito do mouse em uma ordem planejada que tenha um determinado status e filtrar outras ordens planejadas com o mesmo status. Essa funcionalidade será útil se, por exemplo, você quiser filtrar todas as ordens planejadas cujo status seja **Aprovado**, para que possa então confirmá-las.

<a name="additional-resources"></a>Recursos adicionais
--------

[Planos mestres](master-plans.md)




