---
title: "Dimensões de objeto de custo"
description: "Quando você a analisar custos, dimensões de usar elementos de custo estimado para determinar onde os custos a interno. Use dimensões de objeto de custo para determinar onde atribua custos. Este tópico fornece informações sobre dimensões de objeto de custo."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5c121300877c5835bfe023c11040310dcddff052
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="cost-object-dimensions"></a>Dimensões de objeto de custo

[!include[banner](../includes/banner.md)]


Quando você a analisar custos, dimensões de usar elementos de custo estimado para determinar onde os custos a interno. Use dimensões de objeto de custo para determinar onde atribua custos. Este tópico fornece informações sobre dimensões de objeto de custo.

Um objeto de custo previsto pode ser qualquer tipo de objeto ao qual você deseja prever, alocar custos, ou os para medir diretamente. Os objetos de custo previsto típicos incluem produto, recursos, projetos, departamentos, centros de custo, e regiões em. O gerenciamento usa objetos de custo para quantificar custos e realizar análises de lucratividade.

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>Dimensões de elemento de custo previsto e membros da dimensão do elemento de custo previsto
Os objetos de custo previsto são conhecidos como *dimensões de custo previsto do objeto*. Após decidir qual entidade a dimensão de custo previsto de objeto deve consulte, especifique os valores de dimensão ou importá-los individualmente na contabilização de custo previsto de outros sistemas de origem. Os valores de dimensão específicos são chamados de *membros da dimensão do elemento de custo previsto*. Por exemplo, desejar usar a dimensão financeira que é chamada centro de custo como a dimensão de custo previsto do objeto. Para ver como os custos para os centros de custo individuais, você deve importar os membros de custo previsto de dimensão de objeto. Nesse caso, os membros de custo previsto de dimensão de objetos são centros de custo real, como venda, produção, administração e localizações, em. A captura de tela a seguir mostra um exemplo de centros de custo como dimensão de objeto de custo com seus centros de custo real como membros de dimensão de objeto de custo. 

[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>Membros de custo previsto de dimensão de objeto de importação em dos conectores de dados
Para fazer a importação de objeto de custo previsto dimensionar membros mais disso, use conectores de dados para recuperar os valores das entidades que deseja usar como dimensões de custo previsto do objeto. Você pode usar os conectores compilados anteriormente dados ou dos conectores personalizados de dados que você cria.




