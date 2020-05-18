---
title: Criar um projeto de contratação em massa
description: Este procedimento anda com o processo de configuração de um projeto de contratação em massa.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject,  HRMMassHireLineCreate, HcmJobLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19d2f41f92aef7739e8e36012e207b96af155190
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008126"
---
# <a name="create-a-mass-hire-project"></a><span data-ttu-id="84c6c-103">Criar um projeto de contratação em massa</span><span class="sxs-lookup"><span data-stu-id="84c6c-103">Create a mass hire project</span></span>



<span data-ttu-id="84c6c-104">Este procedimento anda com o processo de configuração de um projeto de contratação em massa.</span><span class="sxs-lookup"><span data-stu-id="84c6c-104">This procedure walks through the process of setting up a mass hire project.</span></span> <span data-ttu-id="84c6c-105">Um recruta pode usar projetos de contratação em massa criar facilmente várias posições e contratar um número de funcionários nas posições.</span><span class="sxs-lookup"><span data-stu-id="84c6c-105">A recruiter can use mass hire projects to easily create multiple positions and hire a number of workers into those positions.</span></span> <span data-ttu-id="84c6c-106">Para iniciar este procedimento, vá para Recursos humanos > Recrutamento > Projetos de contratação em massa.</span><span class="sxs-lookup"><span data-stu-id="84c6c-106">To begin this procedure, go to Human resources > Recruitment > Mass hire projects.</span></span> <span data-ttu-id="84c6c-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="84c6c-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="84c6c-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="84c6c-108">Click New.</span></span>
2. <span data-ttu-id="84c6c-109">No campo Projeto de contratação em massa, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="84c6c-109">In the Mass hire project field, type a value.</span></span>
3. <span data-ttu-id="84c6c-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="84c6c-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="84c6c-111">No campo Início do projeto, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="84c6c-111">In the Project start field, enter a date.</span></span>
5. <span data-ttu-id="84c6c-112">No campo Fim do projeto, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="84c6c-112">In the Project end field, enter a date.</span></span>
6. <span data-ttu-id="84c6c-113">Clique em Exibição do projeto.</span><span class="sxs-lookup"><span data-stu-id="84c6c-113">Click Open project.</span></span>
7. <span data-ttu-id="84c6c-114">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="84c6c-114">Click Yes.</span></span>
8. <span data-ttu-id="84c6c-115">Clique em Criar posições.</span><span class="sxs-lookup"><span data-stu-id="84c6c-115">Click Create positions.</span></span>
9. <span data-ttu-id="84c6c-116">No campo Quantidade, digite o número de posições que deseja criar</span><span class="sxs-lookup"><span data-stu-id="84c6c-116">In the Quantity field, enter the number of positions that you want to create</span></span>
    * <span data-ttu-id="84c6c-117">A data inicial se tornará a data de contratação para os novos funcionários.</span><span class="sxs-lookup"><span data-stu-id="84c6c-117">The Start date will become the Hire date for the new workers.</span></span>  
    * <span data-ttu-id="84c6c-118">A data Final se tornará a data de término para os novos funcionários.</span><span class="sxs-lookup"><span data-stu-id="84c6c-118">The End date will be the Termination date for the new workers.</span></span>  
    * <span data-ttu-id="84c6c-119">Especifique se os novos funcionários serão funcionários ou prestadores de serviço.</span><span class="sxs-lookup"><span data-stu-id="84c6c-119">Specify whether the new workers will be Employees or Contractors.</span></span>  
10. <span data-ttu-id="84c6c-120">No campo Trabalho, clique no botão suspenso para selecionar os trabalhos para criar posições.</span><span class="sxs-lookup"><span data-stu-id="84c6c-120">In the Job field, click the drop-down button to select the job to create the positions for.</span></span>
11. <span data-ttu-id="84c6c-121">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="84c6c-121">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="84c6c-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="84c6c-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="84c6c-123">O valor equivalente de tempo integral padrão virá do trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="84c6c-123">The default full-time equivalent value will come from the selected job.</span></span> <span data-ttu-id="84c6c-124">Você pode mudar isso, se necessário.</span><span class="sxs-lookup"><span data-stu-id="84c6c-124">You can change this if needed.</span></span>  
    * <span data-ttu-id="84c6c-125">Opcionalmente, selecione o departamento para as novas posições.</span><span class="sxs-lookup"><span data-stu-id="84c6c-125">Optionally, select the Department for the new positions.</span></span>  
13. <span data-ttu-id="84c6c-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84c6c-126">Click OK.</span></span>
