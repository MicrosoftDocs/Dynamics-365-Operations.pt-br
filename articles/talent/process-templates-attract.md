---
title: Criar um modelo de processo de contratação no Attract
description: Este tópico fornece informações sobre como criar um modelo de processo de contratação no Attract.
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
ms.openlocfilehash: 82046d43cf7366b760c140bdb8b017337b4f41da
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832549"
---
# <a name="create-a-hiring-process-template-in-attract"></a><span data-ttu-id="44304-103">Criar um modelo de processo de contratação no Attract</span><span class="sxs-lookup"><span data-stu-id="44304-103">Create a hiring process template in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="44304-104">Um *modelo de processo de contratação* contém todas as atividades que devem ser incluídas como parte do processo de contratação para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="44304-104">A *hiring process template* contains all the activities that should be included as part of the hiring process for a job.</span></span> <span data-ttu-id="44304-105">Este tópico descreve os elementos de um modelo de processo no Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="44304-105">This topic describes the elements of a process template in Microsoft Dynamics 365 Talent: Attract.</span></span> <span data-ttu-id="44304-106">Ele também explica como criar um modelo.</span><span class="sxs-lookup"><span data-stu-id="44304-106">It also explains how to create a template.</span></span>

> [!NOTE]
> <span data-ttu-id="44304-107">A criação de modelo é parte do suplemento de contratação abrangente no Attract.</span><span class="sxs-lookup"><span data-stu-id="44304-107">Template creation is part of the Comprehensive Hiring Add-on for Attract.</span></span>

## <a name="template-management"></a><span data-ttu-id="44304-108">Gerenciamento de modelos</span><span class="sxs-lookup"><span data-stu-id="44304-108">Template management</span></span>

<span data-ttu-id="44304-109">Organizações podem decidir se membros da equipe ou apenas administradores podem criar modelos no Attract.</span><span class="sxs-lookup"><span data-stu-id="44304-109">Organizations can decide whether team members or only admins can create process templates in Attract.</span></span> <span data-ttu-id="44304-110">Para configurar o gerenciamento do modelo, vá para **Centro admin** \> **Gerenciamento do modelo**.</span><span class="sxs-lookup"><span data-stu-id="44304-110">To configure template management, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="44304-111">Para deixar membros de equipe criarem seus próprios modelos, ative o gerenciamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="44304-111">To let team members create their own templates, turn on template management.</span></span> <span data-ttu-id="44304-112">Se você não ativa o gerenciamento do modelo, apenas os administradores podem criar modelos.</span><span class="sxs-lookup"><span data-stu-id="44304-112">If you don't turn on template management, only admins can create templates.</span></span>

## <a name="default-template"></a><span data-ttu-id="44304-113">Modelo padrão</span><span class="sxs-lookup"><span data-stu-id="44304-113">Default template</span></span>

<span data-ttu-id="44304-114">Apenas os administradores podem definir o modelo padrão.</span><span class="sxs-lookup"><span data-stu-id="44304-114">Only admins can set the default template.</span></span> <span data-ttu-id="44304-115">O modelo padrão é usado se um modelo não for selecionado quando um trabalho for criado.</span><span class="sxs-lookup"><span data-stu-id="44304-115">The default template is used if a template isn't selected when a job is created.</span></span> <span data-ttu-id="44304-116">Para definir o modelo padrão, vá para **Centro admin** \> **Gerenciamento do modelo**.</span><span class="sxs-lookup"><span data-stu-id="44304-116">To set the default template, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="44304-117">No cartão do modelo que deve ser o modelo padrão, selecione o botão de reticências (**...**), e depois selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="44304-117">On the card for the template that should be the default template, select the ellipsis button (**...**), and then select **Set as default**.</span></span>

## <a name="create-a-process-template"></a><span data-ttu-id="44304-118">Criar um modelo de processo</span><span class="sxs-lookup"><span data-stu-id="44304-118">Create a process template</span></span>

<span data-ttu-id="44304-119">Os administradores, os recrutadores e os gerentes de contratação podem criar modelos de processo.</span><span class="sxs-lookup"><span data-stu-id="44304-119">Admins, recruiters, and hiring managers can create process templates.</span></span> <span data-ttu-id="44304-120">Um modelo de processo consiste de *estágios* e *atividades*.</span><span class="sxs-lookup"><span data-stu-id="44304-120">A process template consists of *stages* and *activities*.</span></span> <span data-ttu-id="44304-121">Os estágios agrupam uma ou mais atividades.</span><span class="sxs-lookup"><span data-stu-id="44304-121">Stages group together one or more activities.</span></span> <span data-ttu-id="44304-122">Por padrão, cada método de processo tem atividades de cliente potencial, de aplicativos e oferta.</span><span class="sxs-lookup"><span data-stu-id="44304-122">By default, every process template has Prospect, Application, and Offer activities.</span></span> <span data-ttu-id="44304-123">Os estágios que contêm essas atividades podem ser renomeados.</span><span class="sxs-lookup"><span data-stu-id="44304-123">The stages that contain these activities can be renamed.</span></span> <span data-ttu-id="44304-124">Você pode adicionar mais estágios selecionando **+ Novo estágio**.</span><span class="sxs-lookup"><span data-stu-id="44304-124">You can add more stages by selecting **+ New Stage**.</span></span> <span data-ttu-id="44304-125">Você pode adicionar as atividades a um estágio arrastando-as para o estágio apropriado ou com clique duplo nelas na lista de atividade.</span><span class="sxs-lookup"><span data-stu-id="44304-125">You can add activities to a stage either by dragging them to the appropriate stage or by double-clicking them in the activity list.</span></span>

> [!NOTE]
> <span data-ttu-id="44304-126">Os nomes de estágio são visíveis candidatos na página **Status de solicitação**.</span><span class="sxs-lookup"><span data-stu-id="44304-126">Stage names are visible to candidates on the **Application status** page.</span></span> <span data-ttu-id="44304-127">Considere esses fatos quando escolher nomes de estágios.</span><span class="sxs-lookup"><span data-stu-id="44304-127">You should consider this fact when you choose names for stages.</span></span>

<span data-ttu-id="44304-128">Para saber mais sobre atividades, consulte [Atividades em processos de contratação](./activities-attract.md).</span><span class="sxs-lookup"><span data-stu-id="44304-128">To learn more about activities, see [Activities in hiring processes](./activities-attract.md).</span></span>

<span data-ttu-id="44304-129">Siga estas etapas para criar um modelo de processo de contratação.</span><span class="sxs-lookup"><span data-stu-id="44304-129">Follow these steps to create a hiring process template.</span></span>

1. <span data-ttu-id="44304-130">Vá para **Modelos**.</span><span class="sxs-lookup"><span data-stu-id="44304-130">Go to **Templates**.</span></span>
2. <span data-ttu-id="44304-131">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="44304-131">Select **New**.</span></span>
3. <span data-ttu-id="44304-132">No campo **Nome do modelo**, insira um nome para o modelo, e depois selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="44304-132">In the **Template name** field, enter a name for the template, and then select **Create**.</span></span>
4. <span data-ttu-id="44304-133">Na lista **Escolha o processo de aprovação**, selecione **Padrão** para exigir aprovação para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="44304-133">In the **Choose the approval process** list, select **Default** to require approval for a job.</span></span>
5. <span data-ttu-id="44304-134">Selecione para habilitar ou desabilitar candidatos potenciais.</span><span class="sxs-lookup"><span data-stu-id="44304-134">Select to enable or disable prospects.</span></span>
6. <span data-ttu-id="44304-135">Opcional: Adicione ou remova estágios.</span><span class="sxs-lookup"><span data-stu-id="44304-135">Optional: Add or remove stages.</span></span>

    - <span data-ttu-id="44304-136">Para adicionar um estágio, selecione **+ Novo estágio**.</span><span class="sxs-lookup"><span data-stu-id="44304-136">To add a stage, select **+ New Stage**.</span></span>
    - <span data-ttu-id="44304-137">Para remover uma remessa, coloque o ponteiro sobre o estágio, e selecione o botão de lixo que aparece.</span><span class="sxs-lookup"><span data-stu-id="44304-137">To remove a stage, hover the pointer over the stage, and then select the trash can button that appears.</span></span>

        > [!NOTE]
        > <span data-ttu-id="44304-138">O candidato potencial, solicitação de emprego e os estágios de oferta não podem ser removidos, mas podem ser renomeados.</span><span class="sxs-lookup"><span data-stu-id="44304-138">Prospect, Application, and Offer stages can't be removed, but they can be renamed.</span></span>

7. <span data-ttu-id="44304-139">Opcional: Adicione ou remova atividades.</span><span class="sxs-lookup"><span data-stu-id="44304-139">Optional: Add or remove activities.</span></span>

    - <span data-ttu-id="44304-140">Para adicionar uma atividade, arraste-a da lista de atividades para a direita do estágio apropriado.</span><span class="sxs-lookup"><span data-stu-id="44304-140">To add an activity, drag it from the activity list on the right to the appropriate stage.</span></span> <span data-ttu-id="44304-141">Outra opção é clicar duas vezes na atividade e selecionar o estágio para adicioná-la.</span><span class="sxs-lookup"><span data-stu-id="44304-141">Alternatively, double-click the activity, and then select the stage to add it to.</span></span>
    - <span data-ttu-id="44304-142">Para remover uma atividade, expanda-a e depois selecione o botão de lixeira no cabeçalho da atividade.</span><span class="sxs-lookup"><span data-stu-id="44304-142">To remove an activity, expand it, and then select the trash can button on the activity header.</span></span>

8. <span data-ttu-id="44304-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="44304-143">Select **Save**.</span></span>
