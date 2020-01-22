---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (agosto de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 08/27/2018
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
ms.search.validFrom: 2018-08-27
ms.dyn365.ops.version: Talent August 2018 update
ms.openlocfilehash: 4f6d0a32807397d5f2c0892061e54c2fed24610b
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897755"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-august-2018"></a><span data-ttu-id="bca8c-103">Novidades ou alterações no Dynamics 365 Talent - Core HR (agosto de 2018)</span><span class="sxs-lookup"><span data-stu-id="bca8c-103">What's new or changed in Dynamics 365 Talent - Core HR (August 2018)</span></span>

<span data-ttu-id="bca8c-104">**Compilação 8.1.104**</span><span class="sxs-lookup"><span data-stu-id="bca8c-104">**Build 8.1.104**</span></span>

<span data-ttu-id="bca8c-105">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="bca8c-105">This topic describes features that are either new or changed in Dynamics 365 Talent: Core HR.</span></span>

## <a name="view-expiring-records-in-manager-self-service"></a><span data-ttu-id="bca8c-106">Exibir registros em vencimento no Autoatendimento para gerentes</span><span class="sxs-lookup"><span data-stu-id="bca8c-106">View expiring records in Manager self service</span></span>

<span data-ttu-id="bca8c-107">Agora você pode exibir registros em vencimento no Autoatendimento para gerentes.</span><span class="sxs-lookup"><span data-stu-id="bca8c-107">You can now view expiring records in Manager self-service.</span></span> <span data-ttu-id="bca8c-108">As novas opções permitem que você configure quais informações estarão disponíveis para que os gerentes visualizem.</span><span class="sxs-lookup"><span data-stu-id="bca8c-108">New options are allow you to configure what information will be available for managers to view.</span></span> <span data-ttu-id="bca8c-109">Eles incluem:</span><span class="sxs-lookup"><span data-stu-id="bca8c-109">These include:</span></span>

-   <span data-ttu-id="bca8c-110">Certificados</span><span class="sxs-lookup"><span data-stu-id="bca8c-110">Certificates</span></span>

-   <span data-ttu-id="bca8c-111">Números de identificação</span><span class="sxs-lookup"><span data-stu-id="bca8c-111">Identification numbers</span></span>

-   <span data-ttu-id="bca8c-112">Períodos de experiência</span><span class="sxs-lookup"><span data-stu-id="bca8c-112">Probation periods</span></span>

-   <span data-ttu-id="bca8c-113">Triagens</span><span class="sxs-lookup"><span data-stu-id="bca8c-113">Screenings</span></span>

-   <span data-ttu-id="bca8c-114">Testes</span><span class="sxs-lookup"><span data-stu-id="bca8c-114">Tests</span></span>

<span data-ttu-id="bca8c-115">Este recurso também fornece a capacidade de especificar o intervalo de dias para procurar por registros em vencimento.</span><span class="sxs-lookup"><span data-stu-id="bca8c-115">This feature also gives you the ability to specify the range of days in which to look for expiring records.</span></span>

## <a name="configurable-transfer-actions"></a><span data-ttu-id="bca8c-116">Ações de transferência configuráveis</span><span class="sxs-lookup"><span data-stu-id="bca8c-116">Configurable transfer actions</span></span>

<span data-ttu-id="bca8c-117">Você pode configurar por função as opções que estarão disponíveis durante a entrada de uma ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="bca8c-117">You can configure by role the options that will be available during the entry of a transfer request.</span></span> <span data-ttu-id="bca8c-118">Este recurso fornece flexibilidade adicional nas funções em uma organização.</span><span class="sxs-lookup"><span data-stu-id="bca8c-118">This feature provides additional flexibility across the roles in an organization.</span></span>

<span data-ttu-id="bca8c-119">Por exemplo, gerentes que solicitam transferências de funcionário podem não ter acesso para sugerir ou inserir valores de remuneração ou selecionar as listas de tarefas a serem associadas à solicitação de transferência.</span><span class="sxs-lookup"><span data-stu-id="bca8c-119">For example, managers requesting employee transfers may not have access to suggest or enter compensation amounts or select the task lists that will be associated with the transfer request.</span></span> <span data-ttu-id="bca8c-120">Nesse caso, os gerentes podem criar e enviar solicitações de transferência, mas não têm permissão para inserir a remuneração ou atribuições da lista de tarefas.</span><span class="sxs-lookup"><span data-stu-id="bca8c-120">In this case, managers can create and submit transfer requests but are not allowed to enter compensation or task list assignments.</span></span> <span data-ttu-id="bca8c-121">Nesta mesma configuração, o RH poderá atribuir os novos valores de remuneração bem como atribuir todas as listas de verificação adicionais a serem concluídas em decorrência da conclusão da transferência.</span><span class="sxs-lookup"><span data-stu-id="bca8c-121">In this same configuration, HR will be able to assign the new compensation values as well as assign any additional checklists to be completed as a result of the transfer completing.</span></span>

<span data-ttu-id="bca8c-122">Por padrão, as novas opções de configuração estão definidas para não alterar os recursos antes desta atualização.</span><span class="sxs-lookup"><span data-stu-id="bca8c-122">By default, the new configuration options are set to not change the capabilities prior to this update.</span></span>

## <a name="leave-and-absence"></a><span data-ttu-id="bca8c-123">Licença e ausência</span><span class="sxs-lookup"><span data-stu-id="bca8c-123">Leave and absence</span></span>

<span data-ttu-id="bca8c-124">Há agora campos adicionais de datas disponíveis em Licenças e ausências.</span><span class="sxs-lookup"><span data-stu-id="bca8c-124">There are now additional Date fields available in Leave and Absence.</span></span>

<span data-ttu-id="bca8c-125">Com esse recurso, você pode definir base da competência no nível do plano para usar datas específicas do funcionário.</span><span class="sxs-lookup"><span data-stu-id="bca8c-125">With this feature you can set the accrual period basis at the plan level to use specific employee dates.</span></span> <span data-ttu-id="bca8c-126">Isso permite que datas diferentes da data de início do plano sejam usadas durante o processo de competência da licença.</span><span class="sxs-lookup"><span data-stu-id="bca8c-126">This allows for dates other than the plan start date to be used during the leave accrual process.</span></span> <span data-ttu-id="bca8c-127">As opções para datas específicas de funcionários incluem os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="bca8c-127">Options for employee specific dates include the following values:</span></span>

-   <span data-ttu-id="bca8c-128">Personalizada (disponível antes desta atualização)</span><span class="sxs-lookup"><span data-stu-id="bca8c-128">Custom (available prior to this update)</span></span>

-   <span data-ttu-id="bca8c-129">Data de aniversário</span><span class="sxs-lookup"><span data-stu-id="bca8c-129">Anniversary date</span></span>

-   <span data-ttu-id="bca8c-130">Data original de contratação</span><span class="sxs-lookup"><span data-stu-id="bca8c-130">Original hire date</span></span>

-   <span data-ttu-id="bca8c-131">Aniversário de tempo de serviço</span><span class="sxs-lookup"><span data-stu-id="bca8c-131">Seniority date</span></span>

-   <span data-ttu-id="bca8c-132">Data inicial ajustada do trabalhador</span><span class="sxs-lookup"><span data-stu-id="bca8c-132">Worker’s adjusted start date</span></span>

-   <span data-ttu-id="bca8c-133">Data inicial do trabalhador</span><span class="sxs-lookup"><span data-stu-id="bca8c-133">Worker’s start date</span></span>

<span data-ttu-id="bca8c-134">Quando configurado para usar uma das datas específicas do funcionário, o processo de inscrição usará a data especificada para calcular os períodos de competência.</span><span class="sxs-lookup"><span data-stu-id="bca8c-134">When configured to use one of the employee specific dates, the enrollment process will use the specified date to calculate the accrual periods.</span></span> <span data-ttu-id="bca8c-135">A base do período de competência é exibida também na inscrição do plano do funcionário para ajudar a entender o que está sendo usado durante o processo de competência.</span><span class="sxs-lookup"><span data-stu-id="bca8c-135">The accrual period basis is also displayed on the employee’s plan enrollment to help you understand what’s being used during the accrual process.</span></span>

## <a name="microsoft-word-integration"></a><span data-ttu-id="bca8c-136">Integração com o Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="bca8c-136">Microsoft Word integration</span></span>

<span data-ttu-id="bca8c-137">Os modelos de documento foram habilitados em todo o Core HR.</span><span class="sxs-lookup"><span data-stu-id="bca8c-137">Document templates have been enabled throughout Core HR.</span></span> <span data-ttu-id="bca8c-138">Esse recurso permite criar cartas e relatórios baseados nos modelos do Word que você cria.</span><span class="sxs-lookup"><span data-stu-id="bca8c-138">This feature allows you to create letters and reports based on Word templates that you create.</span></span>

<span data-ttu-id="bca8c-139">Informações adicionais sobre esse recurso estão disponível em [Tutorial de integração do Office](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).</span><span class="sxs-lookup"><span data-stu-id="bca8c-139">Additional information about this feature is available in the [Office integration tutorial](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).</span></span>


## <a name="other-fixes"></a><span data-ttu-id="bca8c-140">Outras correções</span><span class="sxs-lookup"><span data-stu-id="bca8c-140">Other fixes</span></span>

<span data-ttu-id="bca8c-141">Essa versão também inclui um número de correções, a adição de novas entidades, correções de entidades existentes e alterações a etiquetas localizadas.</span><span class="sxs-lookup"><span data-stu-id="bca8c-141">This release also includes a number of bug fixes, the addition of new entities, fixes to existing entities, and localized label changes.</span></span>
