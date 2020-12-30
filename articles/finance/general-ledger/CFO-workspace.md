---
title: Adicionar dimensões financeiras ao espaço de trabalho do CFO
description: Este tópico explica como adicionar dimensões financeiras ao espaço de trabalho do CFO, para que possam ser usadas para relatórios do razão e de orçamento.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 3817c6688339735c7478e85786efe15bd2372c91
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440329"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a><span data-ttu-id="fd983-103">Adicionar dimensões financeiras ao espaço de trabalho do CFO</span><span class="sxs-lookup"><span data-stu-id="fd983-103">Add financial dimensions to the CFO workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd983-104">Este tópico explica como adicionar dimensões financeiras ao espaço de trabalho do CFO, para que possam ser usadas para relatórios do razão e de orçamento.</span><span class="sxs-lookup"><span data-stu-id="fd983-104">This topic explains how to add financial dimensions to the Chief Financial Officer (CFO) workspace, so that they can be used for the ledger and budget reports.</span></span> <span data-ttu-id="fd983-105">O espaço de trabalho CFO tem uma guia **Visão geral** e uma guia **Financeiro**. Os relatórios dessas duas guias são apoiadas por duas medidas: LedgerActivityMeasure e BudgetActivityMeasure.</span><span class="sxs-lookup"><span data-stu-id="fd983-105">The CFO workspace has an **Overview** tab and a **Financial** tab. The reports on these two tabs are backed by two measures: LedgerActivityMeasure and BudgetActivityMeasure.</span></span> <span data-ttu-id="fd983-106">Há uma relação entre essas duas medidas e a entidade DimensionCombinationEntity.</span><span class="sxs-lookup"><span data-stu-id="fd983-106">There is a relation between those two measures and the DimensionCombinationEntity entity.</span></span> <span data-ttu-id="fd983-107">Portanto, você pode selecionar dimensões.</span><span class="sxs-lookup"><span data-stu-id="fd983-107">Therefore, you can select dimensions.</span></span>

1. <span data-ttu-id="fd983-108">No Finance, na página **Repositório de Entidades**, atualize as medidas **LedgerActivityMeasure** e **BudgetActivityMeasure**.</span><span class="sxs-lookup"><span data-stu-id="fd983-108">In Finance, on the **Entity Store** page, update the **LedgerActivityMeasure** and the **BudgetActivityMeasure** measures.</span></span>
2. <span data-ttu-id="fd983-109">No Microsoft Visual Studio, abra o Explorador de Aplicativos e pesquise por **LedgerCFO**.</span><span class="sxs-lookup"><span data-stu-id="fd983-109">In Microsoft Visual Studio, open Application Explorer, and search for **LedgerCFO**.</span></span>
3. <span data-ttu-id="fd983-110">Em **Recursos**, abra **LedgerCFOWorkspacePBIX**.</span><span class="sxs-lookup"><span data-stu-id="fd983-110">Under **Resources**, open **LedgerCFOWorkspacePBIX**.</span></span>
4. <span data-ttu-id="fd983-111">Quando o recurso for aberto na área de trabalho do Microsoft Power BI, selecione **Obter dados**, **Banco de dados do SQL Server** e, em seguida, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="fd983-111">When the resource opens in Microsoft Power BI desktop, select **Get Data**, select **SQL Server database**, and then select **Connect**.</span></span>
5. <span data-ttu-id="fd983-112">Insira o nome do servidor e insira **AxDW** como o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fd983-112">Enter the server name, and enter **AxDW** as the database.</span></span> <span data-ttu-id="fd983-113">Selecione **DirectQuery** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd983-113">Select **DirectQuery**, and then select **OK**.</span></span>
6. <span data-ttu-id="fd983-114">Procure e selecione **LedgerActivityMeasure\_DimensionCombination** e, em seguida, selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="fd983-114">Search for and select **LedgerActivityMeasure\_DimensionCombination**, and then select **Load**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fd983-115">Na lista de **Campos**, renomeie a tabela **Dimensões financeiras**, para que seja fácil identificá-la.</span><span class="sxs-lookup"><span data-stu-id="fd983-115">In the **Fields** list, rename the table **Financial dimensions**, so that it's easy to identify.</span></span>

7. <span data-ttu-id="fd983-116">Selecione **Gerenciar relacionamentos** e, em seguida, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fd983-116">Select **Manage Relationships**, and then select **New**.</span></span>
8. <span data-ttu-id="fd983-117">No primeiro campo, selecione **Atividades da contabilidade** e, em seguida, selecione **LedgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="fd983-117">In the first field, select **General Ledger Activities**, and then select **LedgerDimension**.</span></span>
9. <span data-ttu-id="fd983-118">No segundo campo, selecione **LedgerActivityMeasure\_DimensionCombination** (ou **Dimensões financeiras**, caso tenha renomeado a tabela).</span><span class="sxs-lookup"><span data-stu-id="fd983-118">In the second field, select **LedgerActivityMeasure\_DimensionCombination** (or **Financial dimensions** if you renamed the table).</span></span> <span data-ttu-id="fd983-119">Selecione o cabeçalho **DimensionCombinationRECID**.</span><span class="sxs-lookup"><span data-stu-id="fd983-119">Select the  **DimensionCombinationRECID** header.</span></span>
10. <span data-ttu-id="fd983-120">No campo **Cardinalidade**, selecione **Muitos para Um**.</span><span class="sxs-lookup"><span data-stu-id="fd983-120">In the **Cardinality** field, select **Many to One**.</span></span>
11. <span data-ttu-id="fd983-121">Altere o valor de **Direção do filtro cruzado** para **Único**.</span><span class="sxs-lookup"><span data-stu-id="fd983-121">Change the **Cross filter direction** value to **Single**.</span></span>
12. <span data-ttu-id="fd983-122">Selecione **Ativar este relacionamento** e **Pressuponha integridade referencial**, selecione **OK** e, em seguida, **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="fd983-122">Select both **Make this relationship active** and **Assume referential integrity**, select **OK**, and then select **Close**.</span></span>

    <span data-ttu-id="fd983-123">[![Criar um relacionamento](./media/Create-relationship.png)](./media/Create-relationship.png)</span><span class="sxs-lookup"><span data-stu-id="fd983-123">[![Create a relationship](./media/Create-relationship.png)](./media/Create-relationship.png)</span></span>

13. <span data-ttu-id="fd983-124">Na lista de **Campos**, você verá a tabela e as dimensões financeiras disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fd983-124">In the **Fields** list, you should see the table and the available financial dimensions.</span></span> <span data-ttu-id="fd983-125">Arraste as dimensões financeiras desejadas para os filtros no nível de relatório.</span><span class="sxs-lookup"><span data-stu-id="fd983-125">Drag the financial dimensions that you want to the report-level filters.</span></span>
14. <span data-ttu-id="fd983-126">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="fd983-126">Save your changes.</span></span>
15. <span data-ttu-id="fd983-127">Na árvore de objetos de aplicativo (AOT), clique com o botão direito do mouse no projeto e selecione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="fd983-127">In the Application Object Tree (AOT), right-click your project, and then select **Synchronize**.</span></span>
16. <span data-ttu-id="fd983-128">Crie o projeto e abra o aplicativo para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="fd983-128">Build your project, and then open the application to view the results.</span></span>

    <span data-ttu-id="fd983-129">[![Espaço de trabalho concluído](./media/workspace.png)](./media/workspace.png)</span><span class="sxs-lookup"><span data-stu-id="fd983-129">[![Completed workspace](./media/workspace.png)](./media/workspace.png)</span></span>
