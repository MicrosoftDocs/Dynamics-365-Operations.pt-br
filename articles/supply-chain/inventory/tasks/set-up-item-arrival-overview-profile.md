---
title: Configurar um perfil de visão geral de entradas de item
description: Essa tarefa se concentra na configuração de um perfil de visão geral de entradas.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b61d77072358083a35de28003176cb88e53453e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555099"
---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="1dd5a-103">Configurar um perfil de visão geral de entradas de item</span><span class="sxs-lookup"><span data-stu-id="1dd5a-103">Set up an item arrival overview profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1dd5a-104">Essa tarefa se concentra na configuração de um perfil de visão geral de entradas.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-104">This task focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="1dd5a-105">O perfil de visão geral de entradas é um conjunto de regras que serão aplicadas quando a página de Visão geral de entradas for aberta por um usuário.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-105">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="1dd5a-106">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-106">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="1dd5a-107">Este procedimento será geralmente executado por um auxiliar de recebimento.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-107">This procedure would typically be carried out by a receiving clerk.</span></span>





1. <span data-ttu-id="1dd5a-108">Vá para Gerenciamento de estoque > Configuração > Distribuição > Perfis de visão geral de entradas.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-108">Go to Inventory management > Setup > Distribution > Arrival overview profiles.</span></span>
2. <span data-ttu-id="1dd5a-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-109">Click New.</span></span>
    * <span data-ttu-id="1dd5a-110">Considerando que você quase sempre irá trabalhar no mesmo depósito descarregando cargas de caminhões, você deve criar uma visão geral das chegadas para simplificar o processo de registro de itens recebidos.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-110">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="1dd5a-111">No campo Nome do perfil de visão geral de entradas, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-111">In the Arrival overview profile name field, type a value.</span></span>
4. <span data-ttu-id="1dd5a-112">No campo Mostrar linhas, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-112">In the Show lines field, select an option.</span></span>
    * <span data-ttu-id="1dd5a-113">Selecione quais linhas dos recebimentos serão mostradas: Todas – mostra todas as linhas, independente do status.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-113">Select which lines to show for the receipts:   All – Show all lines, regardless of status.</span></span>   <span data-ttu-id="1dd5a-114">Em andamento – Mostra as linhas dos recebimentos em que o progresso está Concluído ou Parcial.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-114">In progress – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="1dd5a-115">Isso significa que, para cada linha, toda a quantidade ou parte dela foi registrada em um diário de entrada.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-115">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   <span data-ttu-id="1dd5a-116">Não concluído – Mostra as linhas de recebimentos em que o processo está Nenhum ou Parcial.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-116">Not complete – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="1dd5a-117">Isso significa que, para cada linha, nada ou somente parte da quantidade foi registrada em um diário de entrada.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-117">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  
5. <span data-ttu-id="1dd5a-118">Expanda ou recolha a seção Opções de entrada.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-118">Expand or collapse the Arrival options section.</span></span>
6. <span data-ttu-id="1dd5a-119">No campo Dias à frente, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-119">In the Days forward field, type a value.</span></span>
    * <span data-ttu-id="1dd5a-120">Isso definirá um filtro para mostrar as linhas de recebimento esperadas para o recebimento nos próximos dias (dependendo do número que você definiu).</span><span class="sxs-lookup"><span data-stu-id="1dd5a-120">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="1dd5a-121">No campo Dias atrás, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-121">In the Days back field, type a value.</span></span>
    * <span data-ttu-id="1dd5a-122">Isso definirá um filtro para mostrar as linhas de recebimento esperadas para o recebimento a alguns dias atrás.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-122">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="1dd5a-123">No campo Depósito, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-123">In the Warehouses field, type a value.</span></span>
    * <span data-ttu-id="1dd5a-124">Filtrar um ou mais depósitos.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-124">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="1dd5a-125">No campo Modo de entrega, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-125">In the Mode of delivery field, select a value.</span></span>
    * <span data-ttu-id="1dd5a-126">Isso definirá um filtro para mostrar apenas as linhas de recebimento com esse Modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-126">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="1dd5a-127">No campo Nome, selecione WHS.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-127">In the Name field, select WHS.</span></span>
11. <span data-ttu-id="1dd5a-128">No campo Depósito, selecione o depósito 24.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-128">In the Warehouse field, select warehouse 24.</span></span>
    * <span data-ttu-id="1dd5a-129">Este é o depósito padrão que será usado para as linhas de recebimento registradas que usam este perfil.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-129">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="1dd5a-130">No campo Local, selecione Baydoor.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-130">In the Location field, select Baydoor.</span></span>
    * <span data-ttu-id="1dd5a-131">Esta é a localização padrão que será usada para as linhas de recebimento registradas que usam este perfil.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-131">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="1dd5a-132">Expanda ou recolha a seção Detalhes da consulta de entrada.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-132">Expand or collapse the Arrival query details section.</span></span>
14. <span data-ttu-id="1dd5a-133">No campo Restringir ao local, selecione o local 2.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-133">In the Restrict to site field, select site 2.</span></span>
    * <span data-ttu-id="1dd5a-134">Isso definirá um filtro para mostrar apenas as linhas de recebimento com esse local.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-134">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="1dd5a-135">Defina a opção Ordens de compra como Sim.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-135">Set the Purchase orders option to Yes.</span></span>
    * <span data-ttu-id="1dd5a-136">Selecione as linhas de recebimento das ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-136">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="1dd5a-137">Defina a opção Ordens de transferência como Sim.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-137">Set the Transfer orders option to Yes.</span></span>
    * <span data-ttu-id="1dd5a-138">Selecione as linhas de recebimento das ordens de transferência.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-138">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="1dd5a-139">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-139">Click Save.</span></span>
18. <span data-ttu-id="1dd5a-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1dd5a-140">Close the page.</span></span>

