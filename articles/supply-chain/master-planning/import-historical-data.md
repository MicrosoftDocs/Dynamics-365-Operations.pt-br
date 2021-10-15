---
title: Importar dados históricos para previsões de demanda
description: Para obter previsões de demanda precisas, você precisará dos dados históricos de demanda por item ou por chave de alocação de item. Este tópico explica como usar entidades de dados para importar dados históricos de demanda de qualquer sistema, de forma que você tenha um histórico de dados de previsão de demanda mais amplo.
author: ChristianRytt
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6dba31279541c20949dd1e86236103045c48b701
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579655"
---
# <a name="import-historical-data-for-demand-forecasts"></a>Importar dados históricos para previsões de demanda

[!include [banner](../includes/banner.md)]

Para ajudar a garantir a precisão das previsões de demanda, será necessário ter todos os dados históricos de demanda possíveis que possam ser obtidos por item ou por chave de alocação de item. Se os dados históricos de demanda ainda não tiverem sido importados, use a entidade de dados **Demanda externa histórica** (ReqDemPlanHistoricalExternalDemandEntity) no Dynamics 365 Supply Chain Management para importá-la.

No espaço de trabalho **Gerenciamento de dados**, você pode ter uma visão geral de todos os campos na entidade.

1. Abra o espaço de trabalho **Gerenciamento de dados**.
2. Selecione o bloco **Entidades de dados**.
3. Pesquise a lista de entidades para **Demanda histórica externa**.
4. Selecione **Campos de destino**. Os seguintes campos de entidade são obrigatórios: site (**DeliveringSiteId**), data (**DemandDate**), quantidade (**DemandQuantity**) e número de item (**ItemNumber**) ou chave de alocação de item (**ProductAllocationKeyId**).

Para usar a entidade de dados, você deverá ter um arquivo do Microsoft Excel ou um arquivo de valores separados por vírgulas (CSV) que contenha os dados históricos de demanda. O exemplo a seguir mostra como importar os dados de um arquivo CSV.

Para obter mais informações sobre como importar dados, incluindo como limpar dados após uma importação, consulte [Visão geral sobre trabalhos de importação de dados e exportação](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) e os tópicos relacionados.

Veja também [Gerar uma previsão estatística](generate-statistical-baseline-forecast.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]