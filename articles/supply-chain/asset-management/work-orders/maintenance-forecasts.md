---
title: Previsões de manutenção
description: Este tópico explica as previsões de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2686dd6db032239e2a3aac03f3998cee055302f6
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4422633"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="b478e-103">Previsões de manutenção</span><span class="sxs-lookup"><span data-stu-id="b478e-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="b478e-104">Quando cria uma ordem de serviço, você cria trabalhos da ordem de serviço que possuem ativos e tipos de trabalho de manutenção relacionados.</span><span class="sxs-lookup"><span data-stu-id="b478e-104">When you create a work order, you create work order jobs that have related assets and maintenance job types.</span></span> <span data-ttu-id="b478e-105">Quando você seleciona um tipo de trabalho de manutenção que contém previsões de manutenção, as previsões são copiadas automaticamente para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b478e-105">When you select a maintenance job type that contains maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="b478e-106">Você talvez possa adicionar ou excluir linhas de previsão de uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b478e-106">You might be able to add forecast lines to a work order or delete them from a work order.</span></span> <span data-ttu-id="b478e-107">A configuração do estado de ciclo de vida da ordem de serviço, o tipo de projeto relacionado e as regras de estágio relacionadas ao tipo de projeto determinam se você pode adicionar ou editar as linhas de previsão.</span><span class="sxs-lookup"><span data-stu-id="b478e-107">The setup of the work order lifecycle state, the related project type, and the stage rules that are related to the project type determine whether you can add or edit forecast lines.</span></span> <span data-ttu-id="b478e-108">Para obter mais informações sobre os estados de ciclo de vida da ordem de serviço e os estágios do projeto relacionados, consulte [Previsões, ordens de serviço e projetos](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="b478e-108">For more information about work order lifecycle states and related project stages, see [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

1. <span data-ttu-id="b478e-109">Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="b478e-109">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="b478e-110">Selecione a ordem de serviço na lista e, em seguida, no Painel de Ação, na guia **Ordem de serviço**, no grupo **Projeto**, selecione **Previsão**.</span><span class="sxs-lookup"><span data-stu-id="b478e-110">Select the work order in the list, and then, on the Action Pane > **Work order** tab > the **Project** group, select **Forecast**.</span></span> <span data-ttu-id="b478e-111">A página **Previsão de manutenção da ordem de serviço** mostra as linhas de previsão do tipo de trabalho de manutenção selecionado no trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b478e-111">The **Work order maintenance forecast** page shows forecast lines from the maintenance job type that is selected on the work order job.</span></span>


## <a name="add-an-hours-forecast-to-a-work-order"></a><span data-ttu-id="b478e-112">Adicionar previsão de horas para uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="b478e-112">Add an hours forecast to a work order</span></span>

1. <span data-ttu-id="b478e-113">Na página **Previsão de manutenção da ordem de serviço**, selecione o trabalho da ordem de serviço no qual adicionar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="b478e-113">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="b478e-114">Na Guia Rápida **Horas**, selecione **Adicionar** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="b478e-114">On the **Hours** FastTab, select **Add** to create a new line.</span></span>

3. <span data-ttu-id="b478e-115">No campo **Categoria**, selecione uma categoria.</span><span class="sxs-lookup"><span data-stu-id="b478e-115">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="b478e-116">Insira o número de horas previstas no campo **Horas**.</span><span class="sxs-lookup"><span data-stu-id="b478e-116">In the **Hours** field, enter the number of forecasted hours.</span></span>

5. <span data-ttu-id="b478e-117">No campo **Propriedade da linha**, selecione o tipo de encargo a ser usado na linha.</span><span class="sxs-lookup"><span data-stu-id="b478e-117">In the **Line property** field, select the type of charge that should be used on the line.</span></span>


## <a name="add-an-items-forecast-to-a-work-order"></a><span data-ttu-id="b478e-118">Adicionar previsão de itens em uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="b478e-118">Add an items forecast to a work order</span></span>

<span data-ttu-id="b478e-119">Há três maneiras de adicionar itens a uma previsão de manutenção de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b478e-119">There are three ways to add items to a work order maintenance forecast.</span></span> <span data-ttu-id="b478e-120">Você pode criar linhas para os itens (peças sobressalentes) que não foram incluídos na lista de peças sobressalentes ou na BOM (lista de materiais) de ativos, pode selecionar peças sobressalentes na lista aprovada de peças sobressalentes ou selecionar itens da BOM de ativos.</span><span class="sxs-lookup"><span data-stu-id="b478e-120">You can create lines for items (spare parts) that aren't included on the spare parts list or the asset bill of materials (BOM), you can select spare parts from the approved spare parts list, or you can select items from the asset BOM.</span></span>

- <span data-ttu-id="b478e-121">Na página **Previsão de manutenção da ordem de serviço**, selecione o trabalho da ordem de serviço no qual adicionar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="b478e-121">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

- <span data-ttu-id="b478e-122">Na Guia Rápida **Itens**, adicione itens à previsão de manutenção usando o método apropriado.</span><span class="sxs-lookup"><span data-stu-id="b478e-122">On the **Items** FastTab, add items to the maintenance forecast by using the appropriate method.</span></span>

<span data-ttu-id="b478e-123">Para criar uma linha para uma peça sobressalente que não está na lista de peças sobressalentes ou na BOM de ativos, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b478e-123">To create a line for a spare part that isn't on the spare parts list or the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="b478e-124">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b478e-124">Select **Add**.</span></span>
2. <span data-ttu-id="b478e-125">No campo **Nº do item**, selecione o item.</span><span class="sxs-lookup"><span data-stu-id="b478e-125">In the **Item number** field, select the item.</span></span>
3. <span data-ttu-id="b478e-126">No campo **Quantidade de venda**, insira a quantidade.</span><span class="sxs-lookup"><span data-stu-id="b478e-126">In the **Sales quantity** field, enter the quantity.</span></span>
4. <span data-ttu-id="b478e-127">No campo **Unidade**, selecione a unidade de medida da quantidade.</span><span class="sxs-lookup"><span data-stu-id="b478e-127">In the **Unit** field, select the unit of measure for the quantity.</span></span>
5. <span data-ttu-id="b478e-128">Nos campos **Preço de custo** e **Moeda**, informe os valores apropriados.</span><span class="sxs-lookup"><span data-stu-id="b478e-128">In the **Cost price** and **Currency** fields, enter appropriate values.</span></span>
6. <span data-ttu-id="b478e-129">No campo **Propriedade da linha**, selecione uma propriedade de linha.</span><span class="sxs-lookup"><span data-stu-id="b478e-129">In the **Line property** field, select a line property.</span></span>
7. <span data-ttu-id="b478e-130">Para alterar a lista de dimensões exibida nas linhas do item, selecione **Estoque** > **Exibir dimensões**, selecione as dimensões e, depois, defina a opção **Salvar configuração** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b478e-130">To change the list of dimensions that is shown on the item lines, select **Inventory** > **Display dimensions**, select the dimensions, and then set the **Save setup** option to **Yes**.</span></span>

<span data-ttu-id="b478e-131">Para adicionar uma peça sobressalente de uma lista aprovada de peças sobressalentes, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b478e-131">To add a spare part from an approved spare parts list, follow these steps:</span></span>

1. <span data-ttu-id="b478e-132">Selecione **Adicionar peças sobressalentes**.</span><span class="sxs-lookup"><span data-stu-id="b478e-132">Select **Add spare parts**.</span></span>
2. <span data-ttu-id="b478e-133">Selecione a peça sobressalente e edite as informações relacionadas, conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="b478e-133">Select the spare part, and edit the related information as you require.</span></span>
3. <span data-ttu-id="b478e-134">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b478e-134">Select **OK**.</span></span>

<span data-ttu-id="b478e-135">Para adicionar um item da BOM de ativos, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b478e-135">To add an item from the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="b478e-136">Selecione **Adicionar itens da BOM**.</span><span class="sxs-lookup"><span data-stu-id="b478e-136">Select **Add BOM items**.</span></span>
2. <span data-ttu-id="b478e-137">Selecione o item e edite as informações relacionadas, conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="b478e-137">Select the item, and edit the related information as you require.</span></span>
3. <span data-ttu-id="b478e-138">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b478e-138">Select **OK**.</span></span>

<span data-ttu-id="b478e-139">Para obter uma visão geral que mostre onde o item na linha selecionada é usado em relação a ativos, padrões de tipo de trabalho de manutenção, peças sobressalentes e ordens de serviço no Gerenciamento de Ativos, selecione **Item onde usado**.</span><span class="sxs-lookup"><span data-stu-id="b478e-139">To get an overview that shows where the item on the selected line is used in relation to assets, maintenance job type defaults, spare parts, and work orders in Asset Management, select **Item where used**.</span></span> <span data-ttu-id="b478e-140">Para obter mais informações sobre essa visão geral, consulte [Item onde usado](../controlling-and-reporting/item-where-used.md).</span><span class="sxs-lookup"><span data-stu-id="b478e-140">For more information about this overview, see [Item where used](../controlling-and-reporting/item-where-used.md).</span></span>


## <a name="add-an-expense-forecast-to-a-work-order"></a><span data-ttu-id="b478e-141">Adicionar previsão de despesa a uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="b478e-141">Add an expense forecast to a work order</span></span>

1. <span data-ttu-id="b478e-142">Na página **Previsão de manutenção da ordem de serviço**, selecione o trabalho da ordem de serviço no qual adicionar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="b478e-142">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="b478e-143">Na Guia Rápida **Despesa**, selecione **Adicionar** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="b478e-143">On the **Expense** FastTab, select **Add** to create a line.</span></span>

3. <span data-ttu-id="b478e-144">No campo **Categoria**, selecione uma categoria.</span><span class="sxs-lookup"><span data-stu-id="b478e-144">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="b478e-145">No campo **Quantidade**, insira a quantidade.</span><span class="sxs-lookup"><span data-stu-id="b478e-145">In the **Quantity** field, enter the quantity.</span></span>

5. <span data-ttu-id="b478e-146">Nos campos **Preço de custo**, **Moeda de venda** e **Preço de venda**, insira os valores apropriados.</span><span class="sxs-lookup"><span data-stu-id="b478e-146">In the **Cost price**, **Sales currency**, and **Sales price** fields, enter appropriate values.</span></span>

6. <span data-ttu-id="b478e-147">No campo **Propriedade da linha**, selecione o tipo de encargo a ser usado na linha.</span><span class="sxs-lookup"><span data-stu-id="b478e-147">In the **Line property** field, select the type of charge that should be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="b478e-148">A Guia Rápida **Totais da previsão de manutenção** mostra uma visão geral do número de linhas que foram criadas em cada Guia Rápida para o trabalho da ordem de serviço selecionado e para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b478e-148">The **Maintenance forecast totals** FastTab shows an overview of the number of lines that have been created, for the selected work order job and for the work order, on each FastTab.</span></span> <span data-ttu-id="b478e-149">Também mostra o total de horas de trabalho previstas para o trabalho da ordem de serviço e para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b478e-149">It also shows the total forecasted work hours for the work order job and the work order.</span></span>

<span data-ttu-id="b478e-150">A ilustração a seguir mostra um exemplo da página **Previsão de manutenção da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b478e-150">The illustration below shows an example of the **Work order maintenance forecast** page.</span></span>

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="b478e-152">Atualização automática de previsões de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="b478e-152">Automatic update of work order forecasts</span></span>

<span data-ttu-id="b478e-153">Se os valores de custos por hora, custos do item e despesas forem atualizados em outros módulos do Microsoft Dynamics 365 for Finance and Operations, as previsões da ordem de serviço no Gerenciamento de Ativos poderão ser automaticamente atualizadas para refletir essas alterações.</span><span class="sxs-lookup"><span data-stu-id="b478e-153">If hour costs, item costs, and expenses are updated in other modules in Microsoft Dynamics 365 for Finance and Operations, work order forecasts in Asset Management can automatically be updated to reflect those changes.</span></span> <span data-ttu-id="b478e-154">Esse recurso ajuda a garantir que os preços de custo mais recentes sejam sempre usados nas previsões de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b478e-154">This capability helps guarantee that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="b478e-155">Você também pode fazer atualizações semelhantes para [previsões de tipo de trabalho de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="b478e-155">You can also do similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="b478e-156">Selecione **Gerenciamento de ativos** > **Periódico** > **Previsão** > **Atualizar previsão da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b478e-156">Select **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="b478e-157">Na caixa de diálogo **Atualizar previsão da ordem de serviço**, na Guia Rápida **Registros a serem incluídos**, você pode adicionar seleções relacionadas a ordens de serviço ou trabalhos da ordem de serviço específicos, conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="b478e-157">In the **Update work order forecast** dialog, on the **Records to include** FastTab, you can add selections regarding specific work orders or work order jobs, as you require.</span></span> <span data-ttu-id="b478e-158">Clique em **Filtro** para fazer as seleções relevantes.</span><span class="sxs-lookup"><span data-stu-id="b478e-158">Click **Filter** to make the relevant selections.</span></span>

3. <span data-ttu-id="b478e-159">Na Guia Rápida **Executar em segundo plano**, você pode configurar a atualização automática como um trabalho em lote, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b478e-159">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

4. <span data-ttu-id="b478e-160">Selecione **OK** para iniciar a atualização da previsão.</span><span class="sxs-lookup"><span data-stu-id="b478e-160">Select **OK** to start the forecast update.</span></span>


<span data-ttu-id="b478e-161">A ilustração a seguir mostra um exemplo da caixa de diálogo **Atualizar previsão da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b478e-161">The illustration below shows an example of the **Update work order forecast** dialog.</span></span>

![Figura 2](media/07-work-orders.png)
