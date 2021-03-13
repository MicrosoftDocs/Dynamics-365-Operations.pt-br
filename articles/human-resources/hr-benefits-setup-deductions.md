---
title: Configurar deduções
description: Use deduções no Microsoft Dynamics 365 Human Resources para determinar, se houver, quanto deduzir do salário de um funcionário para cada benefício.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c84e44e784e18c82098d63909f198049ae5f995c
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111483"
---
# <a name="configure-deductions"></a><span data-ttu-id="33a1e-103">Configurar deduções</span><span class="sxs-lookup"><span data-stu-id="33a1e-103">Configure deductions</span></span>

<span data-ttu-id="33a1e-104">Use deduções no Microsoft Dynamics 365 Human Resources para determinar, se houver, quanto deduzir do salário de um funcionário para cada benefício.</span><span class="sxs-lookup"><span data-stu-id="33a1e-104">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="33a1e-105">As deduções têm data efetiva, para que você possa manter um registro histórico das informações de dedução.</span><span class="sxs-lookup"><span data-stu-id="33a1e-105">Deductions are date-effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="33a1e-106">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Deduções**.</span><span class="sxs-lookup"><span data-stu-id="33a1e-106">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="33a1e-107">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="33a1e-107">Select **New**.</span></span>

3. <span data-ttu-id="33a1e-108">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="33a1e-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="33a1e-109">Campo</span><span class="sxs-lookup"><span data-stu-id="33a1e-109">Field</span></span> | <span data-ttu-id="33a1e-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="33a1e-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="33a1e-111">**Dedução**</span><span class="sxs-lookup"><span data-stu-id="33a1e-111">**Deduction**</span></span> | <span data-ttu-id="33a1e-112">Uma ID exclusiva usada para identificar a dedução de benefícios.</span><span class="sxs-lookup"><span data-stu-id="33a1e-112">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="33a1e-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="33a1e-113">**Description**</span></span> | <span data-ttu-id="33a1e-114">Uma descrição para a dedução.</span><span class="sxs-lookup"><span data-stu-id="33a1e-114">A description for the deduction.</span></span> |
   | <span data-ttu-id="33a1e-115">**Efetivação**</span><span class="sxs-lookup"><span data-stu-id="33a1e-115">**Effective**</span></span> | <span data-ttu-id="33a1e-116">A data de início.</span><span class="sxs-lookup"><span data-stu-id="33a1e-116">The start date.</span></span> <span data-ttu-id="33a1e-117">O valor padrão é a data atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="33a1e-117">The default value is the current system date.</span></span> |
   | <span data-ttu-id="33a1e-118">**Expiração**</span><span class="sxs-lookup"><span data-stu-id="33a1e-118">**Expiration**</span></span> | <span data-ttu-id="33a1e-119">A data de término.</span><span class="sxs-lookup"><span data-stu-id="33a1e-119">The end date.</span></span> <span data-ttu-id="33a1e-120">O valor padrão é 12/31/2154, o que significa nunca.</span><span class="sxs-lookup"><span data-stu-id="33a1e-120">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="33a1e-121">**Cabeçalho**</span><span class="sxs-lookup"><span data-stu-id="33a1e-121">**Heading**</span></span> | <span data-ttu-id="33a1e-122">O código de cabeçalho do sistema de folha de pagamento que essa dedução usará para a parte da dedução do funcionário ao processar os benefícios da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="33a1e-122">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="33a1e-123">Isso é usado quando você usa um provedor de folha de pagamento de terceiros.</span><span class="sxs-lookup"><span data-stu-id="33a1e-123">This is used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="33a1e-124">**Referência para dedução na folha de pagamento do funcionário**</span><span class="sxs-lookup"><span data-stu-id="33a1e-124">**Employee payroll deduction reference**</span></span> | <span data-ttu-id="33a1e-125">O código de dedução do sistema de folha de pagamento que será usado por essa dedução para a parte do funcionário da dedução ao processar os benefícios na folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="33a1e-125">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="33a1e-126">**Título do valor**</span><span class="sxs-lookup"><span data-stu-id="33a1e-126">**Amount heading**</span></span> | <span data-ttu-id="33a1e-127">O código de cabeçalho do sistema de folha de pagamento que esse valor de dedução usará para a parte da dedução do funcionário ao processar os benefícios da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="33a1e-127">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="33a1e-128">Isso costuma ser usado quando você usa um provedor de folha de pagamento de terceiros.</span><span class="sxs-lookup"><span data-stu-id="33a1e-128">This is normally used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="33a1e-129">**Pode excluir**</span><span class="sxs-lookup"><span data-stu-id="33a1e-129">**Can delete**</span></span> | <span data-ttu-id="33a1e-130">Especifica se um valor exportado do Dynamics 365 for Finance and Operations pode fazer com que o valor seja excluído no sistema de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="33a1e-130">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="33a1e-131">**Colunas emparelhadas**</span><span class="sxs-lookup"><span data-stu-id="33a1e-131">**Paired columns**</span></span> | <span data-ttu-id="33a1e-132">Especifica se o valor do cabeçalho e da dedução deve ser exportado em colunas adjacentes emparelhadas para o sistema da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="33a1e-132">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="33a1e-133">**Alterar a data de efetivação**</span><span class="sxs-lookup"><span data-stu-id="33a1e-133">**Change effective date**</span></span> | <span data-ttu-id="33a1e-134">A data em que a alteração da dedução do benefício entrará em vigor.</span><span class="sxs-lookup"><span data-stu-id="33a1e-134">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="33a1e-135">Nesta data, o sistema altera automaticamente a dedução de benefícios e atualiza todos os planos de benefícios associados a essa dedução, desde que você execute o processamento da **atualização de alterações de dedução**.</span><span class="sxs-lookup"><span data-stu-id="33a1e-135">On this date, the system automatically changes the benefit deduction and updates all benefit plans associated with this deduction, as long as you run **Deduction change update** processing.</span></span> |
   | <span data-ttu-id="33a1e-136">**Alteração da dedução concluída**</span><span class="sxs-lookup"><span data-stu-id="33a1e-136">**Deduction change completed**</span></span> | <span data-ttu-id="33a1e-137">A caixa de seleção **Alteração de dedução concluída** será selecionada automaticamente assim que as alterações de dedução de benefícios forem concluídas pelo processamento de alterações da atualização de dedução.</span><span class="sxs-lookup"><span data-stu-id="33a1e-137">The **Deduction change completed** check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="33a1e-138">Para controlar e manter alterações na configuração das taxas de benefício, selecione **Ações** e **Manter versões**.</span><span class="sxs-lookup"><span data-stu-id="33a1e-138">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="33a1e-139">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33a1e-139">Select **Save**.</span></span> 
