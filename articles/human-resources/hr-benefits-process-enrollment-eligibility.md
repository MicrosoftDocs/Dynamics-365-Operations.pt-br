---
title: Processar qualificação da inscrição
description: Este artigo explica como executar o processo de qualificação da inscrição.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008037"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="53d1f-103">Processar qualificação da inscrição</span><span class="sxs-lookup"><span data-stu-id="53d1f-103">Process enrollment eligibility</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="53d1f-104">Este artigo explica como executar o processo de qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="53d1f-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="53d1f-105">No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento da qualificação da inscrição**.</span><span class="sxs-lookup"><span data-stu-id="53d1f-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="53d1f-106">No caixa de diálogo **Executar o processamento da qualificação de inscrição no benefício**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="53d1f-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="53d1f-107">Campo</span><span class="sxs-lookup"><span data-stu-id="53d1f-107">Field</span></span> | <span data-ttu-id="53d1f-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="53d1f-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="53d1f-109">Período de inscrição</span><span class="sxs-lookup"><span data-stu-id="53d1f-109">Enrollment period</span></span> | <span data-ttu-id="53d1f-110">O período de inscrição para processar a qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="53d1f-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="53d1f-111">Pessoa jurídica em geral</span><span class="sxs-lookup"><span data-stu-id="53d1f-111">Legal entity</span></span> | <span data-ttu-id="53d1f-112">A entidade legal para processar a qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="53d1f-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="53d1f-113">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="53d1f-113">Worker</span></span> | <span data-ttu-id="53d1f-114">O trabalhador para processar a qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="53d1f-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="53d1f-115">Se você deixar esse campo em branco, a qualificação da inscrição será processada para todos os trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="53d1f-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="53d1f-116">Plano de benefícios</span><span class="sxs-lookup"><span data-stu-id="53d1f-116">Benefit plan</span></span> | <span data-ttu-id="53d1f-117">O plano de benefícios para processar a qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="53d1f-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="53d1f-118">Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="53d1f-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="53d1f-119">Insira informações para o processo.</span><span class="sxs-lookup"><span data-stu-id="53d1f-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="53d1f-120">Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="53d1f-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="53d1f-121">Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="53d1f-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="53d1f-122">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="53d1f-122">Select **OK**.</span></span> <span data-ttu-id="53d1f-123">O processo será executado com os parâmetros definidos por você.</span><span class="sxs-lookup"><span data-stu-id="53d1f-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="53d1f-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="53d1f-124">Select **OK**.</span></span>
