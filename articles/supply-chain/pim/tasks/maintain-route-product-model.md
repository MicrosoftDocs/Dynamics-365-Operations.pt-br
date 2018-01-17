--- 
title: Manter um roteiro para um modelo de produtos
description: "Executar este procedimento exige que exista um modelo de configuração do produto."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 637614a17513ec68c0a180f46606ac8430c00133
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---
# <a name="maintain-a-route-for-a-product-model"></a><span data-ttu-id="57597-103">Manter um roteiro para um modelo de produtos</span><span class="sxs-lookup"><span data-stu-id="57597-103">Maintain a route for a product model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57597-104">Executar este procedimento exige que exista um modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="57597-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="57597-105">Este procedimento usa o modelo de alto-falante avançado da empresa de demonstração USMF para direcioná-lo pelo processo.</span><span class="sxs-lookup"><span data-stu-id="57597-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="57597-106">Adicione uma operação de roteiro</span><span class="sxs-lookup"><span data-stu-id="57597-106">Add a route operation</span></span>
1. <span data-ttu-id="57597-107">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="57597-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="57597-108">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="57597-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="57597-109">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="57597-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="57597-110">Selecione o modelo alto-falante avançado para este exercício.</span><span class="sxs-lookup"><span data-stu-id="57597-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="57597-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="57597-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="57597-112">Expandir a seção Operações de roteiro.</span><span class="sxs-lookup"><span data-stu-id="57597-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="57597-113">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="57597-113">Click Add.</span></span>
7. <span data-ttu-id="57597-114">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="57597-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="57597-115">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="57597-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="57597-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57597-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="57597-117">Informe os detalhes da operação do roteiro</span><span class="sxs-lookup"><span data-stu-id="57597-117">Enter route operation details</span></span>
1. <span data-ttu-id="57597-118">Clique em Detalhes da operação do roteiro.</span><span class="sxs-lookup"><span data-stu-id="57597-118">Click Route operation details.</span></span>
2. <span data-ttu-id="57597-119">No campo Operação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="57597-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="57597-120">No campo Nº</span><span class="sxs-lookup"><span data-stu-id="57597-120">In the Oper.</span></span> <span data-ttu-id="57597-121">Não.</span><span class="sxs-lookup"><span data-stu-id="57597-121">No.</span></span> <span data-ttu-id="57597-122">insira um número.</span><span class="sxs-lookup"><span data-stu-id="57597-122">field, enter a number.</span></span>
    * <span data-ttu-id="57597-123">Os números da operação determinam a sequência no roteiro.</span><span class="sxs-lookup"><span data-stu-id="57597-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="57597-124">Cada propriedade em uma operação de roteiro pode ter um valor estático ou ser mapeada a um atributo.</span><span class="sxs-lookup"><span data-stu-id="57597-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="57597-125">O mapeamento a um atributo resultará no valor que está sendo definido como parte da configuração.</span><span class="sxs-lookup"><span data-stu-id="57597-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="57597-126">No campo Grupo de roteiro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="57597-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="57597-127">O grupo de roteiros determina o comportamento essencial para o custo, o consumo e a configuração.</span><span class="sxs-lookup"><span data-stu-id="57597-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="57597-128">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="57597-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="57597-129">Clique na guia Horas.</span><span class="sxs-lookup"><span data-stu-id="57597-129">Click the Times tab.</span></span>
7. <span data-ttu-id="57597-130">Em Processar quantidade. insira um número.</span><span class="sxs-lookup"><span data-stu-id="57597-130">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="57597-131">Determina a quantidade que será processada em uma operação.</span><span class="sxs-lookup"><span data-stu-id="57597-131">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="57597-132">No campo Horas/tempo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="57597-132">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="57597-133">Digite a razão do tempo.</span><span class="sxs-lookup"><span data-stu-id="57597-133">Enter the time ratio.</span></span>  
9. <span data-ttu-id="57597-134">Marque a caixa de seleção Definir.</span><span class="sxs-lookup"><span data-stu-id="57597-134">Select the Set check box.</span></span>
10. <span data-ttu-id="57597-135">No campo Tempo de execução, insira um número.</span><span class="sxs-lookup"><span data-stu-id="57597-135">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="57597-136">Determine o tempo de processamento para a quantidade especificada.</span><span class="sxs-lookup"><span data-stu-id="57597-136">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="57597-137">Clique na guia Requisitos de recurso.</span><span class="sxs-lookup"><span data-stu-id="57597-137">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="57597-138">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="57597-138">Click Add.</span></span>
13. <span data-ttu-id="57597-139">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="57597-139">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="57597-140">No campo Tipo de requisição, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="57597-140">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="57597-141">Decida se deseja especificar os recursos ou os recursos específicos que devem possuir.</span><span class="sxs-lookup"><span data-stu-id="57597-141">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="57597-142">No campo Requisito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="57597-142">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="57597-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="57597-143">Click OK.</span></span>


