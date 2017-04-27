---
title: "Gerenciamento de atualizações de custo padrão"
description: "As atualizações de dados de custo padrão podem ser gerenciadas usando duas abordagens diferentes: a abordagem de uma versão e a abordagem de duas versões."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 7e0f0817ff37c82ed98a51f10bcdde7e785a19a3
ms.lasthandoff: 03/31/2017


---

# <a name="manage-standard-cost-updates"></a>Gerenciamento de atualizações de custo padrão

[!include[banner](../includes/banner.md)]


As atualizações de dados de custo padrão podem ser gerenciadas usando duas abordagens diferentes: a abordagem de uma versão e a abordagem de duas versões. 

A abordagem de uma versão usa uma única versão de avaliação de custo que contém todos os registros de custo. Esses registros incluem os custos originais e todas as atualizações de custo.
A abordagem de duas versões usa uma versão que contém os registros de custos originais e uma segunda versão que contém os registros de todas as atualizações de custo. Uma vantagem principal da abordagem de duas versões é a delineação clara e o rastreamento de atualizações de custo em uma versão de custo separada sem afetar a versão de custo original. A abordagem de duas versões pode ser usada para identificar várias atualizações incrementais, onde cada atualização incremental possui uma versão de custo separada que contém os registros incrementais de custo. **Exemplo** O exemplo a seguir ilustra como as abordagens de uma versão e de duas versões podem ser usadas para atualizar os custos padrão em um ambiente de fabricação. Por exemplo, atualizações que refletem itens novos ou correções de erro. Suponha que uma única versão de avaliação de custo representa os custos padrão para o ano atual. O identificador para esta versão é 2016-STD. A versão 2016-STD contém os custos ativos atuais para todos os itens. Além disso, ela contém todas as categorias de custo relacionadas a roteiro e fórmulas de cálculo dos custos gerais indiretos que eram conhecidas no início do ano de 2016. 2016-STD é a versão de custo original.
-   **Abordagem de uma versão para atualizações de dados de custo** − na abordagem de uma versão, a versão original de avaliação de custo 2016-STD contém todos os registros de custo. As atualizações de custo são registradas em 2016-STD e são definidas como um status "Pendente". Os custos pendentes podem ser inseridos manualmente para novos itens comprados ou podem ser calculados de um item fabricado para refletir correções. Quando a abordagem de uma versão é usada, os cálculos de BOM não exigem uma fonte de dados de fallback porque todos os custos ativos estão contidos na versão de avaliação de custo. Após os custos pendentes se tornarem ativos, a versão original de avaliação de custo 2016-STD conterá novamente todos os custos ativos atuais.
-   **Abordagem de duas versões para as atualizações de dados de custo** − a abordagem de duas versões requer uma versão adicional de avaliação de custo que contenha somente as atualizações de custo. O identificador para esta versão é 2016-STD-CHANGES. As atualizações de custo são registradas em 2016-STD-CHANGES e definidas com um status "Pendente". Com a abordagem de duas versões, os cálculos de BOM de custos pendentes para itens fabricados exigem uma fonte de dados de fallback. Isso ocorre devido à versão adicional de avaliação de custo 2016-STD-CHANGES conter somente um subconjunto de dados de custo. O fallback pode ser expresso como os custos ativos ou como a versão de avaliação de custo 2016-STD, pois ambos identificam a fonte dos dados de custo quando ela não estiver incluída em 2016-STD-CHANGES. Depois que os custos pendentes se tornarem ativos, a versão de avaliação de custo 2016-STD-CHANGES conterá os custos ativos atuais que refletem as atualizações, enquanto a versão de custo original 2016-STD permanecerá intocada. Quando a abordagem de segunda versão for usada, as políticas de bloqueio da versão de avaliação de custo original deverá ser configurada para evitar atualizações. As políticas de bloqueio idênticas devem ser configuradas para a versão adicional de avaliação de custo, exceto para a data de início especificada e o uso seletivo das políticas de bloqueio para permitir atualizações. A data De especificada deve ser atualizada com cada lote de alterações para refletir a data de ativação programada.

Este exemplo usou uma versão de avaliação de custo adicional para gerenciar atualizações durante o ano de 2016. Mais de uma versão de custo adicional pode ser usada, como uma versão separada para cada lote de atualizações. Quando mais de uma avaliação de custo adicional forem usadas, o fallback deve ser expresso como os custos ativos, pois os custos ativos são difundidos em diversas versões de avaliação de custos.






