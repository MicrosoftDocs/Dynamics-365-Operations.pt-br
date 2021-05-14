---
title: Manter roteiro de um modelo de produto
description: Executar este procedimento exige que exista um modelo de configuração do produto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921256"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="92104-103">Manter roteiro de um modelo de produto</span><span class="sxs-lookup"><span data-stu-id="92104-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="92104-104">Executar este procedimento exige que exista um modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="92104-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="92104-105">Este procedimento usa o modelo de alto-falante avançado da empresa de demonstração USMF para direcioná-lo pelo processo.</span><span class="sxs-lookup"><span data-stu-id="92104-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>

## <a name="add-a-route-operation"></a><span data-ttu-id="92104-106">Adicione uma operação de roteiro</span><span class="sxs-lookup"><span data-stu-id="92104-106">Add a route operation</span></span>

1. <span data-ttu-id="92104-107">Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.</span><span class="sxs-lookup"><span data-stu-id="92104-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="92104-108">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="92104-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="92104-109">Selecione o modelo alto-falante avançado para este exercício.</span><span class="sxs-lookup"><span data-stu-id="92104-109">Select the High end speaker model for this exercise.</span></span>  
1. <span data-ttu-id="92104-110">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="92104-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="92104-111">Expandir a seção **Operações de roteiro**.</span><span class="sxs-lookup"><span data-stu-id="92104-111">Expand the **Route operations** section.</span></span>
1. <span data-ttu-id="92104-112">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="92104-112">Select **Add**.</span></span>
1. <span data-ttu-id="92104-113">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="92104-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="92104-114">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="92104-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="92104-115">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="92104-115">Select **Save**.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="92104-116">Informe os detalhes da operação do roteiro</span><span class="sxs-lookup"><span data-stu-id="92104-116">Enter route operation details</span></span>

1. <span data-ttu-id="92104-117">Selecione **Detalhes da operação do roteiro**.</span><span class="sxs-lookup"><span data-stu-id="92104-117">Select **Route operation details**.</span></span>
1. <span data-ttu-id="92104-118">No campo **Operação**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="92104-118">In the **Operation** field, enter or select a value.</span></span>
1. <span data-ttu-id="92104-119">No campo **Oper. N°**,</span><span class="sxs-lookup"><span data-stu-id="92104-119">In the **Oper. No.**</span></span> <span data-ttu-id="92104-120">insira um número.</span><span class="sxs-lookup"><span data-stu-id="92104-120">field, enter a number.</span></span>
    * <span data-ttu-id="92104-121">Os números da operação determinam a sequência no roteiro.</span><span class="sxs-lookup"><span data-stu-id="92104-121">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="92104-122">Cada propriedade em uma operação de roteiro pode ter um valor estático ou ser mapeada a um atributo.</span><span class="sxs-lookup"><span data-stu-id="92104-122">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="92104-123">O mapeamento a um atributo resultará no valor que está sendo definido como parte da configuração.</span><span class="sxs-lookup"><span data-stu-id="92104-123">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
1. <span data-ttu-id="92104-124">No campo **Grupo de roteiros**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="92104-124">In the **Route group** field, enter or select a value.</span></span>
    * <span data-ttu-id="92104-125">O grupo de roteiros determina o comportamento essencial para o custo, o consumo e a configuração.</span><span class="sxs-lookup"><span data-stu-id="92104-125">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
1. <span data-ttu-id="92104-126">Selecione a guia **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="92104-126">Select the **Setup** tab.</span></span>
1. <span data-ttu-id="92104-127">Selecione a guia **Horas**.</span><span class="sxs-lookup"><span data-stu-id="92104-127">Select the **Times** tab.</span></span>
1. <span data-ttu-id="92104-128">No campo **Processar qtd.**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="92104-128">In the **Process qty.** field, enter a number.</span></span>
    * <span data-ttu-id="92104-129">Determina a quantidade que será processada em uma operação.</span><span class="sxs-lookup"><span data-stu-id="92104-129">Determine how many will be processed during one operation.</span></span>  
1. <span data-ttu-id="92104-130">No campo **Horas/tempo**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="92104-130">In the **Hours/time** field, enter a number.</span></span>
    * <span data-ttu-id="92104-131">Digite a razão do tempo.</span><span class="sxs-lookup"><span data-stu-id="92104-131">Enter the time ratio.</span></span>  
1. <span data-ttu-id="92104-132">Marque a caixa de seleção **Definir**.</span><span class="sxs-lookup"><span data-stu-id="92104-132">Select the **Set** check box.</span></span>
1. <span data-ttu-id="92104-133">No campo **Tempo de execução**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="92104-133">In the **Run time** field, enter a number.</span></span>
    * <span data-ttu-id="92104-134">Determine o tempo de processamento para a quantidade especificada.</span><span class="sxs-lookup"><span data-stu-id="92104-134">Determine the processing time for the quantity that you have specified.</span></span>  
1. <span data-ttu-id="92104-135">Selecione a guia **Requisitos de recursos**.</span><span class="sxs-lookup"><span data-stu-id="92104-135">Select the **Resource requirements** tab.</span></span>
1. <span data-ttu-id="92104-136">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="92104-136">Select **Add**.</span></span>
1. <span data-ttu-id="92104-137">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="92104-137">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="92104-138">No campo **Tipo de requisito**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="92104-138">In the **Requirement type** field, select an option.</span></span>
    * <span data-ttu-id="92104-139">Decida se deseja especificar os recursos ou os recursos específicos que devem possuir.</span><span class="sxs-lookup"><span data-stu-id="92104-139">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
1. <span data-ttu-id="92104-140">No campo **Requisito**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="92104-140">In the **Requirement** field, enter or select a value.</span></span>
1. <span data-ttu-id="92104-141">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="92104-141">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]