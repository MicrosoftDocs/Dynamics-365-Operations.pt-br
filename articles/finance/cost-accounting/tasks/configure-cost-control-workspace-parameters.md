---
title: Configurar parâmetros de espaço de trabalho de controle de custo
description: Use este procedimento para configurar o espaço de trabalho de controle de custo, de forma que os gerentes de vários níveis em uma organização possam se aprofundar nos seus objetos de custo, como centros de custos e grupos de produtos.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 867bfd2f2d1ff486e683cb11c38906dd0efe8c14
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187857"
---
# <a name="configure-cost-control-workspace-parameters"></a><span data-ttu-id="69dd5-103">Configurar parâmetros de espaço de trabalho de controle de custo</span><span class="sxs-lookup"><span data-stu-id="69dd5-103">Configure cost control workspace parameters</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="69dd5-104">Use este procedimento para configurar o espaço de trabalho de controle de custo, de forma que os gerentes de vários níveis em uma organização possam se aprofundar nos seus objetos de custo, como centros de custos e grupos de produtos.</span><span class="sxs-lookup"><span data-stu-id="69dd5-104">Use this procedure to configure the Cost control workspace so that managers at various levels in an organization can gain insight into their cost objects, such as cost centers and product groups.</span></span> <span data-ttu-id="69dd5-105">A empresa de demonstração USP2 foi usada para criar esta gravação.</span><span class="sxs-lookup"><span data-stu-id="69dd5-105">The USP2 demo company was used to create this recording.</span></span>

1. <span data-ttu-id="69dd5-106">Vá para Contabilização de custos > Configuração > Configuração de espaço de trabalho de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="69dd5-106">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
2. <span data-ttu-id="69dd5-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="69dd5-107">Click New.</span></span>
3. <span data-ttu-id="69dd5-108">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-108">In the Name field, type a value.</span></span>
4. <span data-ttu-id="69dd5-109">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="69dd5-110">Selecione Sim no campo Publicado.</span><span class="sxs-lookup"><span data-stu-id="69dd5-110">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="69dd5-111">Se definir esta opção como Sim, os usuários que foram atribuídos a uma dessas funções poderão consultar o relatório no espaço de trabalho de controle de custo: gerente de contabilidade de custo, contador de custos, funcionário de contador de custo ou controlador de objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="69dd5-111">If you set this option to Yes, users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, or cost object controller.</span></span> <span data-ttu-id="69dd5-112">Se definir esta opção como Não, somente os usuários que foram atribuídos a uma dessas funções poderão consultar o relatório no espaço de trabalho de controle de custo: gerente de contabilidade de custo, contador de custos, funcionário de contador de custo.</span><span class="sxs-lookup"><span data-stu-id="69dd5-112">If you set this option to No, only users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, or cost accountant clerk.</span></span>  
6. <span data-ttu-id="69dd5-113">Expanda a seção Filtragem de dados.</span><span class="sxs-lookup"><span data-stu-id="69dd5-113">Expand the Data filtering section.</span></span>
7. <span data-ttu-id="69dd5-114">No campo Unidade de controle de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-114">In the Cost control unit field, enter or select a value.</span></span>
8. <span data-ttu-id="69dd5-115">No campo Versão original do orçamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-115">In the Budget original version field, enter or select a value.</span></span>
9. <span data-ttu-id="69dd5-116">No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-116">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
10. <span data-ttu-id="69dd5-117">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-117">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
11. <span data-ttu-id="69dd5-118">Expanda a seção Atribuir registros de cálculo.</span><span class="sxs-lookup"><span data-stu-id="69dd5-118">Expand the Assign calculation records section.</span></span>
12. <span data-ttu-id="69dd5-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="69dd5-119">Click New.</span></span>
13. <span data-ttu-id="69dd5-120">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="69dd5-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="69dd5-121">No campo Período do calendário fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-121">In the Fiscal calendar period field, enter or select a value.</span></span>
15. <span data-ttu-id="69dd5-122">No campo Versão real, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-122">In the Actual version field, enter or select a value.</span></span>
16. <span data-ttu-id="69dd5-123">Expanda a seção Períodos fiscais por coluna.</span><span class="sxs-lookup"><span data-stu-id="69dd5-123">Expand the Fiscal periods per column section.</span></span>
17. <span data-ttu-id="69dd5-124">Selecione Sim no campo Período atual.</span><span class="sxs-lookup"><span data-stu-id="69dd5-124">Select Yes in the Current period field.</span></span>
18. <span data-ttu-id="69dd5-125">Expanda a seção Colunas a serem exibidas para custos.</span><span class="sxs-lookup"><span data-stu-id="69dd5-125">Expand the Columns to display for costs section.</span></span>
19. <span data-ttu-id="69dd5-126">Selecione Sim no campo Custo fixo.</span><span class="sxs-lookup"><span data-stu-id="69dd5-126">Select Yes in the Fixed cost field.</span></span>
20. <span data-ttu-id="69dd5-127">Selecione Sim no campo Custo variável.</span><span class="sxs-lookup"><span data-stu-id="69dd5-127">Select Yes in the Variable cost field.</span></span>
21. <span data-ttu-id="69dd5-128">Selecione Sim no campo Custo total.</span><span class="sxs-lookup"><span data-stu-id="69dd5-128">Select Yes in the Total cost field.</span></span>
22. <span data-ttu-id="69dd5-129">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="69dd5-129">Click Save.</span></span>
23. <span data-ttu-id="69dd5-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="69dd5-130">Close the page.</span></span>
24. <span data-ttu-id="69dd5-131">Vá para Contabilização de custos > Espaços de trabalho > Controle de custo.</span><span class="sxs-lookup"><span data-stu-id="69dd5-131">Go to Cost accounting > Workspaces > Cost control.</span></span>
25. <span data-ttu-id="69dd5-132">Selecione um demonstrativo para exibir custos fixos, variáveis, totais e não classificados para os períodos fiscais selecionados.</span><span class="sxs-lookup"><span data-stu-id="69dd5-132">Select a statement to see fixed, variable, total, and unclassified costs for the selected fiscal periods.</span></span>
26. <span data-ttu-id="69dd5-133">No campo Período do calendário fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-133">In the Fiscal calendar period field, enter or select a value.</span></span>
27. <span data-ttu-id="69dd5-134">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-134">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="69dd5-135">Depois de ter selecionado uma hierarquia de dimensão do objeto de Custo, expanda a hierarquia de dimensão do elemento de custo para ver os valores de custos desejados.</span><span class="sxs-lookup"><span data-stu-id="69dd5-135">After you've selected a Cost object dimension hierarchy, expand the Cost element dimension hierarchy to see the desired cost values.</span></span> <span data-ttu-id="69dd5-136">Por exemplo, você pode expandir a hierarquia para Custos indiretos de fabricação para ver o valor.</span><span class="sxs-lookup"><span data-stu-id="69dd5-136">For example, you can expand the hierarchy to Manufacturing overhead to see the value.</span></span>  
