--- 
title: "Criar uma célula de trabalho subcontratada para lean manufacturing"
description: "Para modelar trabalho subcontratado para o lean manufacturing, você deve criar uma célula de trabalho associada ao fornecedor que fornece o trabalho."
author: cvocph
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fc8dc0bc29c6bdb662c46808491abf5395f0be5d
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="8267a-103">Criar uma célula de trabalho subcontratada para lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="8267a-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8267a-104">Para modelar trabalho subcontratado para o lean manufacturing, você deve criar uma célula de trabalho associada ao fornecedor que fornece o trabalho.</span><span class="sxs-lookup"><span data-stu-id="8267a-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="8267a-105">Uma célula de trabalho subcontratada é vinculada ao fornecedor por meio da associação de um recurso do tipo de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8267a-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="8267a-106">Se fizer o registro na empresa de demonstração USMF, selecione o ID da conta do fornecedor 1002 e o site 1.</span><span class="sxs-lookup"><span data-stu-id="8267a-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="8267a-107">Crie um recurso de fornecedor</span><span class="sxs-lookup"><span data-stu-id="8267a-107">Create a vendor resource</span></span>
1. <span data-ttu-id="8267a-108">Vá para Recursos.</span><span class="sxs-lookup"><span data-stu-id="8267a-108">Go to Resources.</span></span>
2. <span data-ttu-id="8267a-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8267a-109">Click New.</span></span>
3. <span data-ttu-id="8267a-110">No campo Recurso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8267a-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="8267a-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8267a-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8267a-112">No campo Tipo, selecione 'Fornecedor'.</span><span class="sxs-lookup"><span data-stu-id="8267a-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="8267a-113">No campo Fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="8267a-114">Crie o grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="8267a-114">Create the resource group</span></span>
1. <span data-ttu-id="8267a-115">Ir para grupos de Recurso.</span><span class="sxs-lookup"><span data-stu-id="8267a-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="8267a-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8267a-116">Click New.</span></span>
3. <span data-ttu-id="8267a-117">No campo grupo de Recurso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8267a-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="8267a-118">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8267a-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8267a-119">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8267a-120">Selecione o local ao qual a célula de trabalho deve ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="8267a-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="8267a-121">Em tese, um local pode representar um único local que é operado por um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8267a-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="8267a-122">Entretanto, na maioria dos casos, os recursos subcontratados são alocados apenas ao local que solicita o trabalho subcontratado.</span><span class="sxs-lookup"><span data-stu-id="8267a-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="8267a-123">Observe que os depósitos de entrada e saída das células de trabalho subcontratadas devem estar no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="8267a-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="8267a-124">No campo Local, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8267a-124">In the Site field, type a value.</span></span>
7. @SysTaskRecorder:_RequestClose
8. <span data-ttu-id="8267a-125">Marque ou desmarque a caixa de seleção Célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8267a-125">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="8267a-126">No campo Depósito de entrada, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-126">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8267a-127">Selecione o depósito e o local usados para preparar o material para a célula de trabalho gerenciada pelo fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8267a-127">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="8267a-128">Em muitos casos, depósito e a localização são modelados usando um depósito separado por fornecedor e uma localização por célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8267a-128">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="8267a-129">No campo Localização de entrada, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-129">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="8267a-130">No campo Depósito de saída, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-130">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8267a-131">Defina o depósito e a localização onde o material será lançado quando as atividades subcontratadas da célula de trabalho forem lançadas.</span><span class="sxs-lookup"><span data-stu-id="8267a-131">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="8267a-132">O depósito e a localização podem ser no local do fornecedor, se o fornecedor reportar os trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="8267a-132">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="8267a-133">Se preferir, o depósito e o local podem ser o local de recebimento associado à próxima etapa do fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="8267a-133">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="8267a-134">No campo Localização de saída, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-134">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="8267a-135">Expanda ou recolha a seção Calendários.</span><span class="sxs-lookup"><span data-stu-id="8267a-135">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="8267a-136">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="8267a-136">Click Add.</span></span>
15. <span data-ttu-id="8267a-137">No campo Calendário, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-137">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8267a-138">Associe o calendário de produção da célula de trabalho ao grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="8267a-138">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="8267a-139">Para recursos críticos, recomendamos que você defina os calendários específicos que representam os horários de trabalho exatos as habilidades relacionadas à célula de trabalho e ao site de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8267a-139">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="8267a-140">Expanda ou recolha a seção Recursos.</span><span class="sxs-lookup"><span data-stu-id="8267a-140">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="8267a-141">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="8267a-141">Click Add.</span></span>
    * <span data-ttu-id="8267a-142">Um grupo de recursos subcontratado deve ter o recurso associado do tipo fornecedor que vincula o grupo de recursos à conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8267a-142">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="8267a-143">No campo Recurso, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-143">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8267a-144">Selecione ou insira o recurso do fornecedor que você acabou de criar na subtarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="8267a-144">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="8267a-145">Expanda ou recolha a seção Capacidade de célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8267a-145">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="8267a-146">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="8267a-146">Click Add.</span></span>
    * <span data-ttu-id="8267a-147">Uma célula de trabalho deve ter uma capacidade definida.</span><span class="sxs-lookup"><span data-stu-id="8267a-147">A work cell must have a defined capacity.</span></span> <span data-ttu-id="8267a-148">Neste exemplo, criamos capacidade de produtividade de 100 peças por dia útil padrão.</span><span class="sxs-lookup"><span data-stu-id="8267a-148">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="8267a-149">No campo Modelo de fluxo de produção, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-149">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="8267a-150">No campo Período de capacidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="8267a-150">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="8267a-151">No campo Quantidade de produtividade média, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8267a-151">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="8267a-152">No campo Unidade, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8267a-152">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="8267a-153">Resolver altera a Unidade.</span><span class="sxs-lookup"><span data-stu-id="8267a-153">ResolveChanges the Unit.</span></span>


