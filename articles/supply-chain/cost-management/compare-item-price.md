---
title: Relatório de comparação de armazenamento de preços de item
description: Saiba como gerar um Relatório de comparação de armazenamento de preços de item e, em seguida, procurar e/ou exportar o resultado.
author: AndersGirke
manager: tfehr
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 6c8c72a631d361d7dffb8d18e00636e51e7998d3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201930"
---
# <a name="compare-item-prices-storage-report"></a><span data-ttu-id="b6c06-103">Relatório de comparação de armazenamento de preços de item</span><span class="sxs-lookup"><span data-stu-id="b6c06-103">Compare item prices storage report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6c06-104">Este tópico explica como executar um **Relatório de comparação de armazenamento de preços de item** e disponibilizar a saída digitalmente, como uma página interativa no Dynamics 365 Supply Chain Management ou como um documento exportado em qualquer um dos vários formatos.</span><span class="sxs-lookup"><span data-stu-id="b6c06-104">This topic explains how to run a **Compare item prices storage** report and make the output available digitally, either as an interactive page in Dynamics 365 Supply Chain Management, or as an exported document in any of several formats.</span></span>

<span data-ttu-id="b6c06-105">Ao visualizar o relatório em seu navegador, as colunas e os saldos agregados são ajustados dinamicamente, dependendo do layout configurado.</span><span class="sxs-lookup"><span data-stu-id="b6c06-105">When you view the report in your browser, columns and aggregate balances are dynamically adjusted, depending on your configured layout.</span></span> <span data-ttu-id="b6c06-106">Você pode classificar os resultados, filtrá-los, detalhar os dados e muito mais.</span><span class="sxs-lookup"><span data-stu-id="b6c06-106">You can sort the results, filter them, drill down into the data, and more.</span></span>

<span data-ttu-id="b6c06-107">Os resultados do relatório são armazenados na entidade de dados **Comparar preços de item**, que permite filtrar e exportar os resultados para um formato como CSV ou Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b6c06-107">Report results are stored in the **Compare item prices** data entity, which lets you filter and export the results to a format such as CSV or Microsoft Excel.</span></span>

<span data-ttu-id="b6c06-108">O **Relatório de comparação de armazenamento de preços de item** é útil nos casos em que a saída contém muitas linhas.</span><span class="sxs-lookup"><span data-stu-id="b6c06-108">The **Compare item prices storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="b6c06-109">Por exemplo, a saída conterá muitas linhas se você tiver mais de 40.000 itens com um preço de item pendente na versão de avaliação de custo.</span><span class="sxs-lookup"><span data-stu-id="b6c06-109">For example, the output will contain many lines if you have more than 40,000 items holding a pending item price in the costing version.</span></span>

## <a name="enable-compare-item-prices-storage"></a><span data-ttu-id="b6c06-110">Habilitar comparação de armazenamento de preços de item</span><span class="sxs-lookup"><span data-stu-id="b6c06-110">Enable compare item prices storage</span></span>

<span data-ttu-id="b6c06-111">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="b6c06-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="b6c06-112">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b6c06-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="b6c06-113">Aqui o recurso está listado como:</span><span class="sxs-lookup"><span data-stu-id="b6c06-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="b6c06-114">**Módulo** - Gerenciamento de custos</span><span class="sxs-lookup"><span data-stu-id="b6c06-114">**Module** - Cost management</span></span>
- <span data-ttu-id="b6c06-115">**Nome do recurso** - Comparação de armazenamento de preços de item</span><span class="sxs-lookup"><span data-stu-id="b6c06-115">**Feature name** - Compare item price storage</span></span>

## <a name="generate-a-compare-item-prices-storage-report"></a><span data-ttu-id="b6c06-116">Gerar um relatório de comparação de armazenamento de preços de item</span><span class="sxs-lookup"><span data-stu-id="b6c06-116">Generate a Compare item prices storage report</span></span>

<span data-ttu-id="b6c06-117">Siga estas etapas para gerar e armazenar um **Relatório de comparação de armazenamento de preços de item**:</span><span class="sxs-lookup"><span data-stu-id="b6c06-117">Follow these steps to generate and store a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="b6c06-118">Acesse **Gerenciamento de custos > Consultas e relatórios > Relatórios de custo predeterminado > Comparação de armazenamento de preços de item**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-118">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="b6c06-119">Selecione **Novo** para abrir o painel **Comparar preços de item**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-119">Select **New** to open the **Compare item prices** pane.</span></span> <span data-ttu-id="b6c06-120">Defina as seguintes opções para determinar quais preços comparar no seu relatório:</span><span class="sxs-lookup"><span data-stu-id="b6c06-120">Set the following options to define which prices to compare in your report:</span></span>

    - <span data-ttu-id="b6c06-121">Na Guia Rápida **Parâmetros**, dê ao relatório um único **Nome** e use os campos nas seções **Preços pendentes a serem comparados** e **Preços usados na comparação** para definir quais preços e datas comparar.</span><span class="sxs-lookup"><span data-stu-id="b6c06-121">On the **Parameters** FastTab, give the report a unique **Name** and use the fields in the **Pending prices to compare** and **Prices used for comparison** sections to define which prices and dates to compare.</span></span>
    - <span data-ttu-id="b6c06-122">Na Guia Rápida **Registros a serem incluídos**, configure filtros e restrições para definir quais dados incluir no relatório.</span><span class="sxs-lookup"><span data-stu-id="b6c06-122">On the **Records to include** FastTab, set up filters and constraints to define which data to include in the report.</span></span>
    - <span data-ttu-id="b6c06-123">Na Guia Rápida **Executar em segundo plano**, configure como, quando e com que frequência você deseja gerar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b6c06-123">On the **Run in the background** FastTab, set up how, when, and the frequency at which you want to generate the report.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b6c06-124">Esse relatório é sempre executado como parte de um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="b6c06-124">This report is always executed as part of a batch job.</span></span>

1. <span data-ttu-id="b6c06-125">Selecione **OK** para aplicar suas configurações e fechar o painel.</span><span class="sxs-lookup"><span data-stu-id="b6c06-125">Select **OK** to apply your settings and close the pane.</span></span>

1. <span data-ttu-id="b6c06-126">Após a conclusão do trabalho em lotes, ele será listado na página **Comparação de armazenamento de preços de item**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-126">After the batch job is completed, it will be listed on the **Compare item prices storage** page.</span></span> <span data-ttu-id="b6c06-127">Pode ser necessário atualizar a página para ver o relatório.</span><span class="sxs-lookup"><span data-stu-id="b6c06-127">You may need to refresh the page to see the report.</span></span>

## <a name="explore-the-compare-item-prices-storage-report"></a><span data-ttu-id="b6c06-128">Explorar o Relatório de comparação de armazenamento de preços de item</span><span class="sxs-lookup"><span data-stu-id="b6c06-128">Explore the Compare item prices storage report</span></span>

<span data-ttu-id="b6c06-129">Depois de gerar um relatório, você pode visualizá-lo e explorá-lo a qualquer momento, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b6c06-129">After you've generated a report, you can view and explore it at any time as follows:</span></span>

1. <span data-ttu-id="b6c06-130">Acesse **Gerenciamento de custos > Consultas e relatórios > Relatórios de custo predeterminado > Comparação de armazenamento de preços de item**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-130">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="b6c06-131">Selecione um relatório na lista.</span><span class="sxs-lookup"><span data-stu-id="b6c06-131">Select a report from the list.</span></span>

1. <span data-ttu-id="b6c06-132">Execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b6c06-132">Do one of the following:</span></span>

    - <span data-ttu-id="b6c06-133">Selecione **Visão geral** para obter uma visão geral dos resultados do seu relatório.</span><span class="sxs-lookup"><span data-stu-id="b6c06-133">Select **Overview** to get an overview of your report results.</span></span>
    - <span data-ttu-id="b6c06-134">Selecione **Exibir detalhes** para ter uma visão mais detalhada do seu relatório</span><span class="sxs-lookup"><span data-stu-id="b6c06-134">Select **View details** to get a more detailed view of your report</span></span>

1. <span data-ttu-id="b6c06-135">Após a exibição selecionada ser aberta, você poderá fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b6c06-135">After the selected view opens, you can do the following:</span></span>

    - <span data-ttu-id="b6c06-136">Selecione quase qualquer cabeçalho de coluna para classificar ou filtrar a tabela por valores nessa coluna, assim como nos formulários mais padrão no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6c06-136">Select almost any column heading to sort or filter the table by values in that column, just as with most standard forms in Supply Chain Management.</span></span> <span data-ttu-id="b6c06-137">Observe que você não pode classificar ou filtrar a coluna **% de preço de alteração líquida** porque é um campo calculado.</span><span class="sxs-lookup"><span data-stu-id="b6c06-137">Note, you can't sort or filter the **Net change price %** column because it's a calculated field.</span></span>
    - <span data-ttu-id="b6c06-138">Selecione **Exibição de dimensão** para abrir um painel onde você pode escolher qual coluna de dimensão incluir no formulário.</span><span class="sxs-lookup"><span data-stu-id="b6c06-138">Select **Dimension display** to open a pane where you can choose which dimension column to include on the form.</span></span> <span data-ttu-id="b6c06-139">Defina **Salvar configuração** como **Sim** se deseja salvar essas configurações para que elas sejam preservadas na próxima vez que você abrir o relatório.</span><span class="sxs-lookup"><span data-stu-id="b6c06-139">Set **Save setup** to **Yes** if you'd like to save these settings so they will be preserved the next time you open the report.</span></span> <span data-ttu-id="b6c06-140">Selecione **OK** para aplicar suas configurações e fechar.</span><span class="sxs-lookup"><span data-stu-id="b6c06-140">Select **OK** to apply your settings and close.</span></span>
    - <span data-ttu-id="b6c06-141">Selecione qualquer linha no formulário e selecione **Exibir detalhes** para ver mais informações sobre o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="b6c06-141">Select any row in the form and then select **View details** to see more information about the selected item.</span></span> <span data-ttu-id="b6c06-142">Você poderá detalhar os dados a partir daqui.</span><span class="sxs-lookup"><span data-stu-id="b6c06-142">You'll be able to drill down into the data from here.</span></span>
    - <span data-ttu-id="b6c06-143">Selecione qualquer linha no formulário e, em seguida, selecione **Exibir gráfico de comparação** para ver uma representação gráfica interativa dos seus resultados relacionados ao item selecionado.</span><span class="sxs-lookup"><span data-stu-id="b6c06-143">Select any row in the form and then select **View comparison chart** to see an interactive graphical representation of your results as they relate to your selected item.</span></span> <span data-ttu-id="b6c06-144">Você pode explorar esses resultados selecionando vários elementos gráficos no gráfico e na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="b6c06-144">You can explore these results by selecting various graphical elements in the chart and chart legend.</span></span>
    - <span data-ttu-id="b6c06-145">Selecione qualquer linha no formulário e selecione **Exibir detalhes do cálculo** para ver mais informações sobre cálculos relacionados ao item selecionado.</span><span class="sxs-lookup"><span data-stu-id="b6c06-145">Select any row in the form and then select **View calculation details** to see more information about calculations related to the selected item.</span></span> <span data-ttu-id="b6c06-146">Você poderá detalhar os dados a partir daqui.</span><span class="sxs-lookup"><span data-stu-id="b6c06-146">You'll be able to drill down into the data from here.</span></span>

## <a name="export-the-compare-item-prices-storage-report"></a><span data-ttu-id="b6c06-147">Exportar o Relatório de comparação de armazenamento de preços de item</span><span class="sxs-lookup"><span data-stu-id="b6c06-147">Export the Compare item prices storage report</span></span>

<span data-ttu-id="b6c06-148">Cada relatório que você gera é armazenado na entidade de dados **Comparar preços de item**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-148">Each report that you generate is stored in the **Compare item prices** data entity.</span></span> <span data-ttu-id="b6c06-149">Você pode usar os recursos de gerenciamento de dados padrão do Supply Chain Management para exportar dados dessa entidade para qualquer formato de dados compatível, incluindo CSV ou Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b6c06-149">You can use the standard data management features of Supply Chain Management to export data from this entity to any supported data format, including CSV or Microsoft Excel.</span></span>

<span data-ttu-id="b6c06-150">Veja a seguir um exemplo de como exportar um **Relatório de comparação de armazenamento de preços de item**:</span><span class="sxs-lookup"><span data-stu-id="b6c06-150">The following is an example of how to export a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="b6c06-151">Acesse **Vá para Administração de sistema > Locais de trabalho > Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-151">Go to **System administration > Workspaces > Data management**.</span></span>

1. <span data-ttu-id="b6c06-152">Selecione o botão **Exportar** na seção **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-152">Select the **Export** button in the **Data management** section.</span></span>

1. <span data-ttu-id="b6c06-153">É aberta a página **Exportar**, que você usará para configurar seu trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="b6c06-153">The **Export** page opens, which you'll use to set up your export job.</span></span> <span data-ttu-id="b6c06-154">Comece dando ao seu trabalho uma **Nome do grupo**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-154">Start by giving your job a **Group name**.</span></span>

1. <span data-ttu-id="b6c06-155">Na seção **Entidades selecionadas**, selecione **Adicionar entidade** para abrir uma caixa de diálogo onde você pode definir as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b6c06-155">In the **Selected entities** section, select **Add entity** to open a dialog box where you can set the following options:</span></span>

    - <span data-ttu-id="b6c06-156">**Nome da entidade** - Selecione **Comparar preços de item**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-156">**Entity name** - Select **Compare item prices**.</span></span>
    - <span data-ttu-id="b6c06-157">**Formato de dados de destino** - Escolha o formato para o qual você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="b6c06-157">**Target data format** - Choose the format that you want to export to.</span></span>

1. <span data-ttu-id="b6c06-158">Selecione **Adicionar** para adicionar a nova linha e selecione **Fechar** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b6c06-158">Select **Add** to add the new row and then select **Close** to close the dialog box.</span></span>

1. <span data-ttu-id="b6c06-159">Geralmente, você exportará um relatório por vez.</span><span class="sxs-lookup"><span data-stu-id="b6c06-159">Usually you'll export one report at a time.</span></span> <span data-ttu-id="b6c06-160">Para isso, configure um **Filtro** da linha que você acabou de adicionar ao painel **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-160">To do this, set up a **Filter** for the row you just added to the **Inquiry** pane.</span></span> <span data-ttu-id="b6c06-161">Isso permitirá que você defina quais relatórios da entidade **Comparar preços de item** que você deseja incluir na sua exportação.</span><span class="sxs-lookup"><span data-stu-id="b6c06-161">This will let you define which reports from the **Compare item prices** entity that you want to include in your export.</span></span> <span data-ttu-id="b6c06-162">Defina as seguintes opções de filtro para exportar um único relatório:</span><span class="sxs-lookup"><span data-stu-id="b6c06-162">Set the following filter options to export a single report:</span></span>

    - <span data-ttu-id="b6c06-163">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="b6c06-163">On the **Range** tab, select **Add** to add a new row.</span></span>
    - <span data-ttu-id="b6c06-164">Defina **Tabela** como **Comparar preços de item**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-164">Set **Table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="b6c06-165">Defina **Tabela derivada** como **Comparar preços de item**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-165">Set **Derived table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="b6c06-166">Defina **Campo** como o campo pelo qual você deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="b6c06-166">Set **Field** to the field that you want to filter by.</span></span> <span data-ttu-id="b6c06-167">Em geral, você usará **Nome de execução** ou **Tempo de execução**.</span><span class="sxs-lookup"><span data-stu-id="b6c06-167">Usually you'll use **Execution name** or **Execution time**.</span></span>
    - <span data-ttu-id="b6c06-168">Defina **Critérios** como o valor do campo selecionado que você deseja procurar (o nome do relatório ou a hora em que o relatório foi gerado).</span><span class="sxs-lookup"><span data-stu-id="b6c06-168">Set **Criteria** to the value from your selected field that you want to look for (either the name of the report or the time the report was generated).</span></span>
    - <span data-ttu-id="b6c06-169">Se necessário, adicione mais linhas à tabela **Intervalo** até identificar o relatório que você procura exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="b6c06-169">If necessary, add more rows to the **Range** table until you have uniquely identified the report that you're looking for.</span></span>

1. <span data-ttu-id="b6c06-170">Selecione **OK** para salvar suas configurações e fechar.</span><span class="sxs-lookup"><span data-stu-id="b6c06-170">Select **OK** to save your settings and close.</span></span>

1. <span data-ttu-id="b6c06-171">Selecione **Salvar** para salvar sua configuração de exportação.</span><span class="sxs-lookup"><span data-stu-id="b6c06-171">Select **Save** to save your export setup.</span></span>

1. <span data-ttu-id="b6c06-172">Abra a guia **Opções de exportação** e selecione **Exportar agora** para gerar o arquivo de exportação.</span><span class="sxs-lookup"><span data-stu-id="b6c06-172">Open the **Export options** tab and select **Export now** to generate the export file.</span></span>

1. <span data-ttu-id="b6c06-173">É aberta a página **Resumo de execução** na qual você pode ver o status do seu trabalho de exportação e uma lista de entidades que foram exportadas.</span><span class="sxs-lookup"><span data-stu-id="b6c06-173">The **Execution summary** page opens, where you can see the status of your export job and a list of entities that were exported.</span></span> <span data-ttu-id="b6c06-174">Selecione a entidade **Comparar preços de item** listada na área **Status de processamento da entidade** e, em seguida, selecione **Baixar arquivo** para baixar os dados exportados dessa entidade.</span><span class="sxs-lookup"><span data-stu-id="b6c06-174">Select the **Compare item prices** entity listed in the **Entity processing status** area and then select **Download file** to download the data exported from that entity.</span></span>

<span data-ttu-id="b6c06-175">Para obter mais informações sobre como usar o gerenciamento de dados para exportar dados, consulte [Visão geral de trabalhos de importação e exportação de dados](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="b6c06-175">For more information about how to use data management to export data, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>
