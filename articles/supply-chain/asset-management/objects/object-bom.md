---
title: BOMs de Ativos
description: Este tópico descreve listas de materiais (BOMs) de ativos no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetStandardSparePartsItemGroup, EntAssetObjectBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: baaf516eb386c3cf63d72bf31800b8731121fe26
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019502"
---
# <a name="asset-boms"></a><span data-ttu-id="aedb8-103">BOMs de Ativos</span><span class="sxs-lookup"><span data-stu-id="aedb8-103">Asset BOMs</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="aedb8-104">Este tópico descreve listas de materiais (BOMs) de ativos no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="aedb8-104">This topic describes asset bills of materials (BOMs) in Asset Management.</span></span> <span data-ttu-id="aedb8-105">A **BOM de ativos** mostra uma lista de todos os itens (partes sobressalentes e outros itens) usados em um ativo durante toda sua vida útil.</span><span class="sxs-lookup"><span data-stu-id="aedb8-105">The **Asset BOM** page shows a list of all items (spare parts and other items) that are used on an asset during its whole lifetime.</span></span> <span data-ttu-id="aedb8-106">Quando você criar um novo ativo, considere a configuração de uma BOM de ativos como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="aedb8-106">When you create a new asset, you should consider setting up an asset BOM as a part of the setup procedure.</span></span> <span data-ttu-id="aedb8-107">Assim, você pode controlar o histórico de itens do ativo desde a data de criação.</span><span class="sxs-lookup"><span data-stu-id="aedb8-107">In this way, you can track item history for the asset from the creation date.</span></span>

<span data-ttu-id="aedb8-108">Depois de concluir um trabalho de manutenção, e depois que o consumo de item tiver sido registrado em uma ordem de serviço, você poderá acompanhar o consumo de peças sobressalentes e de outros itens usados no ativo.</span><span class="sxs-lookup"><span data-stu-id="aedb8-108">After you've completed a maintenance job, and item consumption has been registered on a work order, you can track consumption of spare parts and other items that are used on the asset.</span></span> <span data-ttu-id="aedb8-109">Essa funcionalidade permite manter um registro completo de consumo de itens para todos os ativos.</span><span class="sxs-lookup"><span data-stu-id="aedb8-109">This functionality lets you keep a complete item consumption record for all your assets.</span></span> <span data-ttu-id="aedb8-110">Por exemplo, você pode usar o registro para monitorar se uma peça sobressalente específica é substituída com frequência, ou para controlar as partes sobressalentes ou outros itens usados no momento em um ativo.</span><span class="sxs-lookup"><span data-stu-id="aedb8-110">For example, you can use the record to monitor whether a specific spare part is often replaced, or to keep track of the spare parts or other items that are currently used on an asset.</span></span>

> [!NOTE]
> <span data-ttu-id="aedb8-111">Em uma ordem de serviço, o consumo de itens pode incluir peças sobressalentes e outros itens adicionais, como lubrificantes, parafusos e gaxetas.</span><span class="sxs-lookup"><span data-stu-id="aedb8-111">On a work order, item consumption might include both spare parts and other, additional items, such as lubricants, bolts, and gaskets.</span></span>

<span data-ttu-id="aedb8-112">Uma BOM de ativos pode ser automaticamente atualizada com base na configuração do Asset Management.</span><span class="sxs-lookup"><span data-stu-id="aedb8-112">An asset BOM can be automatically updated based on the setup in Asset Management.</span></span> <span data-ttu-id="aedb8-113">Se um estado de ciclo de vida de ordem de serviço tiver sido criado para lidar com ordens de serviço encerradas ou concluídas, e se a opção **Atualizar BOM de ativos** para esse estado de ciclo de vida de ordem de serviço estiver definido como **Sim** na página **Estados de ciclo de vida de ordem de serviço**, todos os itens usados na ordem de serviço serão automaticamente atualizados na página **BOM de ativos** quando a ordem de serviço for atualizada para esse estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="aedb8-113">If a work order lifecycle state has been created to handle finished or completed work orders, and if the **Update asset BOM** option for that work order lifecycle state is set to **Yes** on the **Work order lifecycle states** page, all items that are used on the work order will be automatically updated on the **Asset BOM** page when the work order is updated to that lifecycle state.</span></span> 


<span data-ttu-id="aedb8-114">Você também pode atualizar manualmente uma BOM de ativos criando novas linhas de item na página **BOM de ativos**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-114">You can also manually update an asset BOM by creating new item lines on the **Asset BOM** page.</span></span>

<span data-ttu-id="aedb8-115">Na página **BOM de ativos**, você pode rastrear o histórico de peças sobressalentes para ativos depois que o consumo de itens é registrado em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="aedb8-115">On the **Asset BOM** page, you can track spare parts history for assets after item consumption is registered on a work order.</span></span> <span data-ttu-id="aedb8-116">Para usar essa funcionalidade, selecione os grupos de itens que devem ser usados para o registro de peças sobressalentes na página **Grupos de itens de peças sobressalentes**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-116">To use this functionality, you must select the item groups that should be used for spare parts registration on the **Spare parts item groups** page.</span></span>

<span data-ttu-id="aedb8-117">Para usar a funcionalidade BOM de ativos, primeiro você deverá configurar os grupos de itens de peças sobressalentes.</span><span class="sxs-lookup"><span data-stu-id="aedb8-117">To use asset BOM functionality, you must first set up the required spare parts items groups.</span></span> <span data-ttu-id="aedb8-118">Depois, se desejar que a BOM de ativos seja automaticamente atualizada quando uma ordem de serviço for concluída, você poderá configurar um estado de ciclo de vida de ordem de serviço para lidar essa atualização.</span><span class="sxs-lookup"><span data-stu-id="aedb8-118">Then, if you want the asset BOM to be automatically updated when a work order is completed, you can set up a work order lifecycle state to handle that update.</span></span> 


## <a name="set-up-spare-parts-item-groups"></a><span data-ttu-id="aedb8-119">Configurar grupos de itens de peças sobressalentes</span><span class="sxs-lookup"><span data-stu-id="aedb8-119">Set up spare parts item groups</span></span>

<span data-ttu-id="aedb8-120">A configuração de histórico de peças sobressalentes se baseia em grupos de itens criados no módulo **Gerenciamento de estoque e depósito**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-120">The setup of spare parts history is based on item groups that are created in the **Inventory and warehouse management** module.</span></span> <span data-ttu-id="aedb8-121">No Asset Management, você configura grupos de itens para poder acompanhar o histórico de peças sobressalentes dos itens nos grupos de itens selecionados.</span><span class="sxs-lookup"><span data-stu-id="aedb8-121">In Asset Management, you set up item groups so that you can track spare parts history for the items in the selected item groups.</span></span>

1. <span data-ttu-id="aedb8-122">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativo** \> **Grupos de itens de peças sobressalentes**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-122">Select **Asset management** \> **Setup** \> **Asset** \> **Spare parts item groups**.</span></span>
2. <span data-ttu-id="aedb8-123">Selecione **Novo** para configurar um grupo de itens.</span><span class="sxs-lookup"><span data-stu-id="aedb8-123">Select **New** to set up an item group.</span></span>
3. <span data-ttu-id="aedb8-124">No campo **Grupo de itens**, selecione o grupo.</span><span class="sxs-lookup"><span data-stu-id="aedb8-124">In the **Item group** field, select the group.</span></span> <span data-ttu-id="aedb8-125">O nome do grupo é inserido automaticamente no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-125">The name of the group is automatically entered in the **Name** field.</span></span>

## <a name="view-and-update-asset-boms"></a><span data-ttu-id="aedb8-126">Exibir e atualizar BOMs de ativos</span><span class="sxs-lookup"><span data-stu-id="aedb8-126">View and update asset BOMs</span></span>

<span data-ttu-id="aedb8-127">Depois de lançar o consumo de itens em uma ordem de serviço, você poderá exibir o consumo de item registrado na página **BOM de ativos**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-127">After you post item consumption on a work order, you can view the registered item consumption on the **Asset BOM** page.</span></span>

1. <span data-ttu-id="aedb8-128">Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Ativos ativos**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-128">Select **Asset management** \> **Common** \> **Assets** \> **Active assets**.</span></span> <span data-ttu-id="aedb8-129">Selecione o ativo da lista e depois selecione **BOM de ativos**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-129">Select the asset in the list, and then select **Asset BOM**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aedb8-130">Para exibir todos os registros do consumo de item em todos os ativos, selecione **Gerenciamento de ativos** \> **Consultas** \> **Ativos** \> **BOM de ativos**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-130">To view all item consumption registrations on all assets, select **Asset management** \> **Inquiries** \> **Assets** \> **Asset BOM**.</span></span>

2. <span data-ttu-id="aedb8-131">Selecione **Atualizar BOM de ativos**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-131">Select **Update asset BOM**.</span></span> <span data-ttu-id="aedb8-132">Você pode adicionar ativos, tipos de ativo e recursos à atualização como for necessário ao escolher **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-132">You can add assets, asset types, and resources to the update as you require by selecting **Select**.</span></span> <span data-ttu-id="aedb8-133">Selecione **OK** para iniciar a atualização.</span><span class="sxs-lookup"><span data-stu-id="aedb8-133">Select **OK** to start the update.</span></span> <span data-ttu-id="aedb8-134">Você também pode configurar a função Atualizar como um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="aedb8-134">You can also set up the Update function as a batch job.</span></span>
3. <span data-ttu-id="aedb8-135">Se quiser ver mais informações relacionadas aos itens, adicione dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="aedb8-135">If you want to see more information that is related to the items, you can add inventory dimensions.</span></span> <span data-ttu-id="aedb8-136">Selecione **Estoque** \> **Exibição de dimensões** e marque as caixas de seleção para as dimensões que você deseja ver.</span><span class="sxs-lookup"><span data-stu-id="aedb8-136">Select **Inventory** \> **Dimensions display**, and then select the check boxes for the dimensions that you want to see.</span></span> <span data-ttu-id="aedb8-137">Para manter essa configuração para todos os ativos na página **BOM de ativos**, defina a opção **Salvar configuração** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-137">To keep this setup for all assets on the **Asset BOM** page, set the **Save setup** option to **Yes**.</span></span>
4. <span data-ttu-id="aedb8-138">Para obter uma visão geral de onde no Asset Management o item na linha selecionada é usado, em relação a ativos, padrões de tipo de trabalho, partes sobressalentes e ordens de serviço, selecione **Item onde usado**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-138">To get an overview of where in Asset Management the item on the selected line is used, in relation to assets, job type defaults, spare parts, and work orders, select **Item where used**.</span></span> 
5. <span data-ttu-id="aedb8-139">Para ver apenas as linhas de item ativas, selecione **Exibir** \> **Atual**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-139">If you want to see only active item lines, select **View** \> **Current**.</span></span> <span data-ttu-id="aedb8-140">Para ver todas as linhas de item, incluindo as linhas onde a data de vencimento é anterior à data atual, selecione **Exibir** \> **Tudo**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-140">To see all item lines, including lines where the expiration date is earlier than the current date, select **View** \> **All**.</span></span>

> [!NOTE]
> <span data-ttu-id="aedb8-141">Quando você tiver concluído uma ordem de serviço, se alguns itens ou peças sobressalentes relacionados ao ativo tiverem expirado ou tiverem sido substituídos por outros itens ou peças sobressalentes, recomendamos que você atualize a BOM de ativos de forma correspondente.</span><span class="sxs-lookup"><span data-stu-id="aedb8-141">When you've completed a work order, if some items or spare parts that are related to the related asset have expired or have been replaced by other items or spare parts, we recommend that you update the asset BOM accordingly.</span></span>

## <a name="create-a-new-item-line-in-an-asset-bom"></a><span data-ttu-id="aedb8-142">Criar uma nova linha de item em uma BOM de ativos</span><span class="sxs-lookup"><span data-stu-id="aedb8-142">Create a new item line in an asset BOM</span></span>

<span data-ttu-id="aedb8-143">Você pode as linhas de item para ativos manualmente.</span><span class="sxs-lookup"><span data-stu-id="aedb8-143">You can manually create item lines for assets.</span></span>

1. <span data-ttu-id="aedb8-144">Na página **BOM de ativos**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-144">On the **Asset BOM** page, select **New**.</span></span>
2. <span data-ttu-id="aedb8-145">No campo **Ativo**, selecione o ativo para o qual será adicionada uma linha de item.</span><span class="sxs-lookup"><span data-stu-id="aedb8-145">In the **Asset** field, select the asset to add an item line for.</span></span>
3. <span data-ttu-id="aedb8-146">No campo **Número da linha**, insira um número de linha sequencial.</span><span class="sxs-lookup"><span data-stu-id="aedb8-146">In the **Line number** field, enter a sequential line number.</span></span>
4. <span data-ttu-id="aedb8-147">No campo **Efetivação**, insira uma data inicial para o item.</span><span class="sxs-lookup"><span data-stu-id="aedb8-147">In the **Effective** field, enter a start date for the item.</span></span>
5. <span data-ttu-id="aedb8-148">Se item tiver um vencimento, no campo **Vencimento**, insira uma data de término.</span><span class="sxs-lookup"><span data-stu-id="aedb8-148">If the item will expire, in the **Expiration** field, enter an end date.</span></span>
6. <span data-ttu-id="aedb8-149">No campo **Nº do item**, selecione o item.</span><span class="sxs-lookup"><span data-stu-id="aedb8-149">In the **Item number** field, select the item.</span></span> <span data-ttu-id="aedb8-150">O nome é inserido automaticamente no campo **Nome do produto**.</span><span class="sxs-lookup"><span data-stu-id="aedb8-150">The name is automatically entered in the **Product name** field.</span></span>
7. <span data-ttu-id="aedb8-151">No campo **Quantidade**, insira a quantidade usada.</span><span class="sxs-lookup"><span data-stu-id="aedb8-151">In the **Quantity** field, enter the quantity that is used.</span></span> <span data-ttu-id="aedb8-152">O campo **Unidade** será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="aedb8-152">The **Unit** field is automatically updated.</span></span>
