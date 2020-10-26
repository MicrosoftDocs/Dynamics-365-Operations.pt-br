---
title: Configurar transportadoras
description: Este tópico descreve como montar uma transportadora e definir detalhes como serviço, modo de envio, proposta de transporte, restrições de transporte e taxa de envio.
author: ShylaThompson
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69e711ad2011703efa450d97575784aaee3137dd
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982322"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="1fdd0-103">Configurar transportadoras</span><span class="sxs-lookup"><span data-stu-id="1fdd0-103">Set up shipping carriers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1fdd0-104">Este tópico descreve como montar uma transportadora e definir detalhes como serviço, modo de envio, proposta de transporte, restrições de transporte e taxa de envio.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-104">This topic shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="1fdd0-105">Um coordenador de transporte pode então atribuir uma transportadora a uma carga de entrada ou de saída.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="1fdd0-106">Crie uma nova transportadora</span><span class="sxs-lookup"><span data-stu-id="1fdd0-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="1fdd0-107">Acesse **Painel de navegação > Módulos > Gerenciamento de transporte > Configuração > Transportadoras > Transportadoras de envio**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-107">Go to **Navigation pane > Modules > Transportation management > Setup > Carriers > Shipping carriers**.</span></span>
2. <span data-ttu-id="1fdd0-108">Selecione **Novo** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-108">Select **New** on the Action Pane.</span></span>
3. <span data-ttu-id="1fdd0-109">No campo **Transportadora**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-109">In the **Shipping carrier** field, type a value.</span></span>
4. <span data-ttu-id="1fdd0-110">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="1fdd0-111">No campo **Modo**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-111">In the **Mode** field, select an option from the drop-down menu.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="1fdd0-112">Preencha as informações gerais da transportadora</span><span class="sxs-lookup"><span data-stu-id="1fdd0-112">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="1fdd0-113">Ative a expansão da seção **Visão geral**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-113">Toggle the expansion of the **Overview** section.</span></span>
2. <span data-ttu-id="1fdd0-114">Marque ou desmarque a caixa de seleção **Ativar a transportadora**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-114">Check or uncheck the **Activate shipping carrier** checkbox.</span></span>
3. <span data-ttu-id="1fdd0-115">No campo **Conta de Fornecedor**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-115">In the **Vendor account** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="1fdd0-116">Selecione a conta do fornecedor para atribuí-la a transportadora.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-116">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="1fdd0-117">No campo **Tipo de proposta de transporte**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-117">In the **Transportation tender type** field, select an option.</span></span> <span data-ttu-id="1fdd0-118">Selecione **Manual** para usar a página Proposta de Transporte, ou selecione **EDI** para atualizar a proposta usando Intercâmbio Eletrônico de Dados (EDI).</span><span class="sxs-lookup"><span data-stu-id="1fdd0-118">Select **Manual** to use the Transportation Tender page, or select **EDI** to update the tender by using Electronic Data Interchange (EDI).</span></span>  
5. <span data-ttu-id="1fdd0-119">Marque ou desmarque a caixa de seleção **Ativar a transportadora**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-119">Check or uncheck the **Activate carrier rating** checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="1fdd0-120">Crie os serviços necessários para a transportadora</span><span class="sxs-lookup"><span data-stu-id="1fdd0-120">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="1fdd0-121">Ative a expansão da seção **Serviços**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-121">Toggle the expansion of the **Services** section.</span></span>
2. <span data-ttu-id="1fdd0-122">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-122">Select **New**.</span></span>
3. <span data-ttu-id="1fdd0-123">No campo **Serviço da transportadora**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-123">In the **Carrier service** field, type a value.</span></span>
4. <span data-ttu-id="1fdd0-124">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-124">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="1fdd0-125">No campo **Método de transporte**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-125">In the **Transportation method** field, select an option from the drop-down menu.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="1fdd0-126">Configure o endereço da transportadora (opcional)</span><span class="sxs-lookup"><span data-stu-id="1fdd0-126">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="1fdd0-127">Alternar a expansão da seção **Endereços**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-127">Toggle the expansion of the **Addresses** section.</span></span>
2. <span data-ttu-id="1fdd0-128">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-128">Select **New**.</span></span>
3. <span data-ttu-id="1fdd0-129">No campo **Nome ou Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-129">In the **Name or description** field, type a value.</span></span>
4. <span data-ttu-id="1fdd0-130">No campo **País/região**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-130">In the **Country/region** field, select an option from the drop-down menu.</span></span>
5. <span data-ttu-id="1fdd0-131">No campo **CEP/código postal de destino**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-131">In the **ZIP/postal code** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="1fdd0-132">No campo **Rua**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-132">In the **Street** field, type a value.</span></span>
7. <span data-ttu-id="1fdd0-133">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-133">Select **OK**.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="1fdd0-134">Configure o perfil de classificação para a transportadora.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-134">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="1fdd0-135">Ative a expansão da seção **Perfis de classificação**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-135">Toggle the expansion of the **Rating profiles** section.</span></span>
2. <span data-ttu-id="1fdd0-136">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-136">Select **New**.</span></span>
3. <span data-ttu-id="1fdd0-137">No campo **Perfil de classificação**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-137">In the **Rating profile** field, type a value.</span></span>
4. <span data-ttu-id="1fdd0-138">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="1fdd0-139">No campo **Local**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-139">In the **Site** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="1fdd0-140">No campo **Depósito**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-140">In the **Warehouse** field, select an option from the drop-down menu.</span></span>
7. <span data-ttu-id="1fdd0-141">No campo **Mecanismo de taxa**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-141">In the **Rate engine** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="1fdd0-142">Selecione o Mecanismo de taxa que está de acordo com o contrato que você tem com a transportadora.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-142">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
8. <span data-ttu-id="1fdd0-143">No campo **Mestre de taxa**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-143">In the **Rate master** field, select an option from the drop-down menu.</span></span>
9. <span data-ttu-id="1fdd0-144">No campo **Mecanismo de tempo em trânsito**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-144">In the **Transit time engine** field, select an option from the drop-down menu.</span></span>
10. <span data-ttu-id="1fdd0-145">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1fdd0-145">Select **Save**.</span></span>

