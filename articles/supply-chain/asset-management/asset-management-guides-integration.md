---
title: Integrar Dynamics 365 Supply Chain Management (Gerenciamento de ativos) com Dynamics 365 Guides
description: Este tópico explica como integrar o módulo de gerenciamento de ativos no Microsoft Dynamics 365 Supply Chain Management com Dynamics 365 Guides para aproveitar guias de realidade combinada nos fluxos de trabalho de serviço e manutenção diários.
author: kamaybac
manager: tfehr
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: e3e9e74397faec12f6eecff1f562fd9d731ac5e2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230143"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a><span data-ttu-id="b3ed7-103">Integrar Dynamics 365 Supply Chain Management (Gerenciamento de ativos) com Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="b3ed7-103">Integrate Dynamics 365 Supply Chain Management (Asset management) with Dynamics 365 Guides</span></span>

<span data-ttu-id="b3ed7-104">Você pode integrar o módulo **Gerenciamento de ativos** no Microsoft Dynamics 365 Supply Chain Management com Dynamics 365 Guides para aproveitar guias de realidade combinada nos fluxos de trabalho de serviço e manutenção diários.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-104">You can integrate the **Asset management** module in Microsoft Dynamics 365 Supply Chain Management with Dynamics 365 Guides to take advantage of mixed-reality guides in your day-to-day service and maintenance workflows.</span></span> <span data-ttu-id="b3ed7-105">Se uma guia estiver associada a uma ordem de trabalho de gerenciamento de ativos, um trabalhador que abre a lista de verificação de manutenção da ordem de trabalho no aplicativo móvel do Supply Chain Management (Dynamics 365) verá que um guia está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-105">If a guide is associated with an Asset Management work order, a worker who opens the work order's maintenance checklist in the Supply Chain Management (Dynamics 365) mobile app sees that a guide is available.</span></span> <span data-ttu-id="b3ed7-106">Em seguida, o trabalhador pode encontrar e abrir o guia no aplicativo do Dynamics 365 Guides HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-106">The worker can then find and open the guide in the Dynamics 365 Guides HoloLens app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3ed7-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b3ed7-107">Prerequisites</span></span>

<span data-ttu-id="b3ed7-108">Para poder anexar guias a ordens de trabalho de gerenciamento de ativos, você deve executar estes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="b3ed7-108">Before you can attach guides to Asset management work orders, you must complete these prerequisites:</span></span>

- <span data-ttu-id="b3ed7-109">[Configurar o Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) versão 10.0.9 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-109">[Set up Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 or later.</span></span>
- <span data-ttu-id="b3ed7-110">[Ative a gravação dupla para aplicativos de Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="b3ed7-110">[Turn on dual-write for Supply Chain Management apps](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span></span>
- <span data-ttu-id="b3ed7-111">[Ative a versão de pré-lançamento](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) para o recurso **MRGuidesFeature**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-111">[Turn on flight](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) for the **MRGuidesFeature** feature.</span></span> <span data-ttu-id="b3ed7-112">(Para ambientes de produção, você deve primeiro enviar um tíquete de suporte para que seu locatário seja adicionado ao grupo de versão de pré-lançamento.)</span><span class="sxs-lookup"><span data-stu-id="b3ed7-112">(For production environments, you must first submit a support ticket to have your tenant added to the flighting group.)</span></span>
- <span data-ttu-id="b3ed7-113">[Ative as seguintes chaves de configuração](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) na página **Configuração de licenças**:</span><span class="sxs-lookup"><span data-stu-id="b3ed7-113">[Turn on the following configuration keys](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) on the **License configuration** page:</span></span>

    - <span data-ttu-id="b3ed7-114">Gerenciamento de ativos \> Realidade combinada de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="b3ed7-114">Asset management \> Asset management mixed reality</span></span>
    - <span data-ttu-id="b3ed7-115">Realidade combinada \> Guia de realidade combinada</span><span class="sxs-lookup"><span data-stu-id="b3ed7-115">Mixed reality \> Mixed reality guide</span></span>

- <span data-ttu-id="b3ed7-116">[Configurar Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) versão 200.0.0.96 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-116">[Set up Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 or later.</span></span>

## <a name="use-dynamics-365-guides-with-asset-management"></a><span data-ttu-id="b3ed7-117">Use Dynamics 365 Guides com Gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="b3ed7-117">Use Dynamics 365 Guides with Asset management</span></span>

<span data-ttu-id="b3ed7-118">Para associar uma guia, use a linha da lista de verificação de manutenção no gerenciamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-118">To associate a guide, you use a maintenance checklist line in Asset management.</span></span> <span data-ttu-id="b3ed7-119">Você pode criar a associação por meio de um modelo de lista de verificação de manutenção, um tipo de trabalho de manutenção ou uma ordem de trabalho, pois todos os três contêm linhas da lista de verificação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-119">You can create the association through a maintenance checklist template, a maintenance job type, or a work order, because all three contain maintenance checklist lines.</span></span> <span data-ttu-id="b3ed7-120">Você pode economizar tempo usando um modelo, pois um modelo pode ser associado a todos os tipos de trabalho de manutenção que o usam.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-120">You can save time by using a template, because a template can be associated with all the maintenance job types that use it.</span></span> <span data-ttu-id="b3ed7-121">Por exemplo, um guia associado a um tipo de trabalho de manutenção é associado automaticamente a todas as ordens de trabalho que especificam esse tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-121">For example, a guide that is associated with a maintenance job type is automatically associated with all work orders that specify that job type.</span></span> <span data-ttu-id="b3ed7-122">Por outro lado, um guia associado diretamente a uma ordem de trabalho existe somente para essa ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-122">On the other hand, a guide that is associated directly with a work order exists only for that work order.</span></span>

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a><span data-ttu-id="b3ed7-123">Associar uma guia a um modelo da lista de verificação de manutenção</span><span class="sxs-lookup"><span data-stu-id="b3ed7-123">Associate a guide with a maintenance checklist template</span></span>

<span data-ttu-id="b3ed7-124">Para associar uma guia a um modelo da lista de verificação de manutenção, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-124">To associate a guide with a maintenance checklist template, follow these steps.</span></span>

1. <span data-ttu-id="b3ed7-125">Crie uma guia usando o PC do Dynamics 365 Guides e os aplicativos do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-125">Create a guide by using the Dynamics 365 Guides PC and HoloLens apps.</span></span> <span data-ttu-id="b3ed7-126">Para obter informações sobre como criar uma guia, consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="b3ed7-126">For information about how to create a guide, see the following topics:</span></span>

    - [<span data-ttu-id="b3ed7-127">Use o aplicativo do PC para criar uma guia</span><span class="sxs-lookup"><span data-stu-id="b3ed7-127">Use the PC app to create a guide</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [<span data-ttu-id="b3ed7-128">Use o aplicativo do HoloLens para colocar os hologramas</span><span class="sxs-lookup"><span data-stu-id="b3ed7-128">Use the HoloLens app to place your holograms</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. <span data-ttu-id="b3ed7-129">No Supply Chain Management, [crie um modelo de lista de verificação de manutenção](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span><span class="sxs-lookup"><span data-stu-id="b3ed7-129">In Supply Chain Management, [create a maintenance checklist template](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span></span>
1. <span data-ttu-id="b3ed7-130">Associe a guia criada por uma linha da lista de verificação de manutenção no novo modelo da lista de verificação de manutenção:</span><span class="sxs-lookup"><span data-stu-id="b3ed7-130">Associate the guide that you created with a maintenance checklist line in the new maintenance checklist template:</span></span>

    1. <span data-ttu-id="b3ed7-131">Na Guia Rápida **Linhas da lista de verificação de manutenção**, selecione a linha com a qual você deseja associar a guia.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-131">On the **Maintenance checklist lines** FastTab, select the line that you want to associate the guide with.</span></span>
    1. <span data-ttu-id="b3ed7-132">Na Guia Rápida **Guias associadas**, selecione **Adicionar guia**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-132">On the **Associated guides** FastTab, select **Add Guide**.</span></span>

        <span data-ttu-id="b3ed7-133">![Associar uma guia a uma linha da lista de verificação de manutenção](media/am-guides-integration-add-guide.png "Associar uma guia a uma linha da lista de verificação de manutenção")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-133">![Associate a guide with a maintenance checklist line](media/am-guides-integration-add-guide.png "Associate a guide with a maintenance checklist line")</span></span>

    1. <span data-ttu-id="b3ed7-134">No campo **Nome**, selecione uma guia, e depois seleciona **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-134">In the **Name** field, select a guide, and then select **Save**.</span></span>

        <span data-ttu-id="b3ed7-135">![Selecionar uma guia no campo Nome](media/am-guides-integration-select-guide.png "Selecionar uma guia no campo Nome")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-135">![Select a guide in the Name field](media/am-guides-integration-select-guide.png "Select a guide in the Name field")</span></span>

1. <span data-ttu-id="b3ed7-136">Associar o modelo da lista de verificação de manutenção a um tipo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="b3ed7-136">Associate the maintenance checklist template with a job type:</span></span>

    1. <span data-ttu-id="b3ed7-137">[Crie um tipo de trabalho de manutenção](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) ou selecione um tipo de trabalho de manutenção existente.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-137">[Create a maintenance job type](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type), or select an existing maintenance job type.</span></span>
    1. <span data-ttu-id="b3ed7-138">No Painel de Ações, selecione **Padrões de tipos de trabalho de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-138">On the Action Pane, select **Maintenance job type defaults**.</span></span>

        <span data-ttu-id="b3ed7-139">![Botão Padrões do tipo de trabalho de manutenção](media/am-guides-integration-job-defaults.png "Botão Padrões do tipo de trabalho de manutenção")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-139">![Maintenance job type defaults button](media/am-guides-integration-job-defaults.png "Maintenance job type defaults button")</span></span>

    1. <span data-ttu-id="b3ed7-140">Crie uma linha e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-140">Create a line, and then select **Save**.</span></span>

        <span data-ttu-id="b3ed7-141">![Criar uma linha](media/am-guides-integration-add-line.png "Criar uma linha")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-141">![Create a line](media/am-guides-integration-add-line.png "Create a line")</span></span>

    1. <span data-ttu-id="b3ed7-142">No Painel de Ação, selecione **Lista de verificação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-142">On the Action Pane, select **Maintenance checklist**.</span></span>

        <span data-ttu-id="b3ed7-143">![Botão Lista de verificação de manutenção](media/am-guides-integration-maintenance-checklist.png "Botão Lista de verificação de manutenção")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-143">![Maintenance checklist button](media/am-guides-integration-maintenance-checklist.png "Maintenance checklist button")</span></span>

    1. <span data-ttu-id="b3ed7-144">Na Guia Rápida **Linhas da lista de verificação de manutenção**, adicione uma linha e mude o valor do campo **Tipo** como **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-144">On the **Maintenance checklist lines** FastTab, add a line, and then change the value of the **Type** field to **Template**.</span></span>

        <span data-ttu-id="b3ed7-145">![Alterar o Valor do tipo](media/am-guides-integration-checklist-lines.png "Alterar o Valor do tipo")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-145">![Change the Type value](media/am-guides-integration-checklist-lines.png "Change the Type value")</span></span>

    1. <span data-ttu-id="b3ed7-146">Na Guia Rápida **Detalhes da linha**, no campo **Modelo**, selecione o modelo que você associou com a guia e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-146">On the **Line details** FastTab, in the **Template** field, select the template that you associated the guide with, and then select **Save**.</span></span>

        <span data-ttu-id="b3ed7-147">![Selecione o modelo](media/am-guides-integration-checklist-line-details.png "Selecione o modelo")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-147">![Select the template](media/am-guides-integration-checklist-line-details.png "Select the template")</span></span>

1. <span data-ttu-id="b3ed7-148">[Crie uma ordem de trabalho](work-orders/manually-created-workorders.md#create-work-order) e selecione o tipo de trabalho de manutenção que usa o modelo de lista de verificação de manutenção com o qual você associou a guia.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-148">[Create a work order](work-orders/manually-created-workorders.md#create-work-order), and then select the maintenance job type that uses the maintenance checklist template that you associated the guide with.</span></span> <span data-ttu-id="b3ed7-149">A guia é automaticamente associada à ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-149">The guide is automatically associated with the work order.</span></span>

    <span data-ttu-id="b3ed7-150">![Selecione um tipo de trabalho de manutenção](media/am-guides-integration-create-work-order.png "Selecione um tipo de trabalho de manutenção")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-150">![Select a maintenance job type](media/am-guides-integration-create-work-order.png "Select a maintenance job type")</span></span>

1. <span data-ttu-id="b3ed7-151">Exiba a guia associada à ordem de trabalho e aos trabalhadores:</span><span class="sxs-lookup"><span data-stu-id="b3ed7-151">View the guide that is associated with the work order and workers:</span></span>

    1. <span data-ttu-id="b3ed7-152">Abra o [Espaço de trabalho móvel de gerenciamento de ativos](asset-management-mobile-workspace.md) para acessar a ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-152">Open the [Asset management mobile workspace](asset-management-mobile-workspace.md) to access the work order.</span></span>
    1. <span data-ttu-id="b3ed7-153">[Abra a lista de verificação de manutenção](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) para a ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-153">[Open the maintenance checklist](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) for the work order.</span></span>
    1. <span data-ttu-id="b3ed7-154">Selecione uma linha da lista de verificação para ver a guia associada.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-154">Select a checklist line to see the associated guide.</span></span>

        <span data-ttu-id="b3ed7-155">![Guia associada a uma linha da lista de verificação](media/am-guides-integration-show-guide.png "Guia associado a uma linha da lista de verificação")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-155">![Guide associated with a checklist line](media/am-guides-integration-show-guide.png "Guide associated with a checklist line")</span></span>

    1. <span data-ttu-id="b3ed7-156">Abrir a guia no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-156">Open the guide on HoloLens.</span></span>

        <span data-ttu-id="b3ed7-157">![Abrir a guia no HoloLens](media/am-guides-integration-hololens-select.png "Abrir a guia no HoloLens")</span><span class="sxs-lookup"><span data-stu-id="b3ed7-157">![Open the guide on HoloLens](media/am-guides-integration-hololens-select.png "Open the guide on HoloLens")</span></span>

> [!NOTE]
> <span data-ttu-id="b3ed7-158">Também é possível associar uma guia diretamente na lista de verificação de manutenção de uma ordem de trabalho ou de um tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-158">You can also associate a guide directly in the maintenance checklist of a work order or a job type.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3ed7-159">Há um problema conhecido em que, quando você associa um modelo de lista de verificação de manutenção a um tipo de trabalho de manutenção padrão, a guia vinculada ao modelo não aparece na Guia Rápida **Guias associadas** da página **Padrões de tipo de trabalho de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-159">There is a known issue where, when you associate a maintenance checklist template with a default maintenance job type, the guide that is linked to the template doesn't appear on the **Associated guides** FastTab of the **Maintenance job type defaults** page.</span></span> <span data-ttu-id="b3ed7-160">No entanto, a guia será exibida depois que esse tipo de trabalho for aplicado a uma ordem de trabalho na Guia Rápida **Guias associadas**.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-160">However, the guide will appear after that job type is applied to a work order on the **Associated guides** FastTab.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3ed7-161">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b3ed7-161">See also</span></span>

- [<span data-ttu-id="b3ed7-162">Visão geral da gravação dupla</span><span class="sxs-lookup"><span data-stu-id="b3ed7-162">Dual-write overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [<span data-ttu-id="b3ed7-163">Visão geral do gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="b3ed7-163">Asset management overview</span></span>](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]