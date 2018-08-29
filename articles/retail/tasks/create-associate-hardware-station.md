--- 
title: "Criar estações de hardware"
description: "Este procedimento orienta como criar uma nova estação de hardware."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 3551e37c6aae37c01b5cacff8b908faaf75fb3e2
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="create-hardware-stations"></a><span data-ttu-id="d37d3-103">Criar estações de hardware</span><span class="sxs-lookup"><span data-stu-id="d37d3-103">Create hardware stations</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d37d3-104">Este procedimento orienta como criar uma nova estação de hardware.</span><span class="sxs-lookup"><span data-stu-id="d37d3-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="d37d3-105">Um novo perfil de hardware será criado e usado para adicionar novas estações de hardware a uma loja predefinida (canal).</span><span class="sxs-lookup"><span data-stu-id="d37d3-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="d37d3-106">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="d37d3-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="d37d3-107">Vá para Fundamentos do comércio > Canais > ..</span><span class="sxs-lookup"><span data-stu-id="d37d3-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="d37d3-108">> ..</span><span class="sxs-lookup"><span data-stu-id="d37d3-108">> ..</span></span> <span data-ttu-id="d37d3-109">> ..</span><span class="sxs-lookup"><span data-stu-id="d37d3-109">> ..</span></span> <span data-ttu-id="d37d3-110">> Perfis das estações de hardware.</span><span class="sxs-lookup"><span data-stu-id="d37d3-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="d37d3-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d37d3-111">Click New.</span></span>
3. <span data-ttu-id="d37d3-112">No campo ID da estação de hardware, digite 'TestHWProfile'.</span><span class="sxs-lookup"><span data-stu-id="d37d3-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="d37d3-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d37d3-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d37d3-114">No campo Número da porta, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d37d3-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="d37d3-115">No campo Perfil de hardware, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d37d3-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d37d3-116">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="d37d3-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="d37d3-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d37d3-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="d37d3-118">No campo Nome do pacote, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d37d3-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="d37d3-119">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d37d3-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d37d3-120">Este é o pacote padrão vindo com um novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="d37d3-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="d37d3-121">O número de versão pode variar.</span><span class="sxs-lookup"><span data-stu-id="d37d3-121">The version number may vary.</span></span>  
11. <span data-ttu-id="d37d3-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d37d3-122">Click Save.</span></span>
12. <span data-ttu-id="d37d3-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d37d3-123">Close the page.</span></span>
13. <span data-ttu-id="d37d3-124">Vá para Varejo e comércio > Canais > Todas as lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="d37d3-124">Go to Retail and commerce > Channels > All retail stores.</span></span>
14. <span data-ttu-id="d37d3-125">Na lista, selecione a linha 17.</span><span class="sxs-lookup"><span data-stu-id="d37d3-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="d37d3-126">Se você estiver usando a empresa de dados de demonstração USRT, esta é a loja Houston.</span><span class="sxs-lookup"><span data-stu-id="d37d3-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="d37d3-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d37d3-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="d37d3-128">Ative/desative a expansão da seção Estações de hardware.</span><span class="sxs-lookup"><span data-stu-id="d37d3-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="d37d3-129">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d37d3-129">Click Add.</span></span>
18. <span data-ttu-id="d37d3-130">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d37d3-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="d37d3-131">No campo ID do perfil, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d37d3-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="d37d3-132">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="d37d3-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d37d3-133">Este deve ser o novo perfil da estação de hardware criado nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="d37d3-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="d37d3-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d37d3-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="d37d3-135">No campo Nome do host, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d37d3-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="d37d3-136">No campo ID do terminal de TEF, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d37d3-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="d37d3-137">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d37d3-137">Click Save.</span></span>


