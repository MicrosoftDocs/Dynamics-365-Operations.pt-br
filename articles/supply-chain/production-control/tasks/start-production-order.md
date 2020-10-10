---
title: Começar uma ordem de produção
description: Esse procedimento mostra como iniciar uma ordem de produção no chão de fábrica.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationStartJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47915a93151b1adc99ddb4e3facb29bf8db49dd6
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826013"
---
# <a name="start-a-production-order"></a><span data-ttu-id="04b70-103">Começar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="04b70-103">Start a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="04b70-104">Esse procedimento mostra como iniciar uma ordem de produção no chão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="04b70-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="04b70-105">Consumo de materiais e tempo são relatados nesse processo.</span><span class="sxs-lookup"><span data-stu-id="04b70-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="04b70-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="04b70-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="04b70-107">Este é o quinto procedimento de sete que explica o ciclo de vida da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="04b70-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="04b70-108">Começar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="04b70-108">Start a production order</span></span>
1. <span data-ttu-id="04b70-109">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="04b70-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="04b70-110">Selecione uma ordem de produção com o status Liberada.</span><span class="sxs-lookup"><span data-stu-id="04b70-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="04b70-111">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="04b70-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="04b70-112">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="04b70-112">Click Start.</span></span>
    * <span data-ttu-id="04b70-113">Nesta página, você pode confirmar o início da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="04b70-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="04b70-114">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="04b70-114">Click the General tab.</span></span>
5. <span data-ttu-id="04b70-115">No campo Da Oper.</span><span class="sxs-lookup"><span data-stu-id="04b70-115">In the From Oper.</span></span> <span data-ttu-id="04b70-116">Não.</span><span class="sxs-lookup"><span data-stu-id="04b70-116">No.</span></span> <span data-ttu-id="04b70-117">, insira '10'.</span><span class="sxs-lookup"><span data-stu-id="04b70-117">field, enter '10'.</span></span>
6. <span data-ttu-id="04b70-118">No campo Consumo automático de roteiro, selecione 'Sempre'.</span><span class="sxs-lookup"><span data-stu-id="04b70-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="04b70-119">Clique na caixa de seleção Lançar cartão de roteiro agora.</span><span class="sxs-lookup"><span data-stu-id="04b70-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="04b70-120">No campo Consumo automático de BOM, selecione 'Sempre'.</span><span class="sxs-lookup"><span data-stu-id="04b70-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="04b70-121">Clique na caixa de seleção Lançar lista de separação agora.</span><span class="sxs-lookup"><span data-stu-id="04b70-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="04b70-122">Clique na caixa de seleção Imprimir lista de separação.</span><span class="sxs-lookup"><span data-stu-id="04b70-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="04b70-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="04b70-123">Click OK.</span></span>
    * <span data-ttu-id="04b70-124">Esta é a lista de separação impressa que mostra os materiais usados na ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="04b70-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="04b70-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="04b70-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="04b70-126">Validar a lista de separação</span><span class="sxs-lookup"><span data-stu-id="04b70-126">Validate the picking list</span></span>
1. <span data-ttu-id="04b70-127">No Painel de Ação, clique em Exibir.</span><span class="sxs-lookup"><span data-stu-id="04b70-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="04b70-128">Clique em Lista de separação.</span><span class="sxs-lookup"><span data-stu-id="04b70-128">Click Picking list.</span></span>
3. <span data-ttu-id="04b70-129">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="04b70-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="04b70-130">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="04b70-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="04b70-131">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="04b70-131">Click Edit.</span></span>
6. <span data-ttu-id="04b70-132">No campo Consumo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="04b70-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="04b70-133">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="04b70-133">Click Post.</span></span>
8. <span data-ttu-id="04b70-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="04b70-134">Click OK.</span></span>
    * <span data-ttu-id="04b70-135">No diário da lista de separação, os materiais consumidos pela ordem de produção são lançados.</span><span class="sxs-lookup"><span data-stu-id="04b70-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="04b70-136">Antes de lançar o diário, você pode fazer ajustes se houver uma diferença entre a quantidade prevista e a quantidade realmente consumida.</span><span class="sxs-lookup"><span data-stu-id="04b70-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="04b70-137">Clique na guia GridPanel.</span><span class="sxs-lookup"><span data-stu-id="04b70-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="04b70-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="04b70-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="04b70-139">Verificar o diário de cartão de roteiro</span><span class="sxs-lookup"><span data-stu-id="04b70-139">Verify the route card journal</span></span>
1. <span data-ttu-id="04b70-140">No Painel de Ação, clique em Exibir.</span><span class="sxs-lookup"><span data-stu-id="04b70-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="04b70-141">Clique em Cartão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="04b70-141">Click Route card.</span></span>
3. <span data-ttu-id="04b70-142">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="04b70-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="04b70-143">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="04b70-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="04b70-144">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="04b70-144">Click Edit.</span></span>
6. <span data-ttu-id="04b70-145">No campo Horas, insira um número.</span><span class="sxs-lookup"><span data-stu-id="04b70-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="04b70-146">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="04b70-146">Click Post.</span></span>
8. <span data-ttu-id="04b70-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="04b70-147">Click OK.</span></span>
    * <span data-ttu-id="04b70-148">No diário de cartão de roteiro, é registrado o tempo gasto em operações individuais.</span><span class="sxs-lookup"><span data-stu-id="04b70-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="04b70-149">A quantidade de erros e acertos também pode ser informada.</span><span class="sxs-lookup"><span data-stu-id="04b70-149">Good and error quantity can also be reported.</span></span>  
