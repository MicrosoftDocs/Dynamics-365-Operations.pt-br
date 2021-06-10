---
title: Processar qualificação da inscrição
description: Este artigo explica como executar o processo de qualificação da inscrição.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4dd63e755f0afdbce411b3001410d2e56036e432
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054251"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="a9c6e-103">Processar qualificação da inscrição</span><span class="sxs-lookup"><span data-stu-id="a9c6e-103">Process enrollment eligibility</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a9c6e-104">Este artigo explica como executar o processo de qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="a9c6e-105">No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento da qualificação da inscrição**.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="a9c6e-106">No caixa de diálogo **Executar o processamento da qualificação de inscrição no benefício**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="a9c6e-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="a9c6e-107">Campo</span><span class="sxs-lookup"><span data-stu-id="a9c6e-107">Field</span></span> | <span data-ttu-id="a9c6e-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="a9c6e-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="a9c6e-109">**Período de inscrição**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-109">**Enrollment period**</span></span> | <span data-ttu-id="a9c6e-110">O período de inscrição para processar a qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="a9c6e-111">**Pessoa jurídica em geral**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-111">**Legal entity**</span></span> | <span data-ttu-id="a9c6e-112">A entidade legal para processar a qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="a9c6e-113">**Trabalhador**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-113">**Worker**</span></span> | <span data-ttu-id="a9c6e-114">O trabalhador para processar a qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="a9c6e-115">Se você deixar esse campo em branco, a qualificação da inscrição será processada para todos os trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="a9c6e-116">**Plano de benefícios**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-116">**Benefit plan**</span></span> | <span data-ttu-id="a9c6e-117">O plano de benefícios para processar a qualificação da inscrição.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="a9c6e-118">Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="a9c6e-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="a9c6e-119">Insira informações para o processo.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="a9c6e-120">Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="a9c6e-121">Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="a9c6e-122">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-122">Select **OK**.</span></span> <span data-ttu-id="a9c6e-123">O processo será executado com os parâmetros definidos por você.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="a9c6e-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="a9c6e-125">Exibir resultados do processo</span><span class="sxs-lookup"><span data-stu-id="a9c6e-125">View Process Results</span></span>

<span data-ttu-id="a9c6e-126">Este artigo explica como exibir os resultados de processo de qualificação.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="a9c6e-127">No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Resultados do processo**.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="a9c6e-128">No formulário **Resultados do processo**, os seguintes campos são especificados:</span><span class="sxs-lookup"><span data-stu-id="a9c6e-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="a9c6e-129">Campo</span><span class="sxs-lookup"><span data-stu-id="a9c6e-129">Field</span></span> | <span data-ttu-id="a9c6e-130">descrição</span><span class="sxs-lookup"><span data-stu-id="a9c6e-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="a9c6e-131">**ID de processo**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-131">**Process ID**</span></span> | <span data-ttu-id="a9c6e-132">A identificação exclusiva da combinação de trabalhador, entidade legal e execução do processo.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="a9c6e-133">**Tipo de processo**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-133">**Process type**</span></span> | <span data-ttu-id="a9c6e-134">Isso identifica o processo que foi executado.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-134">This identifies the process that was run.</span></span> <span data-ttu-id="a9c6e-135">Por exemplo: Inscrição.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="a9c6e-136">**Carimbo de data/hora**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-136">**Time stamp**</span></span> | <span data-ttu-id="a9c6e-137">A hora em que o processo de qualificação foi executado.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="a9c6e-138">**Pessoa jurídica em geral**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-138">**Legal entity**</span></span> | <span data-ttu-id="a9c6e-139">A entidade legal especificada durante o processo de inscrição.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="a9c6e-140">**Trabalhador**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-140">**Worker**</span></span> | <span data-ttu-id="a9c6e-141">O trabalhador que foi processado.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="a9c6e-142">\*\*Plano</span><span class="sxs-lookup"><span data-stu-id="a9c6e-142">\*\*Plan</span></span> | <span data-ttu-id="a9c6e-143">O plano de benefícios para o qual o registro foi tentado.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="a9c6e-144">**Regra de qualificação**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-144">**Eligibility rule**</span></span> | <span data-ttu-id="a9c6e-145">A regra de qualificação que foi processada.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="a9c6e-146">Se um erro tiver sido encontrado antes da qualificação ser executada, ele ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="a9c6e-147">Por exemplo: se a compensação não foi definida para um trabalhador, o processo de qualificação não será executado e este campo será deixado em branco.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="a9c6e-148">**Status do resultado**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-148">**Result status**</span></span> | <span data-ttu-id="a9c6e-149">Ele será Qualificado ou Não qualificado.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="a9c6e-150">O status do resultado será inelegível se o trabalhador não atender aos critérios da regra de qualificação, se o trabalhador estiver sem informações necessárias, como uma frequência de pagamento ou uma remuneração fixa, ou se houver informações ausentes no plano de benefícios que impedem que os trabalhadores sejam inscritos.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="a9c6e-151">**Mensagem de resultado**</span><span class="sxs-lookup"><span data-stu-id="a9c6e-151">**Result message**</span></span> | <span data-ttu-id="a9c6e-152">Indica por que um trabalhador não é elegível para um plano de benefícios ou se a regra de qualificação foi aprovada.</span><span class="sxs-lookup"><span data-stu-id="a9c6e-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |



[!INCLUDE[footer-include](../includes/footer-banner.md)]