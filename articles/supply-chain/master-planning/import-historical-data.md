---
title: Importar dados históricos para previsões de demanda
description: Para obter previsões de demanda precisas, você precisará dos dados históricos de demanda por item ou por chave de alocação de item. Este tópico explica como usar entidades de dados para importar dados históricos de demanda de qualquer sistema, de forma que você tenha um histórico de dados de previsão de demanda mais amplo.
author: roxanadiaconu
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
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b04ee246d4c28e934407ccb92d792692cc4347d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301641"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="0fa22-104">Importar dados históricos para previsões de demanda</span><span class="sxs-lookup"><span data-stu-id="0fa22-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0fa22-105">Para ajudar a garantir a precisão das previsões de demanda, será necessário ter todos os dados históricos de demanda possíveis que possam ser obtidos por item ou por chave de alocação de item.</span><span class="sxs-lookup"><span data-stu-id="0fa22-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="0fa22-106">Se os dados históricos de demanda ainda não tiverem sido importados, use a entidade de dados **Demanda externa histórica** (ReqDemPlanHistoricalExternalDemandEntity) no Dynamics 365 Supply Chain Management para importá-la.</span><span class="sxs-lookup"><span data-stu-id="0fa22-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="0fa22-107">No espaço de trabalho **Gerenciamento de dados**, você pode ter uma visão geral de todos os campos na entidade.</span><span class="sxs-lookup"><span data-stu-id="0fa22-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="0fa22-108">Abra o espaço de trabalho **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="0fa22-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="0fa22-109">Selecione o bloco **Entidades de dados**.</span><span class="sxs-lookup"><span data-stu-id="0fa22-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="0fa22-110">Pesquise a lista de entidades para **Demanda histórica externa**.</span><span class="sxs-lookup"><span data-stu-id="0fa22-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="0fa22-111">Selecione **Campos de destino**.</span><span class="sxs-lookup"><span data-stu-id="0fa22-111">Select **Target fields**.</span></span> <span data-ttu-id="0fa22-112">Os seguintes campos de entidade são obrigatórios: site (**DeliveringSiteId**), data (**DemandDate**), quantidade (**DemandQuantity**) e número de item (**ItemNumber**) ou chave de alocação de item (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="0fa22-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="0fa22-113">Para usar a entidade de dados, você deverá ter um arquivo do Microsoft Excel ou um arquivo de valores separados por vírgulas (CSV) que contenha os dados históricos de demanda.</span><span class="sxs-lookup"><span data-stu-id="0fa22-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="0fa22-114">O exemplo a seguir mostra como importar os dados de um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="0fa22-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="0fa22-115">Para obter mais informações sobre como importar dados, incluindo como limpar dados após uma importação, consulte [Visão geral sobre trabalhos de importação de dados e exportação](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) e os tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="0fa22-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

<span data-ttu-id="0fa22-116">Veja também [Gerar uma previsão estatística](generate-statistical-baseline-forecast.md).</span><span class="sxs-lookup"><span data-stu-id="0fa22-116">See also [Generate a statistical baseline forecast](generate-statistical-baseline-forecast.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]