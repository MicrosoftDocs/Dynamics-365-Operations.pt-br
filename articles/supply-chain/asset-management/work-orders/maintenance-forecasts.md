---
title: Previsões de manutenção
description: Este tópico explica as previsões de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1a416bbb79be3f25998d3c0da8d231d0df808685
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875507"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="bcf69-103">Previsões de manutenção</span><span class="sxs-lookup"><span data-stu-id="bcf69-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="bcf69-104">Quando você cria uma ordem de serviço, você cria trabalhos da ordem de serviço com ativos e tipos de trabalho de manutenção relacionados.</span><span class="sxs-lookup"><span data-stu-id="bcf69-104">When you create a work order, you create work order jobs with related assets and maintenance job types.</span></span> <span data-ttu-id="bcf69-105">Quando você seleciona um tipo de trabalho de manutenção que contém previsões de manutenção, as previsões são copiadas automaticamente para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="bcf69-105">When you select a maintenance job type containing maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="bcf69-106">Você pode adicionar ou excluir linhas de previsão em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="bcf69-106">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="bcf69-107">A configuração de um estado de ciclo de vida de ordem de serviço, o tipo de projeto relacionado e as regras de estágio relacionadas ao tipo de projeto determinam se você é capaz de adicionar ou editar linhas de previsão.</span><span class="sxs-lookup"><span data-stu-id="bcf69-107">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determines if you are able to add or edit forecast lines.</span></span> 

1. <span data-ttu-id="bcf69-108">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="bcf69-109">Selecione a ordem de serviço na lista e clique em **Previsão**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-109">Select the work order in the list, and click **Forecast**.</span></span> <span data-ttu-id="bcf69-110">Na **Previsão de manutenção da ordem de serviço**, são exibidas as linhas de previsão do tipo de trabalho de manutenção selecionadas no trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="bcf69-110">In **Work order maintenance forecast**, forecast lines from the maintenance job type selected on the work order job are displayed.</span></span>


## <a name="add-hours-forecast-to-a-work-order"></a><span data-ttu-id="bcf69-111">Adicione a previsão de horas para uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="bcf69-111">Add hours forecast to a work order</span></span>

1. <span data-ttu-id="bcf69-112">Selecione o trabalho da ordem de serviço para o qual você deseja adicionar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="bcf69-112">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="bcf69-113">Na Guia Rápida **Horas**, clique em **Adicionar** para criar uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="bcf69-113">On the **Hours** FastTab, click **Add** to create a new line.</span></span>

3. <span data-ttu-id="bcf69-114">Selecione uma categoria no campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-114">Select a category in the **Category** field.</span></span>

4. <span data-ttu-id="bcf69-115">Insira o número de horas previstas no campo **Horas**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-115">Insert number of forecasted hours in the **Hours** field.</span></span>

5. <span data-ttu-id="bcf69-116">No campo **Propriedade da linha**, selecione o tipo de encargo a ser usado na linha.</span><span class="sxs-lookup"><span data-stu-id="bcf69-116">In the **Line property** field, select the charge type to be used on the line.</span></span>


## <a name="add-items-forecast-to-a-work-order"></a><span data-ttu-id="bcf69-117">Adicione a previsão de itens a uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="bcf69-117">Add items forecast to a work order</span></span>

<span data-ttu-id="bcf69-118">Existem três maneiras de adicionar itens a uma previsão de manutenção de ordem de serviço: você pode criar linhas para itens (peças sobressalentes) que não estão incluídas na lista de peças de reposição ou BOM de ativos, é possível selecionar peças sobressalentes da lista de peças de reposição aprovadas e você pode selecionar itens da BOM de ativos.</span><span class="sxs-lookup"><span data-stu-id="bcf69-118">There are three ways to add items to a work order maintenance forecast: You can create lines for items (spare parts) that are not included in the spare parts list or asset BOM, you can select spare parts from the approved spare parts list, and you can select items from the asset BOM.</span></span>

1. <span data-ttu-id="bcf69-119">Selecione o trabalho da ordem de serviço para o qual você deseja adicionar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="bcf69-119">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="bcf69-120">Selecione a Guia Rápida **Itens**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-120">Select the **Items** FastTab.</span></span>

3. <span data-ttu-id="bcf69-121">Clique em **Adicionar** para criar uma nova linha de uma peça sobressalente que não está na lista de peças sobressalentes ou na lista de BOM de ativos.</span><span class="sxs-lookup"><span data-stu-id="bcf69-121">Click **Add** to create a new line for a spare part that is not on the spare parts list or the asset BOM list.</span></span>

4. <span data-ttu-id="bcf69-122">Selecione o item no campo **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-122">Select the item in the **Item number** field.</span></span>

5. <span data-ttu-id="bcf69-123">Insira a quantidade no campo **Quantidade de venda** e selecione uma unidade de quantidade no campo **Unidade**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-123">Insert quantity in the **Sales quantity** field, and select a quantity unit in the **Unit** field.</span></span>

6. <span data-ttu-id="bcf69-124">Insira o preço de custo estimado e a moeda nos campos relevantes e selecione uma **Propriedade da linha**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-124">Insert cost price and currency in the relevant fields, and select a **Line property**.</span></span>

7. <span data-ttu-id="bcf69-125">Se quiser modificar a lista de dimensões exibidas nas linhas do item, clique em **Estoque** > **Dimensões de exibição**, selecione as dimensões e depois "Sim” no botão de alternância **Salvar configuração**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-125">If you want to change the list of dimensions displayed on the item lines, click **Inventory** > **Display dimensions**, select the dimensions, and select "Yes" on the **Save setup** toggle button.</span></span>

8. <span data-ttu-id="bcf69-126">Se quiser adicionar uma peça sobressalente aprovada à previsão de manutenção, clique em **Adicionar peças sobressalentes**, selecione a peça, edite as informações relacionadas, se necessário, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-126">If you want to add an approved spare part to the maintenance forecast, click **Add spare parts**, select the spare part, edit related information if required, and click **OK**.</span></span>

9. <span data-ttu-id="bcf69-127">Se quiser adicionar itens da BOM de ativos à previsão, clique em **Adicionar itens da BOM**, selecione o item, edite as informações relacionadas, se necessário, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-127">If you want to add asset BOM items to the forecast, click **Add BOM items**, select the item, edit related information if required, and click **OK**.</span></span>

10. <span data-ttu-id="bcf69-128">Clique em **Item onde usado** se quiser obter uma visão geral de onde o item é usado na linha selecionada no Gerenciamento de Ativos em relação aos ativos, padrões do tipo de trabalho de manutenção, peças sobressalentes e ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="bcf69-128">Click **Item where used** if you want to get an overview of where the item on the selected line is used in Asset Management in relation to assets, maintenance job type defaults, spare parts, and work orders.</span></span> 



## <a name="add-expense-forecast-to-a-work-order"></a><span data-ttu-id="bcf69-129">Adicione a previsão de despesa a uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="bcf69-129">Add expense forecast to a work order</span></span>

1. <span data-ttu-id="bcf69-130">Este tópico explica como adicionar uma previsão de despesa a uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="bcf69-130">This topic explains how to add an expense forecast to a work order.</span></span> <span data-ttu-id="bcf69-131">No lado esquerdo do formulário, selecione o trabalho da ordem de serviço no qual você deseja adicionar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="bcf69-131">In the left-hand side of the form, select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="bcf69-132">Selecione a Guia Rápida **Despesas**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-132">Select the **Expense** FastTab.</span></span>

3. <span data-ttu-id="bcf69-133">Clique em **Adicionar** para criar uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="bcf69-133">Click **Add** to create a new line.</span></span>

4. <span data-ttu-id="bcf69-134">Selecione uma categoria no campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-134">Select a category in the **Category** field.</span></span>

5. <span data-ttu-id="bcf69-135">Insira quantidade no campo **Quantidade**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-135">Insert quantity in the **Quantity** field.</span></span>

6. <span data-ttu-id="bcf69-136">Insira preço de custo, moeda de vendas e preço de venda nos campos relevantes.</span><span class="sxs-lookup"><span data-stu-id="bcf69-136">Insert cost price, sales currency, and sales price in the relevant fields.</span></span>

7. <span data-ttu-id="bcf69-137">No campo **Propriedade da linha**, selecione o tipo de encargo a ser usado na linha.</span><span class="sxs-lookup"><span data-stu-id="bcf69-137">In the **Line property** field, select the charge type to be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="bcf69-138">Na Guia Rápida **Totais da previsão de manutenção**, você poderá ver uma visão geral do número de linhas criadas em cada guia, para o trabalho da ordem de serviço e para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="bcf69-138">On the **Maintenance forecast totals** FastTab, you can see an overview of the number of lines created on each tab, for the selected work order job and for the work order.</span></span> <span data-ttu-id="bcf69-139">Além disso, você poderá ver uma soma de horas de trabalho esperadas para o trabalho da ordem de serviço e para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="bcf69-139">Also, you can see a sum of forecasted work hours for the work order job and for the work order.</span></span>

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="bcf69-141">Atualização automática de previsões de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="bcf69-141">Automatic update of work order forecasts</span></span>

<span data-ttu-id="bcf69-142">No Gerenciamento de Ativos, você pode atualizar todas as alterações nas previsões da ordem de serviço referentes aos custos da hora, custos do item e despesas, que foram atualizadas em outros módulos no Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bcf69-142">In Asset Management, you can automatically update any changes in work order forecasts regarding hour costs, item costs, and expenses, which have been updated in other modules in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="bcf69-143">Isso é feito para garantir que os preços de custo mais recentes sejam sempre usados nas previsões de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="bcf69-143">This is done to ensure that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="bcf69-144">Também é possível fazer atualizações semelhantes para [previsões do tipo de trabalho de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="bcf69-144">It is also possible to make similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="bcf69-145">Clique em **Gerenciamento de ativos** > **Periódico** > **Previsão** > **Atualizar previsão da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-145">Click **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="bcf69-146">Na caixa de diálogo suspensa **Atualizar previsão da ordem de serviço** é possível adicionar seleções sobre ordens de serviço ou trabalhos da ordem de serviço específicos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="bcf69-146">In the **Update work order forecast** drop-down dialog, you can add selections regarding specific work orders or work order jobs, if required.</span></span> <span data-ttu-id="bcf69-147">Clique em **Filtro** para fazer essas seleções.</span><span class="sxs-lookup"><span data-stu-id="bcf69-147">Click **Filter** to make those selections.</span></span>

3. <span data-ttu-id="bcf69-148">Se necessário, você pode configurar a atualização automática como trabalho em lotes na Guia Rápida **Executar em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="bcf69-148">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

4. <span data-ttu-id="bcf69-149">Clique em **OK** para iniciar a atualização da previsão.</span><span class="sxs-lookup"><span data-stu-id="bcf69-149">Click **OK** to start the forecast update.</span></span>


![Figura 2](media/07-work-orders.png)

