--- 
title: Configurar transportadoras
description: "Este procedimento descreve como montar uma transportadora e definir detalhes como serviço, modo de envio, proposta de transporte, restrições de transporte e taxa de envio."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6e9ce934016139832b474d60d7dfc2e845434da2
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="89779-103">Configurar transportadoras</span><span class="sxs-lookup"><span data-stu-id="89779-103">Set up shipping carriers</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="89779-104">Este procedimento descreve como montar uma transportadora e definir detalhes como serviço, modo de envio, proposta de transporte, restrições de transporte e taxa de envio.</span><span class="sxs-lookup"><span data-stu-id="89779-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="89779-105">Um coordenador de transporte pode então atribuir uma transportadora a uma carga de entrada ou de saída.</span><span class="sxs-lookup"><span data-stu-id="89779-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="89779-106">Crie uma nova transportadora</span><span class="sxs-lookup"><span data-stu-id="89779-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="89779-107">Vá para Gerenciamento de transporte > Configuração > Transportadoras > Transportadoras de envio.</span><span class="sxs-lookup"><span data-stu-id="89779-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="89779-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="89779-108">Click New.</span></span>
3. <span data-ttu-id="89779-109">No campo Transportadora, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="89779-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="89779-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="89779-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="89779-111">No campo Modo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="89779-112">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="89779-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="89779-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="89779-114">Preencha as informações gerais da transportadora</span><span class="sxs-lookup"><span data-stu-id="89779-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="89779-115">Ative a expansão da seção Visão geral.</span><span class="sxs-lookup"><span data-stu-id="89779-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="89779-116">Marque ou desmarque a caixa de seleção Ativar a transportadora.</span><span class="sxs-lookup"><span data-stu-id="89779-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="89779-117">No campo Fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="89779-118">Selecione a conta do fornecedor para atribuí-la a transportadora.</span><span class="sxs-lookup"><span data-stu-id="89779-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="89779-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="89779-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="89779-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="89779-121">No campo Tipo de proposta de transporte, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="89779-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="89779-122">Selecione Manual para usar a página Proposta de Transporte, ou selecione EDI para atualizar a proposta usando Intercâmbio Eletrônico de Dados (EDI).</span><span class="sxs-lookup"><span data-stu-id="89779-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="89779-123">Marque ou desmarque a caixa de seleção Ativar a transportadora.</span><span class="sxs-lookup"><span data-stu-id="89779-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="89779-124">Crie os serviços necessários para a transportadora</span><span class="sxs-lookup"><span data-stu-id="89779-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="89779-125">Ative a expansão da seção Serviços.</span><span class="sxs-lookup"><span data-stu-id="89779-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="89779-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="89779-126">Click New.</span></span>
3. <span data-ttu-id="89779-127">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="89779-128">No campo Serviço da transportadora, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="89779-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="89779-129">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="89779-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="89779-130">No campo Método de transporte, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="89779-131">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="89779-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="89779-132">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="89779-133">Configure o endereço da transportadora (opcional)</span><span class="sxs-lookup"><span data-stu-id="89779-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="89779-134">Alternar a expansão da seção Endereços.</span><span class="sxs-lookup"><span data-stu-id="89779-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="89779-135">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="89779-135">Click New.</span></span>
3. <span data-ttu-id="89779-136">No campo Nome ou Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="89779-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="89779-137">No campo País/região, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="89779-138">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="89779-139">No campo CEP/código postal, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="89779-140">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="89779-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="89779-141">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="89779-142">No campo Rua, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="89779-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="89779-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="89779-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="89779-144">Configure o perfil de classificação para a transportadora.</span><span class="sxs-lookup"><span data-stu-id="89779-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="89779-145">Ative a expansão da seção Perfis de classificação.</span><span class="sxs-lookup"><span data-stu-id="89779-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="89779-146">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="89779-146">Click New.</span></span>
3. <span data-ttu-id="89779-147">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="89779-148">No campo Perfil de classificação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="89779-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="89779-149">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="89779-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="89779-150">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="89779-151">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="89779-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="89779-152">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="89779-153">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="89779-154">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="89779-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="89779-155">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="89779-156">No campo Mecanismo de classificação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="89779-157">Selecione o Mecanismo de taxa que está de acordo com o contrato que você tem com a transportadora.</span><span class="sxs-lookup"><span data-stu-id="89779-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="89779-158">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="89779-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="89779-159">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="89779-160">No campo Mestre de taxa, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="89779-161">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="89779-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="89779-162">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="89779-163">No campo Mecanismo de tempo de trânsito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89779-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="89779-164">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="89779-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="89779-165">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="89779-165">Click Save.</span></span>


