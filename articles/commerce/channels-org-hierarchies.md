---
title: Configurar hierarquias da organização
description: Este tópico descreve como configurar hierarquias da organização no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b887616ef29396ba99ca0c7428ab89df01b3008c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997766"
---
# <a name="set-up-organization-hierarchies"></a><span data-ttu-id="a19fe-103">Configurar hierarquias da organização</span><span class="sxs-lookup"><span data-stu-id="a19fe-103">Set up organization hierarchies</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a19fe-104">Este tópico descreve como configurar hierarquias da organização no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a19fe-104">This topic describes how to set up organization hierarchies in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a19fe-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="a19fe-105">Overview</span></span>

<span data-ttu-id="a19fe-106">Antes de criar canais, você precisa se certificar de configurar as hierarquias da organização.</span><span class="sxs-lookup"><span data-stu-id="a19fe-106">Before creating channels, you'll want to ensure you have set up your organization hierarchies.</span></span>

<span data-ttu-id="a19fe-107">Você pode usar as hierarquias da organização para exibir e fazer relatórios sobre a empresa de várias perspectivas.</span><span class="sxs-lookup"><span data-stu-id="a19fe-107">You can use organization hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="a19fe-108">Por exemplo, você pode configurar uma hierarquia para relatórios de impostos, legais ou estatutários.</span><span class="sxs-lookup"><span data-stu-id="a19fe-108">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="a19fe-109">Você pode configurar outra hierarquia para criar relatórios sobre informações financeiras que não são necessárias legalmente, mas que são usadas para fins de relatórios internos.</span><span class="sxs-lookup"><span data-stu-id="a19fe-109">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span>

<span data-ttu-id="a19fe-110">Antes de criar uma hierarquia da organização, você deve criar organizações.</span><span class="sxs-lookup"><span data-stu-id="a19fe-110">Before you create an organization hierarchy, you must create organizations.</span></span> <span data-ttu-id="a19fe-111">Para obter mais informações, consulte [Criar entidades legais](channels-legal-entities.md) ou [Criar unidades operacionais](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="a19fe-111">For more information, see [Create legal entities](channels-legal-entities.md) or [Create operating units](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span></span>


<span data-ttu-id="a19fe-112">Para obter mais informações, consulte os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="a19fe-112">For more information, see the following topics.</span></span>
- [<span data-ttu-id="a19fe-113">Visão geral de organizações e hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="a19fe-113">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="a19fe-114">Planejar sua hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="a19fe-114">Plan your organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="a19fe-115">​Criar uma hierarquia da organização​</span><span class="sxs-lookup"><span data-stu-id="a19fe-115">Create an organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a><span data-ttu-id="a19fe-116">Criar uma hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="a19fe-116">Create an organizational hierarchy</span></span>

<span data-ttu-id="a19fe-117">Para criar uma hierarquia organizacional, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a19fe-117">To create an organizational hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="a19fe-118">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de Canal \> Hierarquias da organização**.</span><span class="sxs-lookup"><span data-stu-id="a19fe-118">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="a19fe-119">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a19fe-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a19fe-120">No campo **Nome**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="a19fe-120">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="a19fe-121">Na seção **Finalidade**, selecione **Atribuir finalidade**.</span><span class="sxs-lookup"><span data-stu-id="a19fe-121">In the **Purpose** section, select **Assign purpose**.</span></span>
1. <span data-ttu-id="a19fe-122">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="a19fe-122">In the list, find and select the desired record.</span></span> <span data-ttu-id="a19fe-123">Selecione uma finalidade para atribuir a hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="a19fe-123">Select a purpose to assign to your organization hierarchy.</span></span>
1. <span data-ttu-id="a19fe-124">Na seção **Hierarquias atribuídas**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a19fe-124">In the **Assigned hierarchies** section, select **Add**.</span></span>
1. <span data-ttu-id="a19fe-125">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a19fe-125">In the list, mark the selected row.</span></span> <span data-ttu-id="a19fe-126">Localizar a hierarquia que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="a19fe-126">Find the hierarchy you just created.</span></span>
1. <span data-ttu-id="a19fe-127">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a19fe-127">Select **OK**.</span></span>

<span data-ttu-id="a19fe-128">A imagem a seguir mostra um exemplo de hierarquia organizacional criada para um conjunto de lojas "Adventure Works" fictícias.</span><span class="sxs-lookup"><span data-stu-id="a19fe-128">The following image shows an example organizational hierarchy created for a fictitious "Adventure Works" set of stores.</span></span>

![Exemplo de hierarquias organizacional](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a><span data-ttu-id="a19fe-130">Adicionar organizações a uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="a19fe-130">Add organizations to a hierarchy</span></span>

<span data-ttu-id="a19fe-131">Para adicionar organizações a uma hierarquia, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a19fe-131">To add organizations to a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="a19fe-132">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="a19fe-132">In the list, find and select the desired record.</span></span> <span data-ttu-id="a19fe-133">Selecionar sua hierarquia.</span><span class="sxs-lookup"><span data-stu-id="a19fe-133">Select your hierarchy.</span></span>
1. <span data-ttu-id="a19fe-134">No painel de ação, selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="a19fe-134">On the action pane, select **View**.</span></span>
1. <span data-ttu-id="a19fe-135">Adicione organizações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="a19fe-135">Add organizations, as necessary.</span></span>
1. <span data-ttu-id="a19fe-136">Para adicionar uma organização, selecione **Editar** e, depois, **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="a19fe-136">To add an organization, select **Edit** and then select **Insert**.</span></span> <span data-ttu-id="a19fe-137">Quando terminar de fazer alterações, você pode salvar um rascunho e publicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="a19fe-137">When you are done making changes you can save a draft and publish the changes.</span></span>

<span data-ttu-id="a19fe-138">A imagem a seguir mostra uma entidade legal adicionada na raiz da hierarquia, com quatro centros de custo adicionados para os canais "Shopping", "Loja", "Online" e "Call Center".</span><span class="sxs-lookup"><span data-stu-id="a19fe-138">The following image shows a legal entity added at the hierarchy root with four cost centers added for "Mall", "Outlet", "Online" and "Call Center" channels.</span></span> <span data-ttu-id="a19fe-139">Vários canais online, de varejo e de call center podem ser adicionados a cada um deles.</span><span class="sxs-lookup"><span data-stu-id="a19fe-139">Various retail, call center and online channels can then be added to each.</span></span>

![Exemplo de designer de hierarquia](media/hierarchy-designer.png)

## <a name="additional-resources"></a><span data-ttu-id="a19fe-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a19fe-141">Additional resources</span></span>

[<span data-ttu-id="a19fe-142">Visão geral de organizações e hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="a19fe-142">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="a19fe-143">Planejar sua hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="a19fe-143">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="a19fe-144">Criar entidades legais</span><span class="sxs-lookup"><span data-stu-id="a19fe-144">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="a19fe-145">​Criar unidades operacionais</span><span class="sxs-lookup"><span data-stu-id="a19fe-145">Create operating units</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="a19fe-146">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="a19fe-146">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="a19fe-147">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="a19fe-147">Channel setup prerequisites</span></span>](channels-prerequisites.md)
