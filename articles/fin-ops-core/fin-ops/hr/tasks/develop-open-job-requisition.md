---
title: Desenvolver e abrir requisição de trabalho aberta
description: Os projetos de recrutamento ajudam você a gerenciar o processo de recrutamento.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMRecruitingTable, HcmWorkerLookUp, HcmJobLookup, HRMRecruitingMedia, HRMRecruitingJobAd
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d23f180c1afcfa6d24c0b44f69fba9b40c114e1b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564642"
---
# <a name="develop-and-open-job-requisition"></a><span data-ttu-id="1aa6b-103">Desenvolver e abrir requisição de trabalho aberta</span><span class="sxs-lookup"><span data-stu-id="1aa6b-103">Develop and open job requisition</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1aa6b-104">Os projetos de recrutamento ajudam você a gerenciar o processo de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-104">Recruitment projects help manage the recruiting process.</span></span> <span data-ttu-id="1aa6b-105">Para cada projeto de recrutamento, você pode configurar informações, como o trabalho para o qual você está fazendo o recrutamento, o nome de recruta, o status do projeto e o departamento que o trabalho será encontrados em.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-105">For each recruitment project, you can set up information, such as the job that recruiting is for, the name of the recruiter, the status of the project and the department that the job will be located in.</span></span> <span data-ttu-id="1aa6b-106">Depois de criar um projeto de recrutamento, você pode criar um anúncio de emprego para o projeto, publicar o anúncio de emprego nas páginas de autoatendimento do funcionário, associar aplicações para emprego com o projeto, e rastrear atividades para aquele projeto.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-106">After creating a recruitment project, you can write a job advertisement for the project, publish the ad on Employee self-service pages, associate applications for employment with the project, and track activities for that project.</span></span> <span data-ttu-id="1aa6b-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1aa6b-108">Para iniciar o procedimento, vá para Recursos humanos > Recrutamento > Projetos de recrutamento > Projetos de recrutamento</span><span class="sxs-lookup"><span data-stu-id="1aa6b-108">To begin the procedure, go to Human resources > Recruitment > Recruitment projects > Recruitment projects</span></span>

1. <span data-ttu-id="1aa6b-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-109">Click New.</span></span>
2. <span data-ttu-id="1aa6b-110">No campo Projeto de recrutamento, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-110">In the Recruitment project field, type a value.</span></span>
3. <span data-ttu-id="1aa6b-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-111">In the Description field, type a value.</span></span>
4. <span data-ttu-id="1aa6b-112">No campo Recrutador, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-112">In the Recruiter field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="1aa6b-113">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-113">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="1aa6b-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="1aa6b-115">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-115">Click Select.</span></span>
8. <span data-ttu-id="1aa6b-116">No campo Departamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-116">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="1aa6b-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-117">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="1aa6b-118">No campo Trabalho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-118">In the Job field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="1aa6b-119">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-119">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="1aa6b-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-120">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="1aa6b-121">No campo Número de aberturas, insira um número.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-121">In the Number of openings field, enter a number.</span></span>
14. <span data-ttu-id="1aa6b-122">No campo Contratar gerente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-122">In the Hiring manager field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="1aa6b-123">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="1aa6b-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="1aa6b-125">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-125">Click Select.</span></span>
18. <span data-ttu-id="1aa6b-126">No campo Prazo final da solicitação de emprego, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-126">In the Application deadline field, enter a date.</span></span>
19. <span data-ttu-id="1aa6b-127">Clique em Mídia.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-127">Click Media.</span></span>
    * <span data-ttu-id="1aa6b-128">Os projetos de recrutamento incluem a opção para especificar a mídia de comunicação a ser usada para anunciar posições em aberto.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-128">Recruitment projects include the option to specify media outlets to use to advertise open positions.</span></span>  
20. <span data-ttu-id="1aa6b-129">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-129">Click New.</span></span>
21. <span data-ttu-id="1aa6b-130">No campo Mídia, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-130">In the Media field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="1aa6b-131">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-131">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="1aa6b-132">No campo Data de início, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-132">In the Start date field, enter a date.</span></span>
24. <span data-ttu-id="1aa6b-133">No campo Data final, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-133">In the End date field, enter a date.</span></span>
25. <span data-ttu-id="1aa6b-134">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-134">Click Save.</span></span>
26. <span data-ttu-id="1aa6b-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-135">Close the page.</span></span>
27. <span data-ttu-id="1aa6b-136">Clique em Anúncios de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-136">Click Job ads.</span></span>
28. <span data-ttu-id="1aa6b-137">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-137">Click Save.</span></span>
29. <span data-ttu-id="1aa6b-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-138">Close the page.</span></span>
30. <span data-ttu-id="1aa6b-139">Marque ou desmarque a caixa de seleção Exibir no autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-139">Check or uncheck the Display on employee self service checkbox.</span></span>
    * <span data-ttu-id="1aa6b-140">Selecione a caixa de seleção Exibir no autoatendimento para funcionários para tornar o projeto de recrutamento visível a funcionários em suas páginas de autoatendimento de funcionários.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-140">Select the Display on employee self service check box to make the recruitment project visible to employees on their Employee self-service pages.</span></span>  
31. <span data-ttu-id="1aa6b-141">Clique em Status do projeto de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-141">Click Recruitment project status.</span></span>
32. <span data-ttu-id="1aa6b-142">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-142">Click Start.</span></span>
    * <span data-ttu-id="1aa6b-143">O status Iniciado significa que o projeto está pronto para receber solicitações de emprego.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-143">The Started status means that the project is ready to receive applications.</span></span>  
33. <span data-ttu-id="1aa6b-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1aa6b-144">Click OK.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]