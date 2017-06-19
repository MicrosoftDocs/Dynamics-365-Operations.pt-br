---
title: "Importar dados históricos para previsões de demanda"
description: "Para obter previsões de demanda precisas, você precisará dos dados históricos de demanda por item ou por chave de alocação de item. Este tópico explica como usar entidades de dados para importar dados históricos de demanda de qualquer sistema, de forma que você tenha um histórico de dados de previsão de demanda mais amplo."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0d1e2b9a51c2d7a7c30c2458b7babf8ac5c08118
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="import-historical-data-for-demand-forecasts"></a>Importar dados históricos para previsões de demanda

[!include[banner](../includes/banner.md)]

Para ajudar a garantir a precisão das previsões de demanda, será necessário ter todos os dados históricos de demanda possíveis que possam ser obtidos por item ou por chave de alocação de item. Se os dados históricos de demanda ainda não tiverem sido importados, use **Demanda histórica externa** (ReqDemPlanHistoricalExternalDemandEntity) no Microsoft Dynamics 365 for Operations para importá-los.

No espaço de trabalho **Gerenciamento de dados**, você pode ter uma visão geral de todos os campos na entidade.

1. Abra o espaço de trabalho **Gerenciamento de dados**.
2. Clique no bloco **Entidades de dados**.
3. Pesquise a lista de entidades para **Demanda histórica externa**.
4. Clique em **Campos de destino**. Os seguintes campos de entidade são obrigatórios: site (**DeliveringSiteId**), data (**DemandDate**), quantidade (**DemandQuantity**) e número de item (**ItemNumber**) ou chave de alocação de item (**ProductAllocationKeyId**).

Para usar a entidade de dados, você deverá ter um arquivo do Microsoft Excel ou um arquivo de valores separados por vírgulas (CSV) que contenha os dados históricos de demanda. O exemplo a seguir mostra como importar os dados de um arquivo CSV.

## <a name="example"></a>Exemplo

Você pode usar o arquivo a seguir como um exemplo. Baixe [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast). Este arquivo contém os dados históricos de demanda do item D0001. Ele contém apenas os seguintes campos obrigatórios: site, quantidade e a data de demanda.

1. Selecione a empresa para a qual serão importados os dados históricos de demanda.
2. Abra o espaço de trabalho **Gerenciamento de dados**.
3. Clique no bloco **Importar**.
4. Insira um nome para o projeto de importação, como **Importar a demanda histórica do item D0001**.
5. No campo **Formato de dados de origem**, selecione o formato do arquivo que você está importando. Para importar o arquivo HistoricalDemandData para este exemplo, selecione **CSV**.
6. No campo **Nome da entidade**, selecione **Demanda histórica externa**.
7. Salve o arquivo no computador e depois carregue-o.
8. Clique em **Importar**.
9. A página **Resumo da execução** é aberta automaticamente. Verifique os dados importados na página.

Depois de importar os dados históricos de demanda, você poderá gerar uma previsão de demanda.

## <a name="see-also"></a>Consulte também

[Gerar uma previsão estatística de linha de base](generate-statistical-baseline-forecast.md)
