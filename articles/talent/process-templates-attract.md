---
title: Criar um modelo de processo no Attract
description: Este tópico fornece informações sobre como criar um modelo de processo no Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: ca04bb623b9ddd19f02efbf99289461a78ddd7f1
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "856614"
---
# <a name="create-a-process-template-in-attract"></a><span data-ttu-id="141dd-103">Criar um modelo de processo no Attract</span><span class="sxs-lookup"><span data-stu-id="141dd-103">Create a process template in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="141dd-104">Um *modelo de processo de contratação* contém todas as atividades que devem ser incluídas como parte do processo de contratação para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="141dd-104">A *hiring process template* contains all the activities that should be included as part of the hiring process for a job.</span></span> <span data-ttu-id="141dd-105">Este tópico descreve os elementos de um modelo de processo no Microsoft Dynamics 365 for Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="141dd-105">This topic describes the elements of a process template in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="141dd-106">Ele também explica como criar um modelo.</span><span class="sxs-lookup"><span data-stu-id="141dd-106">It also explains how to create a template.</span></span>

> [!NOTE]
> <span data-ttu-id="141dd-107">A criação de modelo é parte do suplemento de contratação abrangente no Attract.</span><span class="sxs-lookup"><span data-stu-id="141dd-107">Template creation is part of the Comprehensive Hiring Add-on for Attract.</span></span>

## <a name="template-management"></a><span data-ttu-id="141dd-108">Gerenciamento de modelos</span><span class="sxs-lookup"><span data-stu-id="141dd-108">Template management</span></span>

<span data-ttu-id="141dd-109">Organizações podem decidir se membros da equipe ou apenas administradores podem criar modelos no Attract.</span><span class="sxs-lookup"><span data-stu-id="141dd-109">Organizations can decide whether team members or only admins can create process templates in Attract.</span></span> <span data-ttu-id="141dd-110">Para configurar o gerenciamento do modelo, vá para **Centro admin** \> **Gerenciamento do modelo**.</span><span class="sxs-lookup"><span data-stu-id="141dd-110">To configure template management, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="141dd-111">Para deixar membros de equipe criarem seus próprios modelos, ative o gerenciamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="141dd-111">To let team members create their own templates, turn on template management.</span></span> <span data-ttu-id="141dd-112">Se você não ativa o gerenciamento do modelo, apenas os administradores podem criar modelos.</span><span class="sxs-lookup"><span data-stu-id="141dd-112">If you don't turn on template management, only admins can create templates.</span></span>

## <a name="default-template"></a><span data-ttu-id="141dd-113">Modelo padrão</span><span class="sxs-lookup"><span data-stu-id="141dd-113">Default template</span></span>

<span data-ttu-id="141dd-114">Apenas os administradores podem definir o modelo padrão.</span><span class="sxs-lookup"><span data-stu-id="141dd-114">Only admins can set the default template.</span></span> <span data-ttu-id="141dd-115">O modelo padrão é usado se um modelo não for selecionado quando um trabalho for criado.</span><span class="sxs-lookup"><span data-stu-id="141dd-115">The default template is used if a template isn't selected when a job is created.</span></span> <span data-ttu-id="141dd-116">Para definir o modelo padrão, vá para **Centro admin** \> **Gerenciamento do modelo**.</span><span class="sxs-lookup"><span data-stu-id="141dd-116">To set the default template, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="141dd-117">No cartão do modelo que deve ser o modelo padrão, selecione o botão de reticências (**...**), e depois selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="141dd-117">On the card for the template that should be the default template, select the ellipsis button (**...**), and then select **Set as default**.</span></span>

## <a name="create-a-process-template"></a><span data-ttu-id="141dd-118">Criar um modelo de processo</span><span class="sxs-lookup"><span data-stu-id="141dd-118">Create a process template</span></span>

<span data-ttu-id="141dd-119">Os administradores, os recrutadores e os gerentes de contratação podem criar modelos de processo.</span><span class="sxs-lookup"><span data-stu-id="141dd-119">Admins, recruiters, and hiring managers can create process templates.</span></span> <span data-ttu-id="141dd-120">Um modelo de processo consiste de *estágios* e *atividades*.</span><span class="sxs-lookup"><span data-stu-id="141dd-120">A process template consists of *stages* and *activities*.</span></span> <span data-ttu-id="141dd-121">Os estágios agrupam uma ou mais atividades.</span><span class="sxs-lookup"><span data-stu-id="141dd-121">Stages group together one or more activities.</span></span> <span data-ttu-id="141dd-122">Por padrão, cada método de processo tem atividades de cliente potencial, de aplicativos e oferta.</span><span class="sxs-lookup"><span data-stu-id="141dd-122">By default, every process template has Prospect, Application, and Offer activities.</span></span> <span data-ttu-id="141dd-123">Os estágios que contêm essas atividades podem ser renomeados.</span><span class="sxs-lookup"><span data-stu-id="141dd-123">The stages that contain these activities can be renamed.</span></span> <span data-ttu-id="141dd-124">Você pode adicionar mais estágios selecionando **+ Novo estágio**.</span><span class="sxs-lookup"><span data-stu-id="141dd-124">You can add more stages by selecting **+ New Stage**.</span></span> <span data-ttu-id="141dd-125">Você pode levar as atividades a um estágio arrastando-as para o estágio apropriado ou com clique duplo nelas na lista de atividade.</span><span class="sxs-lookup"><span data-stu-id="141dd-125">You can activities to a stage either by dragging them to the appropriate stage or by double-clicking them in the activity list.</span></span>

> [!NOTE]
> <span data-ttu-id="141dd-126">Os nomes de estágio são visíveis candidatos na página **Status de solicitação**.</span><span class="sxs-lookup"><span data-stu-id="141dd-126">Stage names are visible to candidates on the **Application status** page.</span></span> <span data-ttu-id="141dd-127">Considere esses fatos quando escolher nomes de estágios.</span><span class="sxs-lookup"><span data-stu-id="141dd-127">You should consider this fact when you choose names for stages.</span></span>

<span data-ttu-id="141dd-128">Para saber mais sobre atividades, consulte [Atividades do processo de contratação no Attract](./activities-attract.md).</span><span class="sxs-lookup"><span data-stu-id="141dd-128">To learn more about activities, see [Hiring process activities in Attract](./activities-attract.md).</span></span>

<span data-ttu-id="141dd-129">Siga estas etapas para criar um modelo de processo de contratação.</span><span class="sxs-lookup"><span data-stu-id="141dd-129">Follow these steps to create a hiring process template.</span></span>

1. <span data-ttu-id="141dd-130">Vá para **Modelos**.</span><span class="sxs-lookup"><span data-stu-id="141dd-130">Go to **Templates**.</span></span>
2. <span data-ttu-id="141dd-131">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="141dd-131">Select **New**.</span></span>
3. <span data-ttu-id="141dd-132">No campo **Nome do modelo**, insira um nome para o modelo, e depois selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="141dd-132">In the **Template name** field, enter a name for the template, and then select **Create**.</span></span>
4. <span data-ttu-id="141dd-133">Na lista **Escolha o processo de aprovação**, selecione **Padrão** para exigir aprovação para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="141dd-133">In the **Choose the approval process** list, select **Default** to require approval for a job.</span></span>
5. <span data-ttu-id="141dd-134">Selecione para habilitar ou desabilitar candidatos potenciais.</span><span class="sxs-lookup"><span data-stu-id="141dd-134">Select to enable or disable prospects.</span></span>
6. <span data-ttu-id="141dd-135">Opcional: Adicione ou remova estágios.</span><span class="sxs-lookup"><span data-stu-id="141dd-135">Optional: Add or remove stages.</span></span>

    - <span data-ttu-id="141dd-136">Para adicionar um estágio, selecione **+ Novo estágio**.</span><span class="sxs-lookup"><span data-stu-id="141dd-136">To add a stage, select **+ New Stage**.</span></span>
    - <span data-ttu-id="141dd-137">Para remover uma remessa, coloque o ponteiro sobre o estágio, e selecione o botão de lixo que aparece.</span><span class="sxs-lookup"><span data-stu-id="141dd-137">To remove a stage, hover the pointer over the stage, and then select the trash can button that appears.</span></span>

        > [!NOTE]
        > <span data-ttu-id="141dd-138">O candidato potencial, solicitação de emprego e os estágios de oferta não podem ser removidos, mas podem ser renomeados.</span><span class="sxs-lookup"><span data-stu-id="141dd-138">Prospect, Application, and Offer stages can't be removed, but they can be renamed.</span></span>

7. <span data-ttu-id="141dd-139">Opcional: Adicione ou remova atividades.</span><span class="sxs-lookup"><span data-stu-id="141dd-139">Optional: Add or remove activities.</span></span>

    - <span data-ttu-id="141dd-140">Para adicionar uma atividade, arraste-a da lista de atividades para a direita do estágio apropriado.</span><span class="sxs-lookup"><span data-stu-id="141dd-140">To add an activity, drag it from the activity list on the right to the appropriate stage.</span></span> <span data-ttu-id="141dd-141">Outra opção é clicar duas vezes na atividade e selecionar o estágio para adicioná-la.</span><span class="sxs-lookup"><span data-stu-id="141dd-141">Alternatively, double-click the activity, and then select the stage to add it to.</span></span>
    - <span data-ttu-id="141dd-142">Para remover uma atividade, expanda-a e depois selecione o botão de lixeira no cabeçalho da atividade.</span><span class="sxs-lookup"><span data-stu-id="141dd-142">To remove an activity, expand it, and then select the trash can button on the activity header.</span></span>

8. <span data-ttu-id="141dd-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="141dd-143">Select **Save**.</span></span>
