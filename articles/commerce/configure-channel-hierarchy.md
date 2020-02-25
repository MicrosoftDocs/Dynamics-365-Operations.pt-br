---
title: Configurar um canal para usar uma hierarquia de navegação de canal
description: Este tópico descreve como configurar um canal para usar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7b5041d35d310125c314ab2cb77d3cc40cdb7113
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002211"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a><span data-ttu-id="73965-103">Configurar um canal para usar uma hierarquia de navegação de canal</span><span class="sxs-lookup"><span data-stu-id="73965-103">Configure a channel to use a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="73965-104">Este tópico descreve como configurar um canal para usar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="73965-104">This topic describes how to configure a channel to use a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="73965-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="73965-105">Overview</span></span>

<span data-ttu-id="73965-106">As hierarquias de navegação de canal organizam os produtos em categorias para que os produtos possam ser procurados em um site de comércio eletrônico ou em pontos de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="73965-106">Channel navigation hierarchies organize products into categories so that the products can be browsed on an e-Commerce site or at points of sale (POS).</span></span> <span data-ttu-id="73965-107">Os canais de varejo e online devem ser configurados com hierarquias de navegação de canal.</span><span class="sxs-lookup"><span data-stu-id="73965-107">Retail and online channels must be configured with channel navigation hierarchies.</span></span>

## <a name="configure-the-channel"></a><span data-ttu-id="73965-108">Configurar o canal</span><span class="sxs-lookup"><span data-stu-id="73965-108">Configure the channel</span></span>

<span data-ttu-id="73965-109">Para configurar um canal para usar uma hierarquia de navegação de canal, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="73965-109">To configure a channel to use a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="73965-110">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.</span><span class="sxs-lookup"><span data-stu-id="73965-110">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="73965-111">Selecione o canal a configurar.</span><span class="sxs-lookup"><span data-stu-id="73965-111">Select the channel to configure.</span></span>
1. <span data-ttu-id="73965-112">No painel de ação, selecione **Definir metadados de atributo**.</span><span class="sxs-lookup"><span data-stu-id="73965-112">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="73965-113">Na lista suspensa **Hierarquia de categoria**, selecione a hierarquia de navegação de canal apropriada.</span><span class="sxs-lookup"><span data-stu-id="73965-113">In the **Category hierarchy** drop-down list, select the appropriate channel navigation hierarchy.</span></span>
1. <span data-ttu-id="73965-114">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73965-114">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="73965-115">Em **Grupo de atributos**, adicione os grupos de atributos que serão atributos globais de todos os nós.</span><span class="sxs-lookup"><span data-stu-id="73965-115">Under **Attribute group**, add any attribute groups that will be global attributes for all nodes.</span></span>

<span data-ttu-id="73965-116">A imagem a seguir mostra como configurar um canal para usar uma hierarquia de navegação de canal.</span><span class="sxs-lookup"><span data-stu-id="73965-116">The following image shows how to configure a channel to use a channel navigation hierarchy.</span></span>

![Exemplo de configuração de canal](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a><span data-ttu-id="73965-118">Definir metadados de atributo</span><span class="sxs-lookup"><span data-stu-id="73965-118">Set attribute metadata</span></span>

<span data-ttu-id="73965-119">Definir os metadados de atributo permitirá a configuração de atributos em cada nó.</span><span class="sxs-lookup"><span data-stu-id="73965-119">Setting the attribute metadata will allow configuration of attributes on each node.</span></span>

<span data-ttu-id="73965-120">Para definir metadados de atributo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="73965-120">To set attribute metadata, follow these steps.</span></span>

1. <span data-ttu-id="73965-121">No painel de ação, selecione **Definir metadados de atributo**.</span><span class="sxs-lookup"><span data-stu-id="73965-121">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="73965-122">Para cada nó, selecione **Atributos de produto do canal**.</span><span class="sxs-lookup"><span data-stu-id="73965-122">For each node select **Channel product attributes**.</span></span>
1. <span data-ttu-id="73965-123">Defina **Mostrar atributo no canal** como **Sim** e **Pode ser refinado** como **Sim** para habilitar refinadores nesse canal.</span><span class="sxs-lookup"><span data-stu-id="73965-123">Set **Show attribute on channel** to **Yes** and **Can be refined** to **Yes**, to enable refiners on that channel.</span></span>
1. <span data-ttu-id="73965-124">Depois de configurar cada nó conforme desejado, no **Painel de ação**, selecione o botão **Salvar** para salvar.</span><span class="sxs-lookup"><span data-stu-id="73965-124">After configuring each node as desired, on the **Action pane**, select the **Save** button to save.</span></span>
1. <span data-ttu-id="73965-125">Selecione o **X** no canto superior direito para sair desta tela e voltar à página **Categorias do canal e atributos de produto**.</span><span class="sxs-lookup"><span data-stu-id="73965-125">Select the **X** in the top right corner to exit this screen back to the **Channel categories and product attributes** page.</span></span>

<span data-ttu-id="73965-126">A imagem a seguir mostra um exemplo de conjunto de atributos de produto de canal configurados em um nó de categoria de canal.</span><span class="sxs-lookup"><span data-stu-id="73965-126">The following image shows an example set of channel product attributes configured on a channel category node.</span></span>

![Atributos de canal em um nó de categoria de canal](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a><span data-ttu-id="73965-128">Publicar alterações</span><span class="sxs-lookup"><span data-stu-id="73965-128">Publish changes</span></span>

<span data-ttu-id="73965-129">Para que as alterações entrem em vigor, você precisará publicá-las.</span><span class="sxs-lookup"><span data-stu-id="73965-129">For changes to take effect, you will need to publish the changes.</span></span>

<span data-ttu-id="73965-130">Para publicar alterações, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="73965-130">To publish changes, follow these steps.</span></span>

1. <span data-ttu-id="73965-131">No painel de ação, selecione **Publicar atualizações de canal**.</span><span class="sxs-lookup"><span data-stu-id="73965-131">On the action pane, select **Publish channel updates**.</span></span>
1. <span data-ttu-id="73965-132">No painel **Publicar atualizações de canal**, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="73965-132">In the **Publish channel updates** pane, select **OK**.</span></span>

<span data-ttu-id="73965-133">A imagem a seguir mostra como publicar atualizações de canal.</span><span class="sxs-lookup"><span data-stu-id="73965-133">The following image shows how to publish channel updates.</span></span>

![Publicar atualizações de canal](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="73965-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="73965-135">Additional resources</span></span>

[<span data-ttu-id="73965-136">Criar uma hierarquia de navegação de canal</span><span class="sxs-lookup"><span data-stu-id="73965-136">Create a channel navigation hierarchy</span></span>](create-channel-hierarchy.md)


