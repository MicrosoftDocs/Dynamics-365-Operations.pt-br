---
title: "Criar um novo layout de depósito"
description: "Este procedimento mostra como configurar informações sobre as localizações de um depósito."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 11ad27e68e8eb499b2cf8e477d3dbf51d930b736
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="6d6c5-103">Criar um novo layout de depósito</span><span class="sxs-lookup"><span data-stu-id="6d6c5-103">Create a new warehouse layout</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6d6c5-104">Este procedimento mostra como configurar informações sobre as localizações de um depósito.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-104">This procedure shows you how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="6d6c5-105">Aplica-se apenas a depósitos criados usando o "armazenamento básico” no módulo de gerenciamento de estoque, não a depósitos criados no módulo de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="6d6c5-106">Você pode usar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="6d6c5-107">Definir a capacidade do local padrão</span><span class="sxs-lookup"><span data-stu-id="6d6c5-107">Set the default location capacity</span></span>
1. <span data-ttu-id="6d6c5-108">Vá para Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-108">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="6d6c5-109">Clique na guia Locais.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-109">Click the Locations tab.</span></span>
3. <span data-ttu-id="6d6c5-110">No campo de largura padrão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-110">In the Standard width field, enter a number.</span></span>
4. <span data-ttu-id="6d6c5-111">No campo de profundidade padrão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-111">In the Standard depth field, enter a number.</span></span>
5. <span data-ttu-id="6d6c5-112">No campo de altura padrão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-112">In the Standard height field, enter a number.</span></span>
6. <span data-ttu-id="6d6c5-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-113">Click Save.</span></span>
7. <span data-ttu-id="6d6c5-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="6d6c5-115">Definir o formato do nome da localização</span><span class="sxs-lookup"><span data-stu-id="6d6c5-115">Define the location name format</span></span>
1. <span data-ttu-id="6d6c5-116">Vá para Gerenciamento do estoque > Configuração > Divisão do estoque > Depósitos.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-116">Go to Inventory management > Setup > Inventory breakdown > Warehouses.</span></span>
2. <span data-ttu-id="6d6c5-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-117">Click New.</span></span>
3. <span data-ttu-id="6d6c5-118">No campo Depósito, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-118">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="6d6c5-119">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="6d6c5-120">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-120">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="6d6c5-121">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="6d6c5-122">Alternar a expansão da seção Nomes de local.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-122">Toggle the expansion of the Location names section.</span></span>
    * <span data-ttu-id="6d6c5-123">As opções nesta seção definem o formato padrão para nomes da localização.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-123">The options in this section define the default format for location names.</span></span> <span data-ttu-id="6d6c5-124">Em nosso exemplo, incluiremos o número do corredor, o número do rack e o número da prateleira.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-124">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
8. <span data-ttu-id="6d6c5-125">Definir a opção do corredor para Sim.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-125">Set the Include aisle option to Yes.</span></span>
9. <span data-ttu-id="6d6c5-126">Definir a opção do rack para Sim.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-126">Set the Include rack option to Yes.</span></span>
10. <span data-ttu-id="6d6c5-127">No campo Formato, digite o valor para o rack.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-127">In the Format field, for the rack, type a value.</span></span>
    * <span data-ttu-id="6d6c5-128">Por exemplo: -##</span><span class="sxs-lookup"><span data-stu-id="6d6c5-128">For example: -##</span></span>  
11. <span data-ttu-id="6d6c5-129">Definir a opção Incluir prateleira como Sim.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-129">Set the Include shelf option to Yes.</span></span>
12. <span data-ttu-id="6d6c5-130">No campo Formato, digite o valor para a prateleira.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-130">In the Format field, for the shelf, type a value.</span></span>
    * <span data-ttu-id="6d6c5-131">Por exemplo: -##</span><span class="sxs-lookup"><span data-stu-id="6d6c5-131">For example: -##</span></span>  

## <a name="define-warehouse-locations"></a><span data-ttu-id="6d6c5-132">Definir locais de depósito</span><span class="sxs-lookup"><span data-stu-id="6d6c5-132">Define warehouse locations</span></span>
1. <span data-ttu-id="6d6c5-133">No Painel de Ação, clique em Depósito.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-133">On the Action Pane, click Warehouse.</span></span>
2. <span data-ttu-id="6d6c5-134">Clique em Assistente de localização.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-134">Click Location Wizard.</span></span>
3. <span data-ttu-id="6d6c5-135">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-135">Click Next.</span></span>
4. <span data-ttu-id="6d6c5-136">Desmarque a opção de Docas de saída</span><span class="sxs-lookup"><span data-stu-id="6d6c5-136">De-select the Outbound docks option</span></span>
5. <span data-ttu-id="6d6c5-137">Desmarque a opção de Locais de massa</span><span class="sxs-lookup"><span data-stu-id="6d6c5-137">De-select the Bulk locations option</span></span>
6. <span data-ttu-id="6d6c5-138">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-138">Click Next.</span></span>
7. <span data-ttu-id="6d6c5-139">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-139">Click Next.</span></span>
8. <span data-ttu-id="6d6c5-140">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-140">Click Next.</span></span>
9. <span data-ttu-id="6d6c5-141">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-141">Click Next.</span></span>
10. <span data-ttu-id="6d6c5-142">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-142">Click Next.</span></span>
11. <span data-ttu-id="6d6c5-143">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-143">Click Next.</span></span>
12. <span data-ttu-id="6d6c5-144">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-144">Click Next.</span></span>
    * <span data-ttu-id="6d6c5-145">Observe que as dimensões físicas mostradas nessa página são aquelas configuradas que você definiu no início deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-145">Note that the physical dimensions shown on this page are the ones that you set at the start of this procedure.</span></span>  
13. <span data-ttu-id="6d6c5-146">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-146">Click Next.</span></span>
14. <span data-ttu-id="6d6c5-147">Clique em Finish (Concluir).</span><span class="sxs-lookup"><span data-stu-id="6d6c5-147">Click Finish.</span></span>
15. <span data-ttu-id="6d6c5-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-148">Close the page.</span></span>
16. <span data-ttu-id="6d6c5-149">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="6d6c5-149">Refresh the page.</span></span>

