---
title: Integrar gerenciamento de ativos com ativos fixos
description: Este tópico explica como integrar os módulos de gerenciamento de ativos e ativos fixos, de forma que você possa vincular ativos fixos com ativos de manutenção.
author: kamaybac
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: a45bf1f62cdcc8abed2ec157a223e7f3fddec7ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809845"
---
# <a name="integrate-asset-management-with-fixed-assets"></a><span data-ttu-id="c7606-103">Integrar gerenciamento de ativos com ativos fixos</span><span class="sxs-lookup"><span data-stu-id="c7606-103">Integrate asset management with fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c7606-104">Ao integrar os módulos de **gerenciamento de ativos** e **ativos fixos**, você pode vincular ativos fixos com ativos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="c7606-104">By integrating the **Asset management** and **Fixed assets** modules, you can link fixed assets with maintenance assets.</span></span> <span data-ttu-id="c7606-105">Usuários de ativos fixos podem criar um ativo de manutenção a partir de um ativo fixo novo ou existente, e os usuários de gerenciamento de ativos podem associar um ativo de manutenção a um ativo fixo existente.</span><span class="sxs-lookup"><span data-stu-id="c7606-105">Fixed assets users can then create a maintenance asset from a new or existing fixed asset, and Asset management users can associate a maintenance asset with an existing fixed asset.</span></span> <span data-ttu-id="c7606-106">Esse recurso também torna mais fácil para os usuários de ativos fixos exibirem os custos lançados a partir de ordens de trabalho para ativos de manutenção relacionados.</span><span class="sxs-lookup"><span data-stu-id="c7606-106">This feature also makes it easy for Fixed assets users to view the costs that were posted from work orders for related maintenance assets.</span></span>

> [!NOTE]
> <span data-ttu-id="c7606-107">Neste tópico, *ativos de manutenção* refere-se a ativos do módulo **Gerenciamento de ativos** e *ativos fixos* refere-se aos ativos do módulo **Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="c7606-107">In this topic, *maintenance assets* refer to assets from the **Asset management** module, and *fixed assets* refer to assets from the **Fixed assets** module.</span></span>

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a><span data-ttu-id="c7606-108">Definir um local padrão para novos ativos de manutenção que são criados a partir de ativos fixos (opcional)</span><span class="sxs-lookup"><span data-stu-id="c7606-108">Set a default location for new maintenance assets that are created from fixed assets (optional)</span></span>

<span data-ttu-id="c7606-109">Essa configuração opcional permite que você defina um local funcional padrão para nossos ativos de manutenção que são criados de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="c7606-109">This optional configuration lets you set a default functional location for new maintenance assets that are created from fixed assets.</span></span> <span data-ttu-id="c7606-110">Normalmente, você completa essa configuração apenas uma vez, se você concluí-la.</span><span class="sxs-lookup"><span data-stu-id="c7606-110">You typically complete this configuration this just one time, if you complete it at all.</span></span>

<span data-ttu-id="c7606-111">Para concluir a configuração, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="c7606-111">To complete the configuration, follow these steps.</span></span>

1. <span data-ttu-id="c7606-112">Vá para **Gerenciamento de ativo \> Configuração \> Parâmetros de gerenciamento de ativo**.</span><span class="sxs-lookup"><span data-stu-id="c7606-112">Go to **Asset management \> Setup \> Asset management parameters**.</span></span>
1. <span data-ttu-id="c7606-113">Na guia **Ativos fixos**, no campo **Local funcionar**, selecione o local padrão.</span><span class="sxs-lookup"><span data-stu-id="c7606-113">On the **Fixed assets** tab, in the **Functional location** field, select the default location.</span></span>
1. <span data-ttu-id="c7606-114">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7606-114">On the Action Pane, select **Save**.</span></span>

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a><span data-ttu-id="c7606-115">Trabalhar com ativos fixos e de manutenção integrados</span><span class="sxs-lookup"><span data-stu-id="c7606-115">Work with integrated maintenance assets and fixed assets</span></span>

<span data-ttu-id="c7606-116">Esta seção fornece um conjunto de procedimentos que mostram várias maneiras que você pode trabalhar com os recursos de gerenciamento de ativos integrados e ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="c7606-116">This section provides a collection of procedures that show various ways that you can work with the integrated Asset management and Fixed assets features.</span></span>

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a><span data-ttu-id="c7606-117">Associar um ativo de manutenção existente a um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="c7606-117">Associate an existing maintenance asset with a fixed asset</span></span>

<span data-ttu-id="c7606-118">Para associar um ativo de manutenção existente a um ativo fixo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c7606-118">To associate an existing maintenance asset with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7606-119">Vá para **Gerenciamento de ativos \> Ativos \> Todos os ativos** (ou **Ativos ativos**).</span><span class="sxs-lookup"><span data-stu-id="c7606-119">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="c7606-120">Selecionar um ativo.</span><span class="sxs-lookup"><span data-stu-id="c7606-120">Select an asset.</span></span>
1. <span data-ttu-id="c7606-121">Na Guia Rápida **Ativo fixo**, no campo **Número do ativo fixo**, selecione um ativo fixo existente.</span><span class="sxs-lookup"><span data-stu-id="c7606-121">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select an existing fixed asset.</span></span>
1. <span data-ttu-id="c7606-122">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7606-122">On the Action Pane, select **Save**.</span></span>

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a><span data-ttu-id="c7606-123">Exibir o ativo fixo associado a um ativo de manutenção selecionado</span><span class="sxs-lookup"><span data-stu-id="c7606-123">View the fixed asset that is associated with a selected maintenance asset</span></span>

<span data-ttu-id="c7606-124">Para exibir o ativo fixo associado a um ativo de manutenção selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c7606-124">To view the fixed asset that is associated with a selected maintenance asset, follow these steps.</span></span>

1. <span data-ttu-id="c7606-125">Vá para **Gerenciamento de ativos \> Ativos \> Todos os ativos** (ou **Ativos ativos**).</span><span class="sxs-lookup"><span data-stu-id="c7606-125">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="c7606-126">Selecionar um ativo.</span><span class="sxs-lookup"><span data-stu-id="c7606-126">Select an asset.</span></span>
1. <span data-ttu-id="c7606-127">Na Guia Rápida **Ativo fixo**, no campo **Número do ativo fixo**, selecione o link.</span><span class="sxs-lookup"><span data-stu-id="c7606-127">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select the link.</span></span>

    <span data-ttu-id="c7606-128">A página **Ativos fixos** do ativo selecionado é aberta.</span><span class="sxs-lookup"><span data-stu-id="c7606-128">The **Fixed assets** page for the selected asset is opened.</span></span> <span data-ttu-id="c7606-129">(Normalmente, essa página é localizada em **Ativos fixos \> Ativos fixos \> Ativos fixos**.)</span><span class="sxs-lookup"><span data-stu-id="c7606-129">(Typically, this page is found at **Fixed assets \> Fixed assets \> Fixed assets**.)</span></span>

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a><span data-ttu-id="c7606-130">Exibir o ativo de manutenção associado a um ativo fixo selecionado</span><span class="sxs-lookup"><span data-stu-id="c7606-130">View the maintenance asset that is associated with a selected fixed asset</span></span>

<span data-ttu-id="c7606-131">Para exibir o ativo de manutenção associado a um ativo fixo selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c7606-131">To view the maintenance asset that is associated with a selected fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7606-132">Vá para **Ativos fixos \> Ativos fixos \> Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="c7606-132">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="c7606-133">Selecionar um ativo.</span><span class="sxs-lookup"><span data-stu-id="c7606-133">Select an asset.</span></span>
1. <span data-ttu-id="c7606-134">No Painel de Ações, na guia **Gerenciamento de ativos**, no grupo **Exibir**, selecione **Ativo de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="c7606-134">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance asset**.</span></span>

    <span data-ttu-id="c7606-135">A página **Ativo de manutenção** do ativo associado ao ativo fixo selecionado é aberta.</span><span class="sxs-lookup"><span data-stu-id="c7606-135">The **Maintenance asset** page for the asset that is associated with the selected fixed asset is opened.</span></span> <span data-ttu-id="c7606-136">(Normalmente, essa página é encontrada em **Gerenciamento de ativo \> Ativos \> Todos os ativos**.)</span><span class="sxs-lookup"><span data-stu-id="c7606-136">(Typically, this page is found at **Asset management \> Assets \> All assets**.)</span></span>

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a><span data-ttu-id="c7606-137">Exibir os custos de manutenção associados a um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="c7606-137">View maintenance costs that are associated with a fixed asset</span></span>

<span data-ttu-id="c7606-138">As ordens de trabalho de gerenciamento de ativos podem ser lançadas para ativos de manutenção, e cada uma dessas ordens de trabalho normalmente tem um custo.</span><span class="sxs-lookup"><span data-stu-id="c7606-138">Asset management work orders can be posted for maintenance assets, and each of those work orders typically has a cost.</span></span> <span data-ttu-id="c7606-139">Quando um ativo fixo é associado a um ativo de manutenção, você pode ir diretamente do ativo fixo para exibir os custos relacionados.</span><span class="sxs-lookup"><span data-stu-id="c7606-139">When a fixed asset is associated with a maintenance asset, you can go directly from the fixed asset to view the related costs.</span></span>

<span data-ttu-id="c7606-140">Para exibir os custos de manutenção que são associados com um ativo fixo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c7606-140">To view the maintenance costs that are associated with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7606-141">Vá para **Ativos fixos \> Ativos fixos \> Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="c7606-141">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="c7606-142">Selecionar um ativo.</span><span class="sxs-lookup"><span data-stu-id="c7606-142">Select an asset.</span></span>
1. <span data-ttu-id="c7606-143">No Painel de Ações, na guia **Gerenciamento de ativos**, no grupo **Exibir**, selecione **Custo de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="c7606-143">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance cost**.</span></span>

    <span data-ttu-id="c7606-144">A página **Custo de manutenção** é aberta e mostra os custos relacionados.</span><span class="sxs-lookup"><span data-stu-id="c7606-144">The **Maintenance cost** page is opened and shows the related costs.</span></span>

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a><span data-ttu-id="c7606-145">Criar um novo ativo de manutenção para um ativo fixo existente</span><span class="sxs-lookup"><span data-stu-id="c7606-145">Create a new maintenance asset for an existing fixed asset</span></span>

<span data-ttu-id="c7606-146">Para criar um novo ativo de manutenção para um ativo fixo existente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c7606-146">To create a new maintenance asset for an existing fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7606-147">Vá para **Ativos fixos \> Ativos fixos \> Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="c7606-147">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="c7606-148">Selecionar um ativo.</span><span class="sxs-lookup"><span data-stu-id="c7606-148">Select an asset.</span></span>
1. <span data-ttu-id="c7606-149">No Painel de Ações, na guia **Gerenciamento de ativos**, no grupo **Novo**, selecione **Criar ativo de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="c7606-149">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span> <span data-ttu-id="c7606-150">(Se esta opção não estiver disponível, um ativo de manutenção talvez já esteja associado ao ativo fixo selecionado.)</span><span class="sxs-lookup"><span data-stu-id="c7606-150">(If this option is unavailable, a maintenance asset might already be associated with the selected fixed asset.)</span></span>
1. <span data-ttu-id="c7606-151">Conclua a criação do ativo, conforme descrito em [Criar um ativo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="c7606-151">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a><span data-ttu-id="c7606-152">Criar um novo ativo fixo e adicionar um novo ativo de manutenção para ele</span><span class="sxs-lookup"><span data-stu-id="c7606-152">Create a new fixed asset and add a new maintenance asset for it</span></span>

<span data-ttu-id="c7606-153">Para criar um novo ativo fixo e adicionar um novo ativo de manutenção para ele, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c7606-153">To create a new fixed asset and add a new maintenance asset for it, follow these steps.</span></span>

1. <span data-ttu-id="c7606-154">Vá para **Ativos fixos \> Ativos fixos \> Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="c7606-154">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="c7606-155">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c7606-155">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c7606-156">Conclua a criação do ativo fixo, conforme descrito em [Criar um ativo fixo](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="c7606-156">Finish creating the fixed asset as described in [Create a fixed asset](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span></span>
1. <span data-ttu-id="c7606-157">No Painel de Ações, na guia **Gerenciamento de ativos**, no grupo **Novo**, selecione **Criar ativo de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="c7606-157">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span>
1. <span data-ttu-id="c7606-158">Conclua a criação do ativo, conforme descrito em [Criar um ativo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="c7606-158">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="remove-the-association-between-two-assets"></a><span data-ttu-id="c7606-159">Remover a associação entre dois ativos</span><span class="sxs-lookup"><span data-stu-id="c7606-159">Remove the association between two assets</span></span>

<span data-ttu-id="c7606-160">Em alguns casos, talvez seja necessário desassociar um ativo de manutenção do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="c7606-160">In some cases, you might have to disassociate a maintenance asset from its fixed asset.</span></span> <span data-ttu-id="c7606-161">Por exemplo, se desejar [Criar um novo ativo de manutenção](#new-maintenance-from-fixed) a partir de um ativo fixo, você deverá primeiro remover qualquer associação existente.</span><span class="sxs-lookup"><span data-stu-id="c7606-161">For example, if you want to [create a new maintenance asset](#new-maintenance-from-fixed) from a fixed asset, you must first remove any existing association.</span></span>

<span data-ttu-id="c7606-162">Para remover uma associação existente entre um ativo de manutenção e um ativo fixo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c7606-162">To remove an existing association between a maintenance asset and a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7606-163">Vá para **Gerenciamento de ativos \> Ativos \> Todos os ativos** (ou **Ativos ativos**).</span><span class="sxs-lookup"><span data-stu-id="c7606-163">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="c7606-164">Localize e abra o ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="c7606-164">Find and open the fixed asset.</span></span>
1. <span data-ttu-id="c7606-165">Na Guia Rápida **Ativos fixos**, limpe o valor do campo **Local funcional**.</span><span class="sxs-lookup"><span data-stu-id="c7606-165">On the **Fixed asset** FastTab, clear the value from the **Functional location** field.</span></span>
1. <span data-ttu-id="c7606-166">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7606-166">On the Action Pane, select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]