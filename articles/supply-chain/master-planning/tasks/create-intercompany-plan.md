---
title: Criar um plano intercompanhia
description: Este procedimento mostra como criar um plano intercompanhia.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f8cf4ed879b6b2202d0b0f1f45052f5e21452967
ms.sourcegitcommit: 9b07d536b4bd8addfbdba42d2429c9fedb664635
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867341"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="cc648-103">Criar um plano intercompanhia</span><span class="sxs-lookup"><span data-stu-id="cc648-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cc648-104">Este procedimento mostra como criar um plano intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="cc648-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="cc648-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="cc648-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="cc648-106">Configurar um grupo de planejamento intercompanhia</span><span class="sxs-lookup"><span data-stu-id="cc648-106">Set up an intercompany planning group</span></span>

1. <span data-ttu-id="cc648-107">No **Painel de Navegação**, acesse **Módulos > Planejamento mestre > Configuração > Grupos de planejamento intercompanhia**.</span><span class="sxs-lookup"><span data-stu-id="cc648-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span>
2. <span data-ttu-id="cc648-108">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="cc648-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="cc648-109">Por exemplo, filtre o campo Nome com um valor de '10'.</span><span class="sxs-lookup"><span data-stu-id="cc648-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="cc648-110">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cc648-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="cc648-111">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="cc648-111">Select **Delete**.</span></span> <span data-ttu-id="cc648-112">Esta etapa é necessária para encurtar a execução de planejamento intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="cc648-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="cc648-113">O planejamento intercompanhia executará o planejamento mestre em todas as empresas de um grupo de planejamento a partir da sequência de planejamento mais baixa.</span><span class="sxs-lookup"><span data-stu-id="cc648-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="cc648-114">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="cc648-114">Select **Yes**.</span></span>
6. <span data-ttu-id="cc648-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cc648-115">Close the page.</span></span>

## <a name="create-an-intercompany-master-plan"></a><span data-ttu-id="cc648-116">Criar um plano mestre intercompanhia</span><span class="sxs-lookup"><span data-stu-id="cc648-116">Create an intercompany master plan</span></span>

1. <span data-ttu-id="cc648-117">No **Painel de Navegação**, acesse **Módulos > Planejamento mestre > Espaços de trabalho > Planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="cc648-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="cc648-118">Selecione **Planejamento mestre intercompanhia**.</span><span class="sxs-lookup"><span data-stu-id="cc648-118">Select **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="cc648-119">No campo **Grupo de planejamento intercompanhia**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cc648-119">In the **Intercompany planning group** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="cc648-120">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cc648-120">In the list, select the link in the selected row.</span></span> <span data-ttu-id="cc648-121">Selecione Grupo de planejamento intercompanhia 10.</span><span class="sxs-lookup"><span data-stu-id="cc648-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="cc648-122">No campo **Número de iterações de planejamento intercompanhia**, insira "2".</span><span class="sxs-lookup"><span data-stu-id="cc648-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="cc648-123">O grupo de planejamento intercompanhia 10 tem dois membros.</span><span class="sxs-lookup"><span data-stu-id="cc648-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="cc648-124">Para propagar os atrasos da empresa de origem (USMF) para a empresa do cliente (DEMF), será necessário executar a intercompanhia nas duas empresas duas vezes.</span><span class="sxs-lookup"><span data-stu-id="cc648-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="cc648-125">A primeira iteração propagará a demanda e identificará os atrasos na empresa de origem (USMF).</span><span class="sxs-lookup"><span data-stu-id="cc648-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="cc648-126">A segunda iteração propagará os atrasos da USMF para a DEMF.</span><span class="sxs-lookup"><span data-stu-id="cc648-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="cc648-127">No campo **Primeira iteração**, selecione "Regeneração".</span><span class="sxs-lookup"><span data-stu-id="cc648-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="cc648-128">No campo **Iterações subsequentes**, selecione "Regeneração".</span><span class="sxs-lookup"><span data-stu-id="cc648-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="cc648-129">No campo **Número de threads**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="cc648-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="cc648-130">Isso representa o número de threads paralelos usados no planejamento.</span><span class="sxs-lookup"><span data-stu-id="cc648-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="cc648-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc648-131">Select **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="cc648-132">Exibir o resultado do plano</span><span class="sxs-lookup"><span data-stu-id="cc648-132">View the result of the plan</span></span>

1. <span data-ttu-id="cc648-133">No campo **Plano**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cc648-133">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="cc648-134">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cc648-134">In the list, select the link in the selected row.</span></span> <span data-ttu-id="cc648-135">Selecione o link para StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="cc648-135">Select the link for StaticPlan.</span></span> <span data-ttu-id="cc648-136">Você precisa estar na empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="cc648-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="cc648-137">Selecione **Ordens planejadas**.</span><span class="sxs-lookup"><span data-stu-id="cc648-137">Select **Planned orders**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]