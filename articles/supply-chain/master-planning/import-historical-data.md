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
ms.openlocfilehash: de380113fe951f75c15f9e5526ad2f1f5cc84334
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908871"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="0465a-104">Importar dados históricos para previsões de demanda</span><span class="sxs-lookup"><span data-stu-id="0465a-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0465a-105">Para ajudar a garantir a precisão das previsões de demanda, será necessário ter todos os dados históricos de demanda possíveis que possam ser obtidos por item ou por chave de alocação de item.</span><span class="sxs-lookup"><span data-stu-id="0465a-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="0465a-106">Se os dados históricos de demanda ainda não tiverem sido importados, use a entidade de dados **Demanda externa histórica** (ReqDemPlanHistoricalExternalDemandEntity) no Dynamics 365 Supply Chain Management para importá-la.</span><span class="sxs-lookup"><span data-stu-id="0465a-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="0465a-107">No espaço de trabalho **Gerenciamento de dados**, você pode ter uma visão geral de todos os campos na entidade.</span><span class="sxs-lookup"><span data-stu-id="0465a-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="0465a-108">Abra o espaço de trabalho **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="0465a-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="0465a-109">Selecione o bloco **Entidades de dados**.</span><span class="sxs-lookup"><span data-stu-id="0465a-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="0465a-110">Pesquise a lista de entidades para **Demanda histórica externa**.</span><span class="sxs-lookup"><span data-stu-id="0465a-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="0465a-111">Selecione **Campos de destino**.</span><span class="sxs-lookup"><span data-stu-id="0465a-111">Select **Target fields**.</span></span> <span data-ttu-id="0465a-112">Os seguintes campos de entidade são obrigatórios: site (**DeliveringSiteId**), data (**DemandDate**), quantidade (**DemandQuantity**) e número de item (**ItemNumber**) ou chave de alocação de item (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="0465a-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="0465a-113">Para usar a entidade de dados, você deverá ter um arquivo do Microsoft Excel ou um arquivo de valores separados por vírgulas (CSV) que contenha os dados históricos de demanda.</span><span class="sxs-lookup"><span data-stu-id="0465a-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="0465a-114">O exemplo a seguir mostra como importar os dados de um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="0465a-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="0465a-115">Para obter mais informações sobre como importar dados, incluindo como limpar dados após uma importação, consulte [Visão geral sobre trabalhos de importação de dados e exportação](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) e os tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="0465a-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

## <a name="example"></a><span data-ttu-id="0465a-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0465a-116">Example</span></span>

<span data-ttu-id="0465a-117">Você pode usar o arquivo a seguir como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="0465a-117">You can use the following file as an example.</span></span> <span data-ttu-id="0465a-118">Baixe [HistoricalDemandData](/dynamics/s-e/).</span><span class="sxs-lookup"><span data-stu-id="0465a-118">Download the [HistoricalDemandData](/dynamics/s-e/).</span></span> <span data-ttu-id="0465a-119">Este arquivo contém os dados históricos de demanda do item D0001.</span><span class="sxs-lookup"><span data-stu-id="0465a-119">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="0465a-120">Ele contém apenas os seguintes campos obrigatórios: site, quantidade e a data de demanda.</span><span class="sxs-lookup"><span data-stu-id="0465a-120">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="0465a-121">Selecione a empresa para a qual serão importados os dados históricos de demanda.</span><span class="sxs-lookup"><span data-stu-id="0465a-121">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="0465a-122">Abra o espaço de trabalho **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="0465a-122">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="0465a-123">Selecione o bloco **Importação**.</span><span class="sxs-lookup"><span data-stu-id="0465a-123">Select the **Import** tile.</span></span>
4. <span data-ttu-id="0465a-124">Insira um nome para o projeto de importação, como **Importar a demanda histórica do item D0001**.</span><span class="sxs-lookup"><span data-stu-id="0465a-124">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="0465a-125">No campo **Formato de dados de origem**, selecione o formato do arquivo que você está importando.</span><span class="sxs-lookup"><span data-stu-id="0465a-125">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="0465a-126">Para importar o arquivo HistoricalDemandData para este exemplo, selecione **CSV**.</span><span class="sxs-lookup"><span data-stu-id="0465a-126">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="0465a-127">No campo **Nome da entidade**, selecione **Demanda histórica externa**.</span><span class="sxs-lookup"><span data-stu-id="0465a-127">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="0465a-128">Salve o arquivo no computador e depois carregue-o.</span><span class="sxs-lookup"><span data-stu-id="0465a-128">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="0465a-129">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="0465a-129">Select **Import**.</span></span>
9. <span data-ttu-id="0465a-130">A página **Resumo da execução** é aberta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0465a-130">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="0465a-131">Verifique os dados importados na página.</span><span class="sxs-lookup"><span data-stu-id="0465a-131">Verify the imported data on the page.</span></span>

<span data-ttu-id="0465a-132">Depois de importar os dados históricos de demanda, você poderá gerar uma previsão de demanda.</span><span class="sxs-lookup"><span data-stu-id="0465a-132">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0465a-133">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0465a-133">Additional resources</span></span>

[<span data-ttu-id="0465a-134">​Gerar uma previsão estatística​</span><span class="sxs-lookup"><span data-stu-id="0465a-134">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)  
[<span data-ttu-id="0465a-135">Visão geral de trabalhos de importação e exportação de dados</span><span class="sxs-lookup"><span data-stu-id="0465a-135">Data import and export jobs overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]