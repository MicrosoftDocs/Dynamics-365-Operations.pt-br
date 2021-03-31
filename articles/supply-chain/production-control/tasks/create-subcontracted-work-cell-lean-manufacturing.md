---
title: Criar uma célula de trabalho subcontratada para lean manufacturing
description: Para modelar trabalho subcontratado para o lean manufacturing, você deve criar uma célula de trabalho associada ao fornecedor que fornece o trabalho.
author: cvocph
manager: tfehr
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 236ce97fcf4ca76f07ae5f9308cf45240590b399
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228530"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="6e6ee-103">Criar uma célula de trabalho subcontratada para lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="6e6ee-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6e6ee-104">Para modelar trabalho subcontratado para o lean manufacturing, você deve criar uma célula de trabalho associada ao fornecedor que fornece o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="6e6ee-105">Uma célula de trabalho subcontratada é vinculada ao fornecedor por meio da associação de um recurso do tipo de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="6e6ee-106">Se fizer o registro na empresa de demonstração USMF, selecione o ID da conta do fornecedor 1002 e o site 1.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="6e6ee-107">Crie um recurso de fornecedor</span><span class="sxs-lookup"><span data-stu-id="6e6ee-107">Create a vendor resource</span></span>
1. <span data-ttu-id="6e6ee-108">Vá para Recursos.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-108">Go to Resources.</span></span>
2. <span data-ttu-id="6e6ee-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-109">Click New.</span></span>
3. <span data-ttu-id="6e6ee-110">No campo Recurso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="6e6ee-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6e6ee-112">No campo Tipo, selecione 'Fornecedor'.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="6e6ee-113">No campo Fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="6e6ee-114">Crie o grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="6e6ee-114">Create the resource group</span></span>
1. <span data-ttu-id="6e6ee-115">Ir para grupos de Recurso.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="6e6ee-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-116">Click New.</span></span>
3. <span data-ttu-id="6e6ee-117">No campo grupo de Recurso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="6e6ee-118">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6e6ee-119">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6e6ee-120">Selecione o local ao qual a célula de trabalho deve ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="6e6ee-121">Em tese, um local pode representar um único local que é operado por um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="6e6ee-122">Entretanto, na maioria dos casos, os recursos subcontratados são alocados apenas ao local que solicita o trabalho subcontratado.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="6e6ee-123">Observe que os depósitos de entrada e saída das células de trabalho subcontratadas devem estar no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="6e6ee-124">No campo Local, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-124">In the Site field, type a value.</span></span>
7. <span data-ttu-id="6e6ee-125">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="6e6ee-125">@SysTaskRecorder:_RequestClose</span></span>
8. <span data-ttu-id="6e6ee-126">Marque ou desmarque a caixa de seleção Célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-126">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="6e6ee-127">No campo Depósito de entrada, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-127">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6e6ee-128">Selecione o depósito e o local usados para preparar o material para a célula de trabalho gerenciada pelo fornecedor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-128">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="6e6ee-129">Em muitos casos, depósito e a localização são modelados usando um depósito separado por fornecedor e uma localização por célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-129">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="6e6ee-130">No campo Localização de entrada, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-130">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="6e6ee-131">No campo Depósito de saída, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-131">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6e6ee-132">Defina o depósito e a localização onde o material será lançado quando as atividades subcontratadas da célula de trabalho forem lançadas.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-132">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="6e6ee-133">O depósito e a localização podem ser no local do fornecedor, se o fornecedor reportar os trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-133">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="6e6ee-134">Se preferir, o depósito e o local podem ser o local de recebimento associado à próxima etapa do fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-134">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="6e6ee-135">No campo Localização de saída, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-135">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="6e6ee-136">Expanda ou recolha a seção Calendários.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-136">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="6e6ee-137">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-137">Click Add.</span></span>
15. <span data-ttu-id="6e6ee-138">No campo Calendário, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-138">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6e6ee-139">Associe o calendário de produção da célula de trabalho ao grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-139">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="6e6ee-140">Para recursos críticos, recomendamos que você defina os calendários específicos que representam os horários de trabalho exatos as habilidades relacionadas à célula de trabalho e ao site de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-140">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="6e6ee-141">Expanda ou recolha a seção Recursos.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-141">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="6e6ee-142">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-142">Click Add.</span></span>
    * <span data-ttu-id="6e6ee-143">Um grupo de recursos subcontratado deve ter o recurso associado do tipo fornecedor que vincula o grupo de recursos à conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-143">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="6e6ee-144">No campo Recurso, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-144">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6e6ee-145">Selecione ou insira o recurso do fornecedor que você acabou de criar na subtarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-145">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="6e6ee-146">Expanda ou recolha a seção Capacidade de célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-146">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="6e6ee-147">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-147">Click Add.</span></span>
    * <span data-ttu-id="6e6ee-148">Uma célula de trabalho deve ter uma capacidade definida.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-148">A work cell must have a defined capacity.</span></span> <span data-ttu-id="6e6ee-149">Neste exemplo, criamos capacidade de produtividade de 100 peças por dia útil padrão.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-149">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="6e6ee-150">No campo Modelo de fluxo de produção, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-150">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="6e6ee-151">No campo Período de capacidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-151">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="6e6ee-152">No campo Quantidade de produtividade média, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-152">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="6e6ee-153">No campo Unidade, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-153">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="6e6ee-154">Resolver altera a Unidade.</span><span class="sxs-lookup"><span data-stu-id="6e6ee-154">ResolveChanges the Unit.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]