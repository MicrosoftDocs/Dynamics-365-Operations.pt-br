--- 
title: " Criar grupos de permissões de PDV"
description: "Este procedimento mostra como criar um grupo de permissões de PDV."
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e924dc59c3e4cb9b6979014852512453dd3d70db
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="7bbfd-103"> Criar grupos de permissões de PDV</span><span class="sxs-lookup"><span data-stu-id="7bbfd-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="7bbfd-104">Este procedimento mostra como criar um grupo de permissões de PDV.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-104">This procedure will show how to create a POS permission group.</span></span> <span data-ttu-id="7bbfd-105">A empresa de dados de demonstração usada para criar esta tarefa é USRT.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="7bbfd-106">Esta tarefa é destinada à função Gerente de operações de varejo.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="7bbfd-107">Vá para Grupos de permissões.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-107">Go to Permission groups.</span></span>
2. <span data-ttu-id="7bbfd-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-108">Click New.</span></span>
3. <span data-ttu-id="7bbfd-109">No campo ID do grupo de permissões de PDV, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-109">In the POS permission group ID field, type a value.</span></span>
4. <span data-ttu-id="7bbfd-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7bbfd-111">Selecione Sim no campo Exibir entradas do relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-111">Select Yes in the View time clock entries field.</span></span>
    * <span data-ttu-id="7bbfd-112">Agora você pode habilitar ou desabilitar várias permissões para seu grupo de permissões de PDV.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="7bbfd-113">Para algumas permissões, você pode definir um valor que será usado para avaliar se o usuário do PDV pode executar a ação.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span>  <span data-ttu-id="7bbfd-114">Este guia de tarefas mostra como habilitar algumas permissões que podem ser dadas a um caixa.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="7bbfd-115">Selecione Sim no campo Permitir criar ordem.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-115">Select Yes in the Allow create order field.</span></span>
7. <span data-ttu-id="7bbfd-116">Selecione Sim no campo Permitir editar ordem.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-116">Select Yes in the Allow edit order field.</span></span>
8. <span data-ttu-id="7bbfd-117">Selecione Sim no campo Permitir recuperar ordem.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-117">Select Yes in the Allow retrieve order field.</span></span>
9. <span data-ttu-id="7bbfd-118">Selecione Sim no campo Permitir alteração de senha.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-118">Select Yes in the Allow password change field.</span></span>
10. <span data-ttu-id="7bbfd-119">Selecione Sim no campo Permitir fechamento cego.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-119">Select Yes in the Allow blind close field.</span></span>
11. <span data-ttu-id="7bbfd-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-120">Click Save.</span></span>
    * <span data-ttu-id="7bbfd-121">Depois que as alterações forem salvas, é necessário executar a agenda de distribuição da equipe para enviar as alterações aos canais de varejo.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  
12. <span data-ttu-id="7bbfd-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-122">Close the page.</span></span>
13. <span data-ttu-id="7bbfd-123">Vá para Trabalhos.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-123">Go to Jobs.</span></span>
    * <span data-ttu-id="7bbfd-124">A seguir, atribuiremos o grupo de permissões de PDV a um trabalho.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-124">Next we will assign the POS permission group to a Job.</span></span>  
14. <span data-ttu-id="7bbfd-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-125">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="7bbfd-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-126">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="7bbfd-127">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-127">Click Edit.</span></span>
17. <span data-ttu-id="7bbfd-128">Expanda a seção Classificação do trabalho.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-128">Expand the Job classification section.</span></span>
18. <span data-ttu-id="7bbfd-129">No campo grupo de permissões de PDV, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-129">In the POS permission group field, enter or select a value.</span></span>
    * <span data-ttu-id="7bbfd-130">Todos os trabalhadores em posições para esse trabalho usarão estas configurações de grupo de permissões de PDV a menos que as permissões de PDV dos trabalhadores tenham sido substituídas em suas posições.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-130">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
19. <span data-ttu-id="7bbfd-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-131">Click Save.</span></span>
    * <span data-ttu-id="7bbfd-132">Depois que as alterações forem salvas, é necessário executar a agenda de distribuição da equipe para enviar as alterações aos canais de varejo.</span><span class="sxs-lookup"><span data-stu-id="7bbfd-132">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  


