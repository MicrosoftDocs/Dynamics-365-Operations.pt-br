---
title: Visão geral do ciclo de vida da ordem de produção
description: Ao criar uma ordem de produção, você inicia uma solicitação para iniciar a fabricação de um item. A ordem de produção contém informações sobre o que será produzido, a quantidade a ser produzida e a data de conclusão planejada. Também contém informações sobre quais materiais consumir e qual processo seguir para produzir o item.
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19741"
- intro-internal
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f0e3d15cbb522dd4a9322a8bac64e1a14e8432d3aff6722907a7f14fa3fefb2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773216"
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






[!INCLUDE[footer-include](../../includes/footer-banner.md)]