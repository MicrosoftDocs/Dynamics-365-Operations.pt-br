---
title: Configurar deduções
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7ee9e8f3bc0e9027e41d3aa91bd097a3f046cbb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008112"
---
# <a name="configure-deductions"></a><span data-ttu-id="5b899-102">Configurar deduções</span><span class="sxs-lookup"><span data-stu-id="5b899-102">Configure deductions</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="5b899-103">Use deduções no Microsoft Dynamics 365 Human Resources para determinar, se houver, quanto deduzir do salário de um funcionário para cada benefício.</span><span class="sxs-lookup"><span data-stu-id="5b899-103">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="5b899-104">As deduções têm data efetiva, para que você possa manter um registro histórico das informações de dedução.</span><span class="sxs-lookup"><span data-stu-id="5b899-104">Deductions are date effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="5b899-105">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Deduções**.</span><span class="sxs-lookup"><span data-stu-id="5b899-105">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="5b899-106">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5b899-106">Select **New**.</span></span>

3. <span data-ttu-id="5b899-107">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="5b899-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="5b899-108">Campo</span><span class="sxs-lookup"><span data-stu-id="5b899-108">Field</span></span> | <span data-ttu-id="5b899-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="5b899-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="5b899-110">Dedução</span><span class="sxs-lookup"><span data-stu-id="5b899-110">Deduction</span></span> | <span data-ttu-id="5b899-111">Uma ID exclusiva usada para identificar a dedução de benefícios.</span><span class="sxs-lookup"><span data-stu-id="5b899-111">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="5b899-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="5b899-112">Description</span></span> | <span data-ttu-id="5b899-113">Uma descrição para a dedução.</span><span class="sxs-lookup"><span data-stu-id="5b899-113">A description for the deduction.</span></span> |
   | <span data-ttu-id="5b899-114">Efetivação</span><span class="sxs-lookup"><span data-stu-id="5b899-114">Effective</span></span> | <span data-ttu-id="5b899-115">A data de início.</span><span class="sxs-lookup"><span data-stu-id="5b899-115">The start date.</span></span> <span data-ttu-id="5b899-116">O valor padrão é a data atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="5b899-116">The default value is the current system date.</span></span> |
   | <span data-ttu-id="5b899-117">Expiração</span><span class="sxs-lookup"><span data-stu-id="5b899-117">Expiration</span></span> | <span data-ttu-id="5b899-118">A data de término.</span><span class="sxs-lookup"><span data-stu-id="5b899-118">The end date.</span></span> <span data-ttu-id="5b899-119">O valor padrão é 12/31/2154, o que significa nunca.</span><span class="sxs-lookup"><span data-stu-id="5b899-119">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="5b899-120">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="5b899-120">Heading</span></span> | <span data-ttu-id="5b899-121">O código de cabeçalho do sistema de folha de pagamento que essa dedução usará para a parte da dedução do funcionário ao processar os benefícios da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5b899-121">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="5b899-122">Isso é usado quando você usa um provedor de folha de pagamento de terceiros.</span><span class="sxs-lookup"><span data-stu-id="5b899-122">This is used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="5b899-123">Referência para dedução na folha de pagamento do funcionário</span><span class="sxs-lookup"><span data-stu-id="5b899-123">Employee payroll deduction reference</span></span> | <span data-ttu-id="5b899-124">O código de dedução do sistema de folha de pagamento que será usado por essa dedução para a parte do funcionário da dedução ao processar os benefícios na folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5b899-124">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="5b899-125">Título do valor</span><span class="sxs-lookup"><span data-stu-id="5b899-125">Amount heading</span></span> | <span data-ttu-id="5b899-126">O código de cabeçalho do sistema de folha de pagamento que esse valor de dedução usará para a parte da dedução do funcionário ao processar os benefícios da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5b899-126">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="5b899-127">Isso costuma ser usado quando você usa um provedor de folha de pagamento de terceiros.</span><span class="sxs-lookup"><span data-stu-id="5b899-127">This is normally used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="5b899-128">Pode excluir</span><span class="sxs-lookup"><span data-stu-id="5b899-128">Can delete</span></span> | <span data-ttu-id="5b899-129">Especifica se um valor exportado do Dynamics 365 for Finance and Operations pode fazer com que o valor seja excluído no sistema de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5b899-129">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="5b899-130">Colunas emparelhadas</span><span class="sxs-lookup"><span data-stu-id="5b899-130">Paired columns</span></span> | <span data-ttu-id="5b899-131">Especifica se o valor do cabeçalho e da dedução deve ser exportado em colunas adjacentes emparelhadas para o sistema da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5b899-131">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="5b899-132">Alterar a data de efetivação</span><span class="sxs-lookup"><span data-stu-id="5b899-132">Change effective date</span></span> | <span data-ttu-id="5b899-133">A data em que a alteração da dedução do benefício entrará em vigor.</span><span class="sxs-lookup"><span data-stu-id="5b899-133">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="5b899-134">Nesta data, o sistema alterará automaticamente a dedução de benefícios e atualizará todos os planos de benefícios associados a essa dedução, desde que você execute o processamento da atualização de alterações de dedução.</span><span class="sxs-lookup"><span data-stu-id="5b899-134">On this date the system will automatically change the benefit deduction and update all benefit plans associated with this deduction, as long as you run Deduction change update processing.</span></span> |
   | <span data-ttu-id="5b899-135">Alteração da dedução concluída</span><span class="sxs-lookup"><span data-stu-id="5b899-135">Deduction change completed</span></span> | <span data-ttu-id="5b899-136">A caixa de seleção Alteração de dedução concluída será selecionada automaticamente assim que as alterações de dedução de benefícios forem concluídas pelo processamento de alterações da atualização de dedução.</span><span class="sxs-lookup"><span data-stu-id="5b899-136">The Deduction change completed check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="5b899-137">Para controlar e manter alterações na configuração das taxas de benefício, selecione **Ações** e **Manter versões**.</span><span class="sxs-lookup"><span data-stu-id="5b899-137">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="5b899-138">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5b899-138">Select **Save**.</span></span> 
