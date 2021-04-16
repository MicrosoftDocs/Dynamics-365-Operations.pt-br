---
title: Adicionar um canal a uma hierarquia organizacional
description: Este tópico descreve como adicionar um canal a uma hierarquia organizacional no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c7ff6d8ee7e526e45975cfa500b5e6d6079054dc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800678"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a><span data-ttu-id="32068-103">Adicionar um canal a uma hierarquia organizacional</span><span class="sxs-lookup"><span data-stu-id="32068-103">Add a channel to an organizational hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="32068-104">Este tópico descreve como adicionar um canal a uma hierarquia organizacional no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="32068-104">This topic describes how to add a channel to an organizational hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="32068-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="32068-105">Overview</span></span>

<span data-ttu-id="32068-106">Os canais precisam ser associados a uma ou mais hierarquias organizacionais.</span><span class="sxs-lookup"><span data-stu-id="32068-106">Channels need to be associated with one or more organizational hierarchies.</span></span> <span data-ttu-id="32068-107">Antes de criar canais, você precisa confirmar que suas hierarquias organizacionais foram configuradas.</span><span class="sxs-lookup"><span data-stu-id="32068-107">Before creating channels, you need to confirm that your organizational hierarchies have been set up.</span></span>  

<span data-ttu-id="32068-108">Consulte [Hierarquias organizacionais](channels-org-hierarchies.md) para obter mais detalhes sobre como criar hierarquias organizacionais.</span><span class="sxs-lookup"><span data-stu-id="32068-108">See [Organizational hierarchies](channels-org-hierarchies.md) for more details on how to create organizational hierarchies.</span></span>

## <a name="select-a-hierarchy"></a><span data-ttu-id="32068-109">Selecionar uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="32068-109">Select a hierarchy</span></span>

<span data-ttu-id="32068-110">Para selecionar uma hierarquia, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="32068-110">To select a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="32068-111">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de Canal \> Hierarquias da organização**.</span><span class="sxs-lookup"><span data-stu-id="32068-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="32068-112">Na lista, selecione a hierarquia da organização à qual você adicionará o canal.</span><span class="sxs-lookup"><span data-stu-id="32068-112">From the list, select the organization hierarchy that you'll be adding the channel to.</span></span>
1. <span data-ttu-id="32068-113">No painel de ação, selecione **Exibir** para ver detalhes de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="32068-113">On the action pane, select **View** to view hierarchy details.</span></span>

<span data-ttu-id="32068-114">A imagem a seguir mostra os detalhes da hierarquia organizacional selecionada.</span><span class="sxs-lookup"><span data-stu-id="32068-114">The following image shows organizational hierarchy details for the selected hierarchy.</span></span>

![Detalhes da hierarquia organizacional selecionada](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a><span data-ttu-id="32068-116">Adicionar um canal a um nó de hierarquia</span><span class="sxs-lookup"><span data-stu-id="32068-116">Add a channel to a hierachy node</span></span>

<span data-ttu-id="32068-117">Para adicionar um canal a um nó da hierarquia, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="32068-117">To add a channel to a hierachy node, follow these steps.</span></span>

1. <span data-ttu-id="32068-118">No painel de ação, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="32068-118">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="32068-119">Selecione o nó da hierarquia ao qual você deseja adicionar o canal e, na lista suspensa **Inserir**, selecione **Canal de Varejo**.</span><span class="sxs-lookup"><span data-stu-id="32068-119">Select the hierachy node you want the channel added to, then from the **Insert** drop-down list, select **Retail Channel**.</span></span> 
1. <span data-ttu-id="32068-120">Selecione o canal a ser adicionado e clique no botão **OK**.</span><span class="sxs-lookup"><span data-stu-id="32068-120">Select the channel to add, then select the **OK** button.</span></span>
1. <span data-ttu-id="32068-121">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="32068-121">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="32068-122">No painel de ação, selecione **Publicar** e especifique uma **Data de efetivação** no passado para que esta ação entre em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="32068-122">On the action pane, select **Publish** and provide an **Effective date** in the past to have this action go into effect immediately.</span></span>

<span data-ttu-id="32068-123">A imagem a seguir mostra como selecionar um canal a ser adicionado a um nó de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="32068-123">The following image shows how to select a channel to add to a hierarchy node.</span></span>

![Selecionar um canal para adicionar a um nó de hierarquia](media/channel-add-to-org-hierarchy-2.png)

<span data-ttu-id="32068-125">A imagem a seguir mostra uma hierarquia com vários canais adicionados.</span><span class="sxs-lookup"><span data-stu-id="32068-125">The following image shows a hierarchy with various channels added.</span></span>

![Uma hierarquia com vários canais adicionados](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="32068-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="32068-127">Additional resources</span></span>

[<span data-ttu-id="32068-128">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="32068-128">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="32068-129">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="32068-129">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="32068-130">Visão geral de organizações e hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="32068-130">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="32068-131">Planejar sua hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="32068-131">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="32068-132">Hierarquias da organização</span><span class="sxs-lookup"><span data-stu-id="32068-132">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="32068-133">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="32068-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="32068-134">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="32068-134">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]