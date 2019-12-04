---
title: Novidades ou alterações no Dynamics 365 Talent (5 de novembro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e6a81209c3c4a95ee51668533d40d4aecc1d58b9
ms.sourcegitcommit: a46fb06138f7f82e973dca3157d30f9b21d3a70b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "2778373"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a><span data-ttu-id="efecb-103">Novidades ou alterações no Dynamics 365 Talent (5 de novembro de 2019)</span><span class="sxs-lookup"><span data-stu-id="efecb-103">What's new or changed in Dynamics 365 Talent (November 5, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="efecb-104">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="efecb-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="efecb-105">Alterações no Attract</span><span class="sxs-lookup"><span data-stu-id="efecb-105">Changes in Attract</span></span>

<span data-ttu-id="efecb-106">Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="efecb-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="efecb-107">Alterações de Integração</span><span class="sxs-lookup"><span data-stu-id="efecb-107">Changes in Onboard</span></span>

<span data-ttu-id="efecb-108">Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="efecb-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="efecb-109">Alterações no Core HR</span><span class="sxs-lookup"><span data-stu-id="efecb-109">Changes in Core HR</span></span>

<span data-ttu-id="efecb-110">As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2598.</span><span class="sxs-lookup"><span data-stu-id="efecb-110">Changes described in this section apply to build number 8.1.2598.</span></span> <span data-ttu-id="efecb-111">Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="efecb-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="copy-a-core-hr-instance"></a><span data-ttu-id="efecb-112">Copiar uma instância do Core HR</span><span class="sxs-lookup"><span data-stu-id="efecb-112">Copy a Core HR instance</span></span>

<span data-ttu-id="efecb-113">Na versão desta semana, é possível usar o Microsoft Dynamics Lifecycle Services (LCS) para copiar um banco de dados do Microsoft Dynamics 365 Talent: Core HR para um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="efecb-113">In this week's release, you can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Talent: Core HR database to a sandbox environment.</span></span> <span data-ttu-id="efecb-114">Se houver outro ambiente de área restrita, você também poderá copiar o banco de dados daquele ambiente para um ambiente de área restrita direcionado.</span><span class="sxs-lookup"><span data-stu-id="efecb-114">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span> <span data-ttu-id="efecb-115">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="efecb-115">For more information, see:</span></span>

- <span data-ttu-id="efecb-116">[Gerenciamento de ambiente mais amplo](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) no plano da onda 2 da versão 2019 do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="efecb-116">[Broader environment management](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) in the Dynamics 365: 2019 release wave 2 plan</span></span>

- <span data-ttu-id="efecb-117">[Copiar uma instância Core HR](hr-copy-instance.md) na documentação do Talent</span><span class="sxs-lookup"><span data-stu-id="efecb-117">[Copy a Core HR instance](hr-copy-instance.md) in Talent documentation</span></span>

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a><span data-ttu-id="efecb-118">Os trabalhos em lotes da integração do Common Data Service não são criados quando a integração do Common Data Service está habilitada (388030)</span><span class="sxs-lookup"><span data-stu-id="efecb-118">Common Data Service integration batch jobs aren't created when Common Data Service integration is enabled (388030)</span></span>

<span data-ttu-id="efecb-119">Esta alteração criará trabalhos em lotes para a integração do Common Data Service quando ele estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="efecb-119">This change will create batch jobs for Common Data Service integration when it's enabled.</span></span>

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a><span data-ttu-id="efecb-120">A HcmPersonImageEntity não redimensiona a imagem da pessoa no upload (369469)</span><span class="sxs-lookup"><span data-stu-id="efecb-120">The HcmPersonImageEntity doesn't resize the person image when uploaded (369469)</span></span>

<span data-ttu-id="efecb-121">A versão desta semana altera a forma como as imagens são redimensionadas para melhorar o desempenho quando importadas por meio do gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="efecb-121">This week's release changes how images are resized for better performance when imported through data management.</span></span>

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a><span data-ttu-id="efecb-122">Uma Data disponível para atribuição da posição pode ser anterior à Data de ativação (340103)</span><span class="sxs-lookup"><span data-stu-id="efecb-122">A position's Available for assignment date can be earlier than the Activation date (340103)</span></span>

<span data-ttu-id="efecb-123">Com essa alteração, um aviso será exibido se você selecionar uma **Data disponível para atribuição** anterior à **Data de ativação** da posição.</span><span class="sxs-lookup"><span data-stu-id="efecb-123">With this change, a warning will appear if you select an **Available for assignment date** that's earlier than the position's **Activation date**.</span></span>

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a><span data-ttu-id="efecb-124">Não é possível criar uma solicitação de alteração de compensação no auto-atendimento do funcionário para os planos baseados em etapas (376872)</span><span class="sxs-lookup"><span data-stu-id="efecb-124">Can't create a compensation change request in employee self-service for step-based plans (376872)</span></span>

<span data-ttu-id="efecb-125">Essa versão corrige um problema na solicitação de alterações de compensação por meio do auto-atendimento para funcionário em planos baseados em etapas.</span><span class="sxs-lookup"><span data-stu-id="efecb-125">This release corrects an issue when requesting compensation changes through employee self-service for step-based plans.</span></span> 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a><span data-ttu-id="efecb-126">O código do motivo não será sincronizado com o Common Data Service se a descrição tiver mais de 30 caracteres, o Core HR permite 60 (352682)</span><span class="sxs-lookup"><span data-stu-id="efecb-126">Reason code doesn't sync to Common Data Service if the description is longer than 30 characters, Core HR allows 60 (352682)</span></span>

<span data-ttu-id="efecb-127">Com essa alteração, os códigos de motivo com mais de 30 caracteres serão atualizados no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="efecb-127">with this change, reason codes with more than 30 characters will be updated in Common Data Service.</span></span> <span data-ttu-id="efecb-128">As alterações feitas no Common Data Service também serão refletidas no Talent.</span><span class="sxs-lookup"><span data-stu-id="efecb-128">Changes made in Common Data Service will also be reflected back in Talent.</span></span>

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a><span data-ttu-id="efecb-129">Integração de endereço do Talent ao Finance and Operations (351961)</span><span class="sxs-lookup"><span data-stu-id="efecb-129">Address integration from Talent to Finance and Operations (351961)</span></span>

<span data-ttu-id="efecb-130">Essa versão corrige um problema em que os endereços atualizados no Talent não estavam sendo atualizados no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="efecb-130">This release fixes an issue where addresses updated in Talent weren't updating in Finance and Operations.</span></span> <span data-ttu-id="efecb-131">As alterações feitas nos blocos de endereço serão atualizadas agora.</span><span class="sxs-lookup"><span data-stu-id="efecb-131">Changes to address blocks will now update.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="efecb-132">Em breve</span><span class="sxs-lookup"><span data-stu-id="efecb-132">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="efecb-133">Imprima avaliações de desempenho</span><span class="sxs-lookup"><span data-stu-id="efecb-133">Print performance reviews</span></span>

<span data-ttu-id="efecb-134">Consulte [Revisões de desempenho de impressão](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) no plano da onda 2 da versão 2019 do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="efecb-134">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="efecb-135">Espaço de trabalho do gerenciamento de recursos</span><span class="sxs-lookup"><span data-stu-id="efecb-135">Feature management workspace</span></span>

<span data-ttu-id="efecb-136">Os recursos são adicionados e atualizados em cada versão.</span><span class="sxs-lookup"><span data-stu-id="efecb-136">Features are added and updated in every release.</span></span> <span data-ttu-id="efecb-137">A experiência de gerenciamento de recursos fornece um espaço de trabalho no qual você pode exibir uma lista dos recursos que foram entregues em cada versão.</span><span class="sxs-lookup"><span data-stu-id="efecb-137">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="efecb-138">Por padrão, os novos recurso estão desativados.</span><span class="sxs-lookup"><span data-stu-id="efecb-138">By default, new features are turned off.</span></span> <span data-ttu-id="efecb-139">Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles.</span><span class="sxs-lookup"><span data-stu-id="efecb-139">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="efecb-140">Para saber mais sobre as mudanças que acompanham o gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview)</span><span class="sxs-lookup"><span data-stu-id="efecb-140">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
