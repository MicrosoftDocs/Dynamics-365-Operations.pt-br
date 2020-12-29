---
title: Inserir folhas de ponto do projeto
description: Este procedimento permite criar uma folha de ponto usando um formulário vazio de folha de ponto.
author: andreabichsel
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Operations, Human Resources
ms.search.region: Global
ms.search.industry: Service industries
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10dbb43cec47a758d11362947f27932a4911911a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417306"
---
# <a name="enter-project-timesheets"></a><span data-ttu-id="b95c5-103">Inserir folhas de ponto do projeto</span><span class="sxs-lookup"><span data-stu-id="b95c5-103">Enter project timesheets</span></span>



<span data-ttu-id="b95c5-104">Este procedimento permite criar uma folha de ponto usando um formulário vazio de folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="b95c5-104">This procedure lets you create a timesheet by using an empty timesheet form.</span></span> <span data-ttu-id="b95c5-105">A nova folha de ponto pode ser baseada nas informações de uma folha de ponto anterior, ou em atribuições de projeto e de atividade na página **Meus favoritos**.</span><span class="sxs-lookup"><span data-stu-id="b95c5-105">The new timesheet can be based on information from a previous timesheet, or from project and activity assignments in the **My favorites** page.</span></span> <span data-ttu-id="b95c5-106">Por padrão, a página de lista **Todas as folhas de ponto** exibe todas as suas folhas de ponto do período atual.</span><span class="sxs-lookup"><span data-stu-id="b95c5-106">By default, the **All timesheets** list page displays all your timesheets for the current period.</span></span> <span data-ttu-id="b95c5-107">Você pode usar a lista suspensa do campo **Mostrar** na página **Minhas folhas de ponto** para filtrar a lista de folha de ponto por período ou por projeto, ou para exibir as folhas de ponto que foram criadas em nome de outros trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="b95c5-107">You can use the drop-down list for the **Show** field in the **My timesheets** page to filter the timesheet list by time period or project, or to view timesheets that were created on behalf of other workers.</span></span> <span data-ttu-id="b95c5-108">A empresa de dados de demonstração utilizada para criar esse procedimento é a USSI.</span><span class="sxs-lookup"><span data-stu-id="b95c5-108">The demo data company used to create this procedure is USSI.</span></span> 

1. <span data-ttu-id="b95c5-109">No **Painel de Navegação**, acesse **Módulos > Gerenciamento e contabilidade do projeto > Folhas de ponto > Minhas folhas de ponto**.</span><span class="sxs-lookup"><span data-stu-id="b95c5-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Timesheets > My timesheets**.</span></span>
2. <span data-ttu-id="b95c5-110">Para inserir uma nova planilha de horas, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b95c5-110">To enter a new timesheet, click **New**.</span></span>
    - <span data-ttu-id="b95c5-111">A lista suspensa Recurso mostra o trabalhador atribuído ao usuário atual, por padrão.</span><span class="sxs-lookup"><span data-stu-id="b95c5-111">The Resource drop-down list shows the worker assigned to the current user, by default.</span></span>  
    - <span data-ttu-id="b95c5-112">Se o usuário for designado como um delegado, ele listará os nomes, de modo que um usuário possa inserir uma folha de ponto em seu nome.</span><span class="sxs-lookup"><span data-stu-id="b95c5-112">If the user is designated as a delegate, this will list the names so that a user can enter a timesheet on their behalf.</span></span>  
3. <span data-ttu-id="b95c5-113">No campo **Data**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b95c5-113">In the **Date** field, enter a date.</span></span> <span data-ttu-id="b95c5-114">Se essa opção for selecionada, as novas linhas de folha de ponto serão criadas usando as configurações da folha de ponto que foram configuradas como favoritas.</span><span class="sxs-lookup"><span data-stu-id="b95c5-114">If this option is selected, new timesheet lines will be created by using the timesheet settings that were configured as favorites.</span></span>  
4. <span data-ttu-id="b95c5-115">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b95c5-115">Click **OK**.</span></span>
5. <span data-ttu-id="b95c5-116">Clique em **Nova linha**.</span><span class="sxs-lookup"><span data-stu-id="b95c5-116">Click **New line**.</span></span>
6. <span data-ttu-id="b95c5-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b95c5-117">In the list, mark the selected row.</span></span> <span data-ttu-id="b95c5-118">O campo **Entidade legal** exibe a entidade legal atual, por padrão.</span><span class="sxs-lookup"><span data-stu-id="b95c5-118">The **Legal Entity** field displays the current Legal entity by default.</span></span>   
7. <span data-ttu-id="b95c5-119">No campo **Projeto**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b95c5-119">In the **Project** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="b95c5-120">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="b95c5-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="b95c5-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b95c5-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="b95c5-122">No campo **Número da atividade**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b95c5-122">In the **Activity number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="b95c5-123">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="b95c5-123">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="b95c5-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b95c5-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="b95c5-125">No campo **Categoria**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b95c5-125">In the **Category** field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="b95c5-126">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="b95c5-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="b95c5-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b95c5-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="b95c5-128">Insira o número de horas trabalhadas em cada dia.</span><span class="sxs-lookup"><span data-stu-id="b95c5-128">Enter the number of hours worked each day.</span></span> <span data-ttu-id="b95c5-129">Insira as horas em um formato decimal.</span><span class="sxs-lookup"><span data-stu-id="b95c5-129">Enter the hours in decimal format.</span></span> <span data-ttu-id="b95c5-130">Por exemplo, se você tiver trabalhado por duas horas e quinze minutos, insira 2,25.</span><span class="sxs-lookup"><span data-stu-id="b95c5-130">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
17. <span data-ttu-id="b95c5-131">Em **Detalhes da linha**, as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b95c5-131">In **Line details**, the following options are available:</span></span>
    - <span data-ttu-id="b95c5-132">Adicione informações sobre impostos e dimensões financeiras na guia **Geral** e **Dimensões Financeiras**.</span><span class="sxs-lookup"><span data-stu-id="b95c5-132">Add information about taxes and financial dimensions in the **General** and the **Financial Dimensions** tab.</span></span>
    - <span data-ttu-id="b95c5-133">Adicione comentários sobre a linha da folha de ponto na guia **Comentário**.</span><span class="sxs-lookup"><span data-stu-id="b95c5-133">Add comments about the timesheet line in the **Comment** tab.</span></span>
20. <span data-ttu-id="b95c5-134">No **Painel de Ações**, clique em **Fluxo de trabalho** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="b95c5-134">In the **Action pane**, click **Workflow** to open the drop dialog.</span></span>
21. <span data-ttu-id="b95c5-135">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b95c5-135">Click **Submit**.</span></span>
22. <span data-ttu-id="b95c5-136">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b95c5-136">Click **Submit**.</span></span>

