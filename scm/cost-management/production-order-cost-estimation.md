---
title: "Estimativa de custo da ordem de produção"
description: "Este artigo fornece informações sobre a previsão de custo de produção. A estimativa de custo de produção fornece os custos projetados de consumo de capacidade e de material para produzir um item na quantidade da ordem de produção planejada."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9ae0bbb641d7517d33ad087faec231cb0bda3f78
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="production-order-cost-estimation"></a>Estimativa de custo da ordem de produção

[!include[banner](../includes/banner.md)]


Este artigo fornece informações sobre a previsão de custo de produção. A estimativa de custo de produção fornece os custos projetados de consumo de capacidade e de material para produzir um item na quantidade da ordem de produção planejada. 

Depois de criar uma ordem de produção, você deve estimar o custo de produção. Sua função é estimar o consumo de item e roteiro para o processo de produção, pois essas estimativas formam a base dos processos de produção e planejamento subsequente.

## <a name="production-cost-estimation"></a>Estimativa de custo de produção
As estimativas dos custos de produção são baseadas nas seguintes informações:

-   A quantidade na ordem de produção
-   Os componentes na lista de materiais (BOMs) de produção
-   As operações de roteiro na rota de produção
-   Os custos indiretos que se aplicam aos componentes e operações
-   Os dados de custo ativos como a data de cálculo

Se houver um item de linha fantasma nas BOMs de produção, os cálculos refletirão os componentes do fantasma e as operações de roteiro. Você pode usar a tarefa de estimativa para recalcular os custos estimados para que eles reflitam a informação atualizada. Por exemplo, as informações atualizadas podem ser alterações na quantidade da ordem de produção, os componentes nas BOMs de produção, as operações de roteamento no roteiro de produção, os custos indiretos aplicados a esses componentes e operações ou os dados de custo ativos a partir da data do novo cálculo. Os cálculos do custo estimado também sugerem um preço de venda para o item de produção com base em uma abordagem de custo mais marcação. Os cálculos de custo estimados podem, opcionalmente, ser aplicados para ordens de referência que reflitam ordens de produção que são vinculados a ordem de produção.

## <a name="view-the-estimated-costs"></a>Exiba os custos previstos
Depois de executar a estimativa, você poderá ver os resultados na página **Cálculo de preço**. A estimativa calcula os seguintes valores:

-   **Custo de produção** – O custo de produção é a linha superior da estimativa. Ela mostra o custo completo de executar a ordem de produção e o preço de venda total para a produção. É a soma de todas as linhas de custo na estimativa.
-   **Custos de roteiro ou do recurso** – Os custos de roteiro ou do recurso são os custos das operações de produção. Incluem os custos dos elementos como o tempo de preparação, o tempo de execução, e custos gerais indiretos.
-   **Custos de material** – Custos de material são os custos e os preços dos componentes da lista de materiais (BOM) necessários para produzir o item. Eles foram estabelecidos e inseridos no sistema previamente.

## <a name="other-uses-of-cost-estimation"></a>Outros usos de uma estimativa de custo
Uma estimativa de custo também fornece as seguintes informações:

-   Cotações de preço significativas
-   Estimativas da lucratividade da ordem
-   Estimativas do uso de matéria-prima
-   Comparações das informações de custo de produções anteriores
-   Informações sobre orçamento e previsões
-   Estimativas do tamanho de produção necessário para manter um determinado custo





