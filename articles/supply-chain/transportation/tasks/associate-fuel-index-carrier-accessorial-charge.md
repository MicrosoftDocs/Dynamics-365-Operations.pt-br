---
title: Associar um índice de combustível a uma transportadora como um encargo suplementar
description: Este guia mostra como criar uma atribuição suplementar, um encargo suplementar da transportadora, um mestre suplementar para sobretaxa de combustível e como associar um índice de combustível da transportadora a uma transportadora.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43b3267122594329444fc4b0458db6b14aa5c672
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206187"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="1adbb-103">Associar um índice de combustível a uma transportadora como um encargo suplementar</span><span class="sxs-lookup"><span data-stu-id="1adbb-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1adbb-104">Este guia mostra como criar uma atribuição suplementar, um encargo suplementar da transportadora, um mestre suplementar para sobretaxa de combustível e como associar um índice de combustível da transportadora a uma transportadora.</span><span class="sxs-lookup"><span data-stu-id="1adbb-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="1adbb-105">Você precisa ter configurado um índice de combustível da transportadora antes de executar esse guia.</span><span class="sxs-lookup"><span data-stu-id="1adbb-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="1adbb-106">Para isso, você pode usar o guia "Configurar um índice de combustível da transportadora".</span><span class="sxs-lookup"><span data-stu-id="1adbb-106">You can use the "Set up a carrier fuel index" guide to do this.</span></span> <span data-ttu-id="1adbb-107">Essas tarefas de configuração são tipicamente feitas por um gerente de logística.</span><span class="sxs-lookup"><span data-stu-id="1adbb-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="1adbb-108">Os dados demonstrativos utilizados na criação desse procedimento são do conjunto USMF.</span><span class="sxs-lookup"><span data-stu-id="1adbb-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="1adbb-109">Crie um mestre suplementar</span><span class="sxs-lookup"><span data-stu-id="1adbb-109">Create an accessorial master</span></span>
1. <span data-ttu-id="1adbb-110">Vá para Gerenciamento de transporte > Configurar > Classificação > Mestres suplementares.</span><span class="sxs-lookup"><span data-stu-id="1adbb-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="1adbb-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1adbb-111">Click New.</span></span>
3. <span data-ttu-id="1adbb-112">No campo Mestre suplementar, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1adbb-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="1adbb-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1adbb-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="1adbb-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1adbb-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="1adbb-115">Crie um encargo suplementar da transportadora</span><span class="sxs-lookup"><span data-stu-id="1adbb-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="1adbb-116">Vá para Gerenciamento de transporte > Configurar > Classificação > Encargos suplementares da transportadora.</span><span class="sxs-lookup"><span data-stu-id="1adbb-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="1adbb-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1adbb-117">Click New.</span></span>
3. <span data-ttu-id="1adbb-118">No campo ID suplementar da transportadora, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1adbb-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="1adbb-119">No campo Transportadora, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1adbb-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="1adbb-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="1adbb-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1adbb-121">Neste exemplo, escolha Transportadora Rodoviária.</span><span class="sxs-lookup"><span data-stu-id="1adbb-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="1adbb-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1adbb-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="1adbb-123">No campo Serviço da transportadora, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1adbb-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="1adbb-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1adbb-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="1adbb-125">No campo Mestre suplementar, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1adbb-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="1adbb-126">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="1adbb-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1adbb-127">Neste exemplo, escolha o Mestre suplementar criado recentemente.</span><span class="sxs-lookup"><span data-stu-id="1adbb-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="1adbb-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1adbb-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="1adbb-129">Crie uma atribuição suplementar</span><span class="sxs-lookup"><span data-stu-id="1adbb-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="1adbb-130">Clique em Atribuições suplementares.</span><span class="sxs-lookup"><span data-stu-id="1adbb-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="1adbb-131">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1adbb-131">Click New.</span></span>
3. <span data-ttu-id="1adbb-132">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1adbb-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="1adbb-133">Ative a expansão da seção Critérios.</span><span class="sxs-lookup"><span data-stu-id="1adbb-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="1adbb-134">Nos critérios, você pode optar por sempre aplicar a sobretaxa de combustível ou, para este exemplo, escolher que ela se aplique somente dentro de uma determinada região.</span><span class="sxs-lookup"><span data-stu-id="1adbb-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="1adbb-135">No campo CEP/código postal de, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1adbb-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="1adbb-136">No campo CEP/código postal até, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1adbb-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="1adbb-137">Ative a expansão da seção Cálculos.</span><span class="sxs-lookup"><span data-stu-id="1adbb-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="1adbb-138">Na seção de cálculo, é possível especificar como calcular a sobretaxa de combustível.</span><span class="sxs-lookup"><span data-stu-id="1adbb-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="1adbb-139">Esse cálculo depende da unidade Suplementar escolhida como base para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="1adbb-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="1adbb-140">No campo Tipo de taxa suplementar, selecione 'Sobretaxa de combustível'.</span><span class="sxs-lookup"><span data-stu-id="1adbb-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="1adbb-141">No campo Unidade suplementar, selecione 'Quilometragem'.</span><span class="sxs-lookup"><span data-stu-id="1adbb-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="1adbb-142">No campo Região, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1adbb-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="1adbb-143">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1adbb-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="1adbb-144">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1adbb-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="1adbb-145">Atualize o perfil de classificação da transportadora</span><span class="sxs-lookup"><span data-stu-id="1adbb-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="1adbb-146">Vá para Gerenciamento de transporte > Configuração > Transportadoras > Transportadoras de envio.</span><span class="sxs-lookup"><span data-stu-id="1adbb-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="1adbb-147">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="1adbb-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1adbb-148">Ative a expansão da seção Perfis de classificação.</span><span class="sxs-lookup"><span data-stu-id="1adbb-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="1adbb-149">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="1adbb-149">Click Edit.</span></span>
5. <span data-ttu-id="1adbb-150">No campo Índice de combustível da transportadora, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1adbb-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1adbb-151">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1adbb-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="1adbb-152">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1adbb-152">Click Save.</span></span>

