---
title: Página inicial de gerenciamento de custos
description: O gerenciamento de custos permite que você lide com a avaliação e a contabilidade de materiais não processados, bens não concluídos, bens concluídos e ativos em progresso.
author: AndersGirke
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd94ae4c5ea855139fd1c41060de7db455ffab06
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557630"
---
# <a name="cost-management-home-page"></a>Página inicial de gerenciamento de custos

[!include [banner](../includes/banner.md)]

[Gerenciamento de custos (vídeo)](https://www.youtube.com/watch?v=vXzlC-mOBcg&feature=youtu.be) permite que você trabalhe com a avaliação e a contabilidade de materiais não processados, bens não concluídos, bens concluídos e ativos em progresso. É o processo de definir, gerenciar e relatar [Contabilidade de estoque](cost-object.md) e [Contabilidade de fabricação](bom-calculations.md).

Você pode definir políticas de custo estimado nas seguintes áreas: 
-  [Custo predeterminado](costing-versions.md)
-  [Contabilidade de estoque](cost-object.md)
-  [Contabilidade de fabricação](bom-calculations.md)
-  [Contabilidade de custo indireto](costing-sheets.md)
-  [Integração com o razão](production-order-cost-analysis.md)

Por exemplo, você pode definir quais métodos de avaliação de estoque, como [PEPS](fifo-physical-value-marking.md), [Média ponderada](weighted-average-physical-value-marking.md), [Custo padrão](prerequisites-standard-costs.md) ou [Média de movimentos](moving-average.md) que deseja aplicar aos produtos no [Grupo de modelo do item](../inventory/reserve-inventory-quantities.md) em Contabilidade de estoque.

Você pode acessar a Contabilidade de estoque e a Contabilidade de fabricação dos espaços de trabalho **Administração de custo** e **Análise de custo**. Esses espaços de trabalho fornecem uma visão geral abrangente do status atual, indicadores de desempenho-chave (KPIs) e detecção de desvio. 

A Contabilidade de fabricação permite que você lide com [Custos de ordem de produção](production-order-cost-analysis.md) em ordens de produção e de lote, assim como [Custos de fluxo inverso](backflush-costing.md) em lean manufacturing.

O conteúdo de [Gerenciamento de custos do Power BI](../../dev-itpro/analytics/cost-management-content-pack.md) mostra uma visão administrativa sobre o estoque e o estoque WIP (trabalho em andamento) e como é o fluxo de custos por categoria ao longo do tempo. As informações também podem ser usadas como um suplemento detalhado para o demonstrativo financeiro.

### <a name="additional-resources"></a>Recursos adicionais

#### <a name="whats-new-and-in-development"></a>Novidades e o que está em desenvolvimento

Visite o [Roteiro do Microsoft Dynamics 365](https://roadmap.dynamics.com/) para conferir os novos recursos que foram lançados e os novos recursos em desenvolvimento. 

#### <a name="white-paper"></a>White paper
[Cálculo de BOM usando uma folha de custos](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/white-papers/365operationsbomcalsheet) descreve como definir uma folha de contabilidade que inclua material e fabricação, e como a configuração afeta os resultados de cálculo do BOM. Para explicar de uma melhor forma os tópicos, ele fornece cenários concretos e dados que demonstram o efeito de várias definições e configurações. Nós não esperamos que você siga todos esses cenários, porque este documento não fornece detalhes o suficiente para configurá-los. No entanto, se você tiver o conhecimento básico, poderá tentar executar as guias de tarefa listadas abaixo na ordem em que elas aparecem. Use o conhecimento obtido com a leitura desse documento para realizar a análise de cálculo de bom. 

-  [Criar um produto finalizado](tasks/create-finished-product-2016-02.md)
-  [Criar um produto semifinalizado](tasks/create-semi-finished-product-2016-02.md)
-  [Criar matérias-primas](tasks/create-raw-materials-2016-02.md)
-  [Criar BOMs](tasks/create-boms-2016-02.md)
-  [Criar roteiros](tasks/create-routes-2016-02.md)
-  [Calcular um BOM usando uma estrutura de nível único](tasks/calculate-bom-single-level-structure-2016-02.md)
-  [Calcular um BOM usando uma estrutura de vários níveis](tasks/calculate-bom-multilevel-structure-2016-02.md)


#### <a name="blogs"></a>Blogs
Você encontra opiniões, notícias e outras informações sobre gerenciamento de custos no [blog da equipe de P&D de Manufacturing do Dynamics AX](https://blogs.msdn.microsoft.com/axmfg) e no [blog da equipe de P&D de Supply Chain Management do Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm). Embora algumas dessas postagens tenham sido escritas para a versão anterior de Gerenciamento de custo, os mesmos conceitos ainda se aplicam, e os procedimentos também são semelhantes na versão atual.

#### <a name="task-guides"></a>Guias de tarefas
Há ajuda adicional disponível como guias de tarefas dentro do Finance and Operations. Para acessar os guias de tarefas, clique no botão Ajuda em qualquer página.

