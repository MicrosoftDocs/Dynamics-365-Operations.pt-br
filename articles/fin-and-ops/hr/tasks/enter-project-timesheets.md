---
title: Inserir folhas de ponto do projeto
description: Este procedimento permite criar uma folha de ponto usando um formulário vazio de folha de ponto.
author: andreabichsel
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.search.industry: Service industries
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f1be02f0080ee23359ad905b1e997d8cd5adfd2
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "859128"
---
# <a name="enter-project-timesheets"></a><span data-ttu-id="ae0dd-103">Inserir folhas de ponto do projeto</span><span class="sxs-lookup"><span data-stu-id="ae0dd-103">Enter project timesheets</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ae0dd-104">Este procedimento permite criar uma folha de ponto usando um formulário vazio de folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-104">This procedure lets you create a timesheet by using an empty timesheet form.</span></span> <span data-ttu-id="ae0dd-105">A nova folha de ponto pode ser baseada nas informações de uma folha de ponto anterior, ou em atribuições de projeto e de atividade na página Meus favoritos.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-105">The new timesheet can be based on information from a previous timesheet, or from project and activity assignments in the My favorites page.</span></span> <span data-ttu-id="ae0dd-106">Por padrão, a página de lista Todas as folhas de ponto exibe todas as suas folhas de ponto do período atual.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-106">By default, the All timesheets list page displays all your timesheets for the current period.</span></span> <span data-ttu-id="ae0dd-107">Você pode usar a lista suspensa do campo Mostrar na página Minhas folhas de ponto para filtrar a lista de folha de ponto por período ou por projeto, ou para exibir as folhas de ponto que foram criadas em nome de outros trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-107">You can use the drop-down list for the Show field in the My timesheets page to filter the timesheet list by time period or project, or to view timesheets that were created on behalf of other workers.</span></span> <span data-ttu-id="ae0dd-108">A empresa de dados de demonstração utilizada para criar esse procedimento é a USSI.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-108">The demo data company used to create this procedure is USSI.</span></span> <span data-ttu-id="ae0dd-109">Para iniciar este procedimento, vá para Gerenciamento e contabilidade de projetos > Folhas de ponto > Minhas folhas de ponto</span><span class="sxs-lookup"><span data-stu-id="ae0dd-109">To begin this procedure, go to Project management and accounting > Timesheets >My timesheets</span></span>

1. <span data-ttu-id="ae0dd-110">Para inserir uma nova planilha de horas, clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-110">To enter a new timesheet, click New.</span></span>
    * <span data-ttu-id="ae0dd-111">A lista suspensa Recurso mostra o trabalhador atribuído ao usuário atual, por padrão.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-111">The Resource drop-down list shows the worker assigned to the current user, by default.</span></span>  
    * <span data-ttu-id="ae0dd-112">Se o usuário for designado como um delegado, ele listará os nomes, de modo que um usuário possa inserir uma folha de ponto em seu nome.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-112">If the user is designated as a delegate, this will list the names so that a user can enter a timesheet on their behalf.</span></span>  
2. <span data-ttu-id="ae0dd-113">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-113">In the Date field, enter a date.</span></span>
    * <span data-ttu-id="ae0dd-114">Se essa opção for selecionada, as novas linhas de folha de ponto serão criadas usando as configurações da folha de ponto que foram configuradas como favoritas.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-114">If this option is selected, new timesheet lines will be created by using the timesheet settings that were configured as favorites.</span></span>  
3. <span data-ttu-id="ae0dd-115">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-115">Click OK.</span></span>
4. <span data-ttu-id="ae0dd-116">Clique em Nova linha.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-116">Click New line.</span></span>
5. <span data-ttu-id="ae0dd-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ae0dd-118">O campo Entidade legal exibe a entidade legal atual, por padrão.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-118">The Legal Entity field displays the current Legal entity by default.</span></span>   
6. <span data-ttu-id="ae0dd-119">No campo Projeto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-119">In the Project field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ae0dd-120">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-120">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="ae0dd-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ae0dd-122">No campo Atividade, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-122">In the Activity field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="ae0dd-123">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-123">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="ae0dd-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-124">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="ae0dd-125">No campo Categoria, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-125">In the Category field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="ae0dd-126">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-126">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="ae0dd-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-127">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="ae0dd-128">Insira o número de horas trabalhadas em cada dia.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-128">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="ae0dd-129">As horas devem ser inseridas em um formato decimal.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-129">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="ae0dd-130">Por exemplo, se você tiver trabalhado por duas horas e quinze minutos, insira 2,25.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-130">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
16. <span data-ttu-id="ae0dd-131">Insira o número de horas trabalhadas em cada dia.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-131">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="ae0dd-132">As horas devem ser inseridas em um formato decimal.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-132">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="ae0dd-133">Por exemplo, se você tiver trabalhado por duas horas e quinze minutos, insira 2,25.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-133">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
17. <span data-ttu-id="ae0dd-134">Insira o número de horas trabalhadas em cada dia.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-134">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="ae0dd-135">As horas devem ser inseridas em um formato decimal.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-135">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="ae0dd-136">Por exemplo, se você tiver trabalhado por duas horas e quinze minutos, insira 2,25.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-136">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
18. <span data-ttu-id="ae0dd-137">Insira o número de horas trabalhadas em cada dia.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-137">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="ae0dd-138">As horas devem ser inseridas em um formato decimal.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-138">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="ae0dd-139">Por exemplo, se você tiver trabalhado por duas horas e quinze minutos, insira 2,25.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-139">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
19. <span data-ttu-id="ae0dd-140">Insira o número de horas trabalhadas em cada dia.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-140">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="ae0dd-141">As horas devem ser inseridas em um formato decimal.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-141">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="ae0dd-142">Por exemplo, se você tiver trabalhado por duas horas e quinze minutos, insira 2,25.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-142">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
    * <span data-ttu-id="ae0dd-143">Nos detalhes da Linha, as seguintes opções estão disponíveis:  o  Adicionar informações sobre impostos e dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-143">In Line details, the following options are available:  o  Add information about taxes and financial dimensions.</span></span>  <span data-ttu-id="ae0dd-144">o    Adicionar comentários sobre a linha da folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-144">o    Add comments about the timesheet line.</span></span>  
20. <span data-ttu-id="ae0dd-145">Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-145">Click Workflow to open the drop dialog.</span></span>
21. <span data-ttu-id="ae0dd-146">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-146">Click Submit.</span></span>
22. <span data-ttu-id="ae0dd-147">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="ae0dd-147">Click Submit.</span></span>

