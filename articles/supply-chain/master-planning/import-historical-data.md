---
title: Importar dados históricos para previsões de demanda
description: Para obter previsões de demanda precisas, você precisará dos dados históricos de demanda por item ou por chave de alocação de item. Este tópico explica como usar entidades de dados para importar dados históricos de demanda de qualquer sistema, de forma que você tenha um histórico de dados de previsão de demanda mais amplo.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6ba2e1a3a884d29bff491f914aa2d5f9ece2b84
ms.sourcegitcommit: 79621e667cd7f48ba3bdbf2731f6f33d8e9f57f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "5154218"
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

## <a name="example"></a>Exemplo

Você pode usar o arquivo a seguir como um exemplo. Baixe [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/). Este arquivo contém os dados históricos de demanda do item D0001. Ele contém apenas os seguintes campos obrigatórios: site, quantidade e a data de demanda.

1. Selecione a empresa para a qual serão importados os dados históricos de demanda.
2. Abra o espaço de trabalho **Gerenciamento de dados**.
3. Selecione o bloco **Importação**.
4. Insira um nome para o projeto de importação, como **Importar a demanda histórica do item D0001**.
5. No campo **Formato de dados de origem**, selecione o formato do arquivo que você está importando. Para importar o arquivo HistoricalDemandData para este exemplo, selecione **CSV**.
6. No campo **Nome da entidade**, selecione **Demanda histórica externa**.
7. Salve o arquivo no computador e depois carregue-o.
8. Selecione **Importar**.
9. A página **Resumo da execução** é aberta automaticamente. Verifique os dados importados na página.

Depois de importar os dados históricos de demanda, você poderá gerar uma previsão de demanda.

## <a name="additional-resources"></a>Recursos adicionais

[​Gerar uma previsão estatística​](generate-statistical-baseline-forecast.md)  
[Visão geral de trabalhos de importação e exportação de dados](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]