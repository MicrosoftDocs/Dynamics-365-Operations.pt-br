---
title: "Importar dados históricos para previsões de demanda"
description: "Para obter previsões de demanda precisas, você precisará dos dados históricos de demanda por item ou por chave de alocação de item. Este tópico explica como usar entidades de dados para importar dados históricos de demanda de qualquer sistema, de forma que você tenha um histórico de dados de previsão de demanda mais amplo."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 97d374230cc6e833b9f585de000e1252f2a78b9d
ms.openlocfilehash: c46b659a0ecffd6180fd0a76ff1b8d228f121571
ms.contentlocale: pt-br
ms.lasthandoff: 08/30/2017

---

# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="542c1-104">Importar dados históricos para previsões de demanda</span><span class="sxs-lookup"><span data-stu-id="542c1-104">Import historical data for demand forecasts</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="542c1-105">Para ajudar a garantir a precisão das previsões de demanda, será necessário ter todos os dados históricos de demanda possíveis que possam ser obtidos por item ou por chave de alocação de item.</span><span class="sxs-lookup"><span data-stu-id="542c1-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="542c1-106">Se os dados históricos de demanda ainda não tiverem sido importados, use entidade de dados **Demanda histórica externa** (ReqDemPlanHistoricalExternalDemandEntity) no Microsoft Dynamics 365 for Finance and Operations para importá-los.</span><span class="sxs-lookup"><span data-stu-id="542c1-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Microsoft Dynamics 365 for Finance and Operations to import it.</span></span>

<span data-ttu-id="542c1-107">No espaço de trabalho **Gerenciamento de dados**, você pode ter uma visão geral de todos os campos na entidade.</span><span class="sxs-lookup"><span data-stu-id="542c1-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="542c1-108">Abra o espaço de trabalho **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="542c1-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="542c1-109">Clique no bloco **Entidades de dados**.</span><span class="sxs-lookup"><span data-stu-id="542c1-109">Click the **Data entities** tile.</span></span>
3. <span data-ttu-id="542c1-110">Pesquise a lista de entidades para **Demanda histórica externa**.</span><span class="sxs-lookup"><span data-stu-id="542c1-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="542c1-111">Clique em **Campos de destino**.</span><span class="sxs-lookup"><span data-stu-id="542c1-111">Click **Target fields**.</span></span> <span data-ttu-id="542c1-112">Os seguintes campos de entidade são obrigatórios: site (**DeliveringSiteId**), data (**DemandDate**), quantidade (**DemandQuantity**) e número de item (**ItemNumber**) ou chave de alocação de item (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="542c1-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="542c1-113">Para usar a entidade de dados, você deverá ter um arquivo do Microsoft Excel ou um arquivo de valores separados por vírgulas (CSV) que contenha os dados históricos de demanda.</span><span class="sxs-lookup"><span data-stu-id="542c1-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="542c1-114">O exemplo a seguir mostra como importar os dados de um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="542c1-114">The following example shows how to import the data from a CSV file.</span></span>

## <a name="example"></a><span data-ttu-id="542c1-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="542c1-115">Example</span></span>

<span data-ttu-id="542c1-116">Você pode usar o arquivo a seguir como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="542c1-116">You can use the following file as an example.</span></span> <span data-ttu-id="542c1-117">Baixe [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span><span class="sxs-lookup"><span data-stu-id="542c1-117">Download the [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span></span> <span data-ttu-id="542c1-118">Este arquivo contém os dados históricos de demanda do item D0001.</span><span class="sxs-lookup"><span data-stu-id="542c1-118">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="542c1-119">Ele contém apenas os seguintes campos obrigatórios: site, quantidade e a data de demanda.</span><span class="sxs-lookup"><span data-stu-id="542c1-119">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="542c1-120">Selecione a empresa para a qual serão importados os dados históricos de demanda.</span><span class="sxs-lookup"><span data-stu-id="542c1-120">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="542c1-121">Abra o espaço de trabalho **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="542c1-121">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="542c1-122">Clique no bloco **Importar**.</span><span class="sxs-lookup"><span data-stu-id="542c1-122">Click the **Import** tile.</span></span>
4. <span data-ttu-id="542c1-123">Insira um nome para o projeto de importação, como **Importar a demanda histórica do item D0001**.</span><span class="sxs-lookup"><span data-stu-id="542c1-123">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="542c1-124">No campo **Formato de dados de origem**, selecione o formato do arquivo que você está importando.</span><span class="sxs-lookup"><span data-stu-id="542c1-124">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="542c1-125">Para importar o arquivo HistoricalDemandData para este exemplo, selecione **CSV**.</span><span class="sxs-lookup"><span data-stu-id="542c1-125">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="542c1-126">No campo **Nome da entidade**, selecione **Demanda histórica externa**.</span><span class="sxs-lookup"><span data-stu-id="542c1-126">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="542c1-127">Salve o arquivo no computador e depois carregue-o.</span><span class="sxs-lookup"><span data-stu-id="542c1-127">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="542c1-128">Clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="542c1-128">Click **Import**.</span></span>
9. <span data-ttu-id="542c1-129">A página **Resumo da execução** é aberta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="542c1-129">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="542c1-130">Verifique os dados importados na página.</span><span class="sxs-lookup"><span data-stu-id="542c1-130">Verify the imported data on the page.</span></span>

<span data-ttu-id="542c1-131">Depois de importar os dados históricos de demanda, você poderá gerar uma previsão de demanda.</span><span class="sxs-lookup"><span data-stu-id="542c1-131">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="see-also"></a><span data-ttu-id="542c1-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="542c1-132">See also</span></span>

[<span data-ttu-id="542c1-133">Gerar uma previsão estatística de linha de base</span><span class="sxs-lookup"><span data-stu-id="542c1-133">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)

