---
title: Criar uma nova regra kanban duplicando uma regra kanban existente
description: Este procedimento tem como foco a criação de uma duplicata de uma regra kanban existente.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3aef2725152d39e49070f33d0c56089200c94353
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837797"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a>Criar uma nova regra kanban duplicando uma regra kanban existente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento tem como foco a criação de uma duplicata de uma regra kanban existente. Ele é útil se você quiser criar regras kanban com base em regras kanban existentes. A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento destina-se ao engenheiro do processo ou gerente de fluxo de valor, pois eles preparam a produção para uma produção de fluxo ou um produto novo ou modificado.


## <a name="select-a-kanban-rule"></a>Selecionar uma regra kanban
1. Vá para Regras kanban.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione a regra kanban 000017 para produto M0006.  

## <a name="duplicate-a-kanban-rule"></a>Duplicar uma regra kanban
1. Clique em Duplicar regra kanban.
    * Ao duplicar uma regra kanban, é possível alterar tipo, data, atividades e a seleção do produto. Altere o produto para o procedimento na próxima etapa.  
2. No campo Produto, insira ou selecione um valor.
    * Selecione M0007.  
3. Clique em OK.
    * Note que uma duplicata da regra kanban 000017 é criada.    

