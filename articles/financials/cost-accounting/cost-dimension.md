---
title: "Criar dimensões e importar membros da dimensão"
description: "A contabilização de custos é um módulo independente que requer dados mestre de outros módulos."
author: YuyuScheller
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0fb276e7d62e2f7c02934e74741c8cf74778fc12
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="create-dimensions-and-import-dimension-members"></a>Criar dimensões e importar membros da dimensão

[!include[banner](../includes/banner.md)]

A contabilização de custos é um módulo independente que requer dados de outros módulos. Esses dados são classificados como segue:

-  Elementos de custo
-  Objetos de custo
-  Dimensões estatísticas

Um **Elemento de custo** corresponde a um item relevante a custo no plano de contas. Um **Objeto de custo** corresponde a qualquer tipo de dimensão financeira, como produtos, centros de custos e projetos que você deseja estimar, alocar custos ou medir diretamente. Uma **Dimensão estatística** e seus membros são usados para registrar entradas não monetárias. Os membros da dimensão estatística podem ser utilizados como base de alocação na distribuição e alocação de custos 

O diagrama a seguir ilustra as dimensões usadas na Contabilização de custos.

[![Dimensões na contabilização de custos](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

Depois que dados são importados para a Contabilização de custo, você pode usá-los para construir as várias perspectivas que fornecem ideias a gerentes em todos os níveis da organização. Os seguintes tópicos fornecem informações sobre a criação de dimensões e a importação de membros da dimensão. 

-  [Dimensões do elemento de custo](cost-elements.md)
-  [Criar elementos de custo (Guia de tarefas)](./tasks/create-cost-elements.md)
-  [Dimensões de objeto de custo](cost-objects.md)
-  [Criar elementos de custo (Guia de tarefas)](./tasks/create-cost-objects.md)
-  [Mapear membros de dimensão de elemento de custo para um conjunto comum de membros de dimensão](map-cost-elements-dimension-members.md)
-  [Mapear uma dimensão de elemento de custo (Guia de tarefas)](./tasks/map-cost-element-dimension.md)
-  [Membros estatísticos de dimensões e modelos de fornecedores de medições estatísticas](statistical-measure-provider-template.md)







