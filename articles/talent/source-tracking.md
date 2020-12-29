---
title: Rastrear origens do candidato no Attract
description: Este tópico fornece informações sobre como rastrear a origem de perfis de candidatos e solicitações de emprego.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8860f508eebc377042c4e101eeb08a14a737ba0c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460316"
---
# <a name="track-candidate-sources-in-attract"></a><span data-ttu-id="dd13d-103">Rastrear origens do candidato no Attract</span><span class="sxs-lookup"><span data-stu-id="dd13d-103">Track candidate sources in Attract</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE] 
> <span data-ttu-id="dd13d-104">A funcionalidade observada neste tópico está disponível para usuários como parte de uma revisão de versão prévia.</span><span class="sxs-lookup"><span data-stu-id="dd13d-104">Functionality noted in this topic is available as part of a preview review release.</span></span> <span data-ttu-id="dd13d-105">O conteúdo e as funcionalidades estão sujeitos a alteração.</span><span class="sxs-lookup"><span data-stu-id="dd13d-105">The content and the functionality are subject to change.</span></span> <span data-ttu-id="dd13d-106">Para usar o recurso, peça ao administrador habilitá-lo usando as **Configurações do administrador** no Attract.</span><span class="sxs-lookup"><span data-stu-id="dd13d-106">To use this feature, ask an administrator to enable it using the **Admin settings** in Attract.</span></span> <span data-ttu-id="dd13d-107">Uma versão futura fornecerá relatórios de rastreamento da origem.</span><span class="sxs-lookup"><span data-stu-id="dd13d-107">A future release will provide source tracking reports.</span></span> <span data-ttu-id="dd13d-108">Para obter mais informações, consulte [Acessar os recursos de visualização no Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="dd13d-108">For more information, see [Access preview features in Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

<span data-ttu-id="dd13d-109">Quando os candidatos se candidatam a um trabalho, o Attract automaticamente rastreia a origem dessas solicitações de emprego, fornecendo informações valiosas que ajudam a direcionar os esforços de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="dd13d-109">When candidates apply for a job, Attract automatically tracks the source of their applications, providing you with valuable information to help you target your recruiting efforts.</span></span> <span data-ttu-id="dd13d-110">Os recrutadores e gerentes de projeto também podem selecionar uma origem de solicitação de emprego ao adicionar manualmente um candidato a um grupo de trabalhos ou de talentos.</span><span class="sxs-lookup"><span data-stu-id="dd13d-110">Recruiters and hiring managers can also select an application source while manually adding a candidate to a job or talent pool.</span></span>

<span data-ttu-id="dd13d-111">Você pode exibir a origem da solicitação de emprego nos detalhes da atividade de solicitação de emprego na guia **Atividade** e no histórico de solicitações em **Perfil**, nos grupos de talentos.</span><span class="sxs-lookup"><span data-stu-id="dd13d-111">You can view the application source in the application activity details under the **Activity** tab, as well as in the application history available under **Profile** in talent pools.</span></span> <span data-ttu-id="dd13d-112">Você pode encontrar a origem do perfil de um candidato nos detalhes do candidato na guia **Perfil** em grupos de talentos e de solicitações de emprego.</span><span class="sxs-lookup"><span data-stu-id="dd13d-112">You can find a candidate's profile source in the candidate details under the **Profile** tab in both applications and talent pools.</span></span>

> [!NOTE] 
> <span data-ttu-id="dd13d-113">Você pode encontrar modelos de processo no [complemento de Contratação abrangente](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="dd13d-113">You can find process templates in the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>

## <a name="pre-configured-sources"></a><span data-ttu-id="dd13d-114">Fontes pré-configuradas</span><span class="sxs-lookup"><span data-stu-id="dd13d-114">Pre-configured sources</span></span>

<span data-ttu-id="dd13d-115">A lista de origens padrão contém fontes comuns de solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="dd13d-115">The default source list contains common application sources.</span></span> <span data-ttu-id="dd13d-116">Alguns tipos de fonte, como **Quadro de trabalho** e **Rede Social**, possuem outros detalhes.</span><span class="sxs-lookup"><span data-stu-id="dd13d-116">Some source types, like **Job board** and **Social Network**, have additional source details.</span></span> <span data-ttu-id="dd13d-117">Por exemplo, **Rede Social** inclui Facebook e Twitter.</span><span class="sxs-lookup"><span data-stu-id="dd13d-117">For example, **Social Network** includes Facebook and Twitter.</span></span> <span data-ttu-id="dd13d-118">O tipo de fonte **Indicação** permite especificar um funcionário interno como referenciador.</span><span class="sxs-lookup"><span data-stu-id="dd13d-118">The **Referral** source type allows you to specify an internal employee as the referrer.</span></span> <span data-ttu-id="dd13d-119">A lista de origens padrão inclui as seguintes fontes pré-configuradas:</span><span class="sxs-lookup"><span data-stu-id="dd13d-119">The default source list includes the following pre-configured sources:</span></span>

-   <span data-ttu-id="dd13d-120">Site de carreiras Attract</span><span class="sxs-lookup"><span data-stu-id="dd13d-120">Attract career site</span></span>

-   <span data-ttu-id="dd13d-121">Agência</span><span class="sxs-lookup"><span data-stu-id="dd13d-121">Agency</span></span>

-   <span data-ttu-id="dd13d-122">Feiras de profissões</span><span class="sxs-lookup"><span data-stu-id="dd13d-122">Career Fair</span></span>

-   <span data-ttu-id="dd13d-123">Marketing da empresa</span><span class="sxs-lookup"><span data-stu-id="dd13d-123">Company Marketing</span></span>

-   <span data-ttu-id="dd13d-124">Conferências e feiras de negócios</span><span class="sxs-lookup"><span data-stu-id="dd13d-124">Conferences & Trade shows</span></span>

-   <span data-ttu-id="dd13d-125">Associações profissionais</span><span class="sxs-lookup"><span data-stu-id="dd13d-125">Professional Association</span></span>

-   <span data-ttu-id="dd13d-126">Quadro de trabalho</span><span class="sxs-lookup"><span data-stu-id="dd13d-126">Job board</span></span>

    -   <span data-ttu-id="dd13d-127">Indeed</span><span class="sxs-lookup"><span data-stu-id="dd13d-127">Indeed</span></span>

    -   <span data-ttu-id="dd13d-128">Seek</span><span class="sxs-lookup"><span data-stu-id="dd13d-128">Seek</span></span>

    -   <span data-ttu-id="dd13d-129">CareerBuilder</span><span class="sxs-lookup"><span data-stu-id="dd13d-129">CareerBuilder</span></span>

    -   <span data-ttu-id="dd13d-130">Google Jobs</span><span class="sxs-lookup"><span data-stu-id="dd13d-130">Google Jobs</span></span>

    -   <span data-ttu-id="dd13d-131">Xing</span><span class="sxs-lookup"><span data-stu-id="dd13d-131">Xing</span></span>

    -   <span data-ttu-id="dd13d-132">Glassdoor</span><span class="sxs-lookup"><span data-stu-id="dd13d-132">Glassdoor</span></span>

    -   <span data-ttu-id="dd13d-133">Monster Jobs</span><span class="sxs-lookup"><span data-stu-id="dd13d-133">Monster Jobs</span></span>

-   <span data-ttu-id="dd13d-134">Revistas e publicações</span><span class="sxs-lookup"><span data-stu-id="dd13d-134">Magazines & Publications</span></span>

-   <span data-ttu-id="dd13d-135">Redes sociais</span><span class="sxs-lookup"><span data-stu-id="dd13d-135">Social Network</span></span>

    -   <span data-ttu-id="dd13d-136">Facebook</span><span class="sxs-lookup"><span data-stu-id="dd13d-136">Facebook</span></span>

    -   <span data-ttu-id="dd13d-137">Twitter</span><span class="sxs-lookup"><span data-stu-id="dd13d-137">Twitter</span></span>

-   <span data-ttu-id="dd13d-138">Recrutamento em universidades</span><span class="sxs-lookup"><span data-stu-id="dd13d-138">University Recruiting</span></span>

-   <span data-ttu-id="dd13d-139">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="dd13d-139">LinkedIn</span></span>

-   <span data-ttu-id="dd13d-140">Classificados</span><span class="sxs-lookup"><span data-stu-id="dd13d-140">Classifieds</span></span>

-   <span data-ttu-id="dd13d-141">Referência</span><span class="sxs-lookup"><span data-stu-id="dd13d-141">Referral</span></span>

-   <span data-ttu-id="dd13d-142">Adicionado pelo recrutador</span><span class="sxs-lookup"><span data-stu-id="dd13d-142">Added by Recruiter</span></span>

-   <span data-ttu-id="dd13d-143">Outro</span><span class="sxs-lookup"><span data-stu-id="dd13d-143">Other</span></span>

## <a name="customize-the-source-list"></a><span data-ttu-id="dd13d-144">Personalizar a lista de origens</span><span class="sxs-lookup"><span data-stu-id="dd13d-144">Customize the source list</span></span> 

<span data-ttu-id="dd13d-145">Você pode estender a lista de origens para incluir outras fontes de solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="dd13d-145">You can extend the source list to include additional application sources.</span></span> <span data-ttu-id="dd13d-146">Para personalizar essa lista, siga as instruções em [Extensão dos conjuntos de opções no Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span><span class="sxs-lookup"><span data-stu-id="dd13d-146">To customize this list, follow the instructions in [Extending Option Sets in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span></span> <span data-ttu-id="dd13d-147">Edite a entidade **TalentSource** para incluir outras origens.</span><span class="sxs-lookup"><span data-stu-id="dd13d-147">Edit the **TalentSource** entity to include additional sources.</span></span> 

<span data-ttu-id="dd13d-148">Para não gerar um impacto negativo na interface do usuário, não edite nem exclua os valores de enumeração **TalentCategory** (não nomes) para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dd13d-148">To avoid negatively impacting the user interface (UI), don't edit or delete the **TalentCategory** enum values (not names) for the following:</span></span>

- <span data-ttu-id="dd13d-149">**Referência**</span><span class="sxs-lookup"><span data-stu-id="dd13d-149">**Referral**</span></span>
- <span data-ttu-id="dd13d-150">**LinkedIn**</span><span class="sxs-lookup"><span data-stu-id="dd13d-150">**LinkedIn**</span></span>
- <span data-ttu-id="dd13d-151">**Outro**</span><span class="sxs-lookup"><span data-stu-id="dd13d-151">**Other**</span></span>

<span data-ttu-id="dd13d-152">Em vez disso, você pode estender a enumeração **TalentSource** para adicionar outros tipos de origem.</span><span class="sxs-lookup"><span data-stu-id="dd13d-152">Instead, you can extend the **TalentSource** enum to add other types of sources.</span></span>
