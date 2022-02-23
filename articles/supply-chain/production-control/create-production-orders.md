---
title: Visão geral do ciclo de vida da ordem de produção
description: Ao criar uma ordem de produção, você inicia uma solicitação para iniciar a fabricação de um item. A ordem de produção contém informações sobre o que será produzido, a quantidade a ser produzida e a data de conclusão planejada. Também contém informações sobre quais materiais consumir e qual processo seguir para produzir o item.
author: johanhoffmann
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80031737ab0d0c4ab1e4dbd5646ad91f1a010cd5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422328"
---
# <a name="production-order-lifecycle-overview"></a>Visão geral do ciclo de vida da ordem de produção

[!include [banner](../includes/banner.md)]

Ao criar uma ordem de produção, você inicia uma solicitação para iniciar a fabricação de um item. A ordem de produção contém informações sobre o que será produzido, a quantidade a ser produzida e a data de conclusão planejada. Também contém informações sobre quais materiais consumir e qual processo seguir para produzir o item.

Uma ordem de produção passa pelos estágios do ciclo de vida de produção. Quando uma ordem é criada, ela recebe o status **Criada**. Quando uma ordem é concluída, recebe o status **Encerrada**. Uma configuração de parâmetro em cada estágio permite que um usuário configure cada etapa. A configuração pode ser configurada para um único usuário ou para todos.

A lista de materiais de produção e o roteiro de produção são as principais entidades da ordem de produção. Elas são copiadas para a ordem de produção com base no item selecionado e na quantidade que será produzida. Antes que a ordem de produção seja iniciada, a lista de materiais e o roteiro de produção podem ser editados.

Uma ordem de produção pode ser criada nestes cenários:

-   Criada pela execução do planejamento mestre com base na demanda de materiais.
-   Criada diretamente de uma linha da ordem de venda ou quando uma ordem de produção de nível superior é criada e prevista (fornecimento vinculado).
-   Criada manualmente.




