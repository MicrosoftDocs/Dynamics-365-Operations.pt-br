---
title: Criar e associar uma estação de hardware
description: Este procedimento orienta como criar uma nova estação de hardware.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 305308b0e4ba99aae4bf6f8f94041db570a25893
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141028"
---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="ff31d-103">Criar e associar uma estação de hardware</span><span class="sxs-lookup"><span data-stu-id="ff31d-103">Create and associate a hardware station</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ff31d-104">Este procedimento orienta como criar uma nova estação de hardware.</span><span class="sxs-lookup"><span data-stu-id="ff31d-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="ff31d-105">Um novo perfil de hardware será criado e usado para adicionar novas estações de hardware a uma loja predefinida (canal).</span><span class="sxs-lookup"><span data-stu-id="ff31d-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="ff31d-106">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="ff31d-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="ff31d-107">Vá para Fundamentos do comércio > Canais > ..</span><span class="sxs-lookup"><span data-stu-id="ff31d-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="ff31d-108">> ..</span><span class="sxs-lookup"><span data-stu-id="ff31d-108">> ..</span></span> <span data-ttu-id="ff31d-109">> ..</span><span class="sxs-lookup"><span data-stu-id="ff31d-109">> ..</span></span> <span data-ttu-id="ff31d-110">> Perfis das estações de hardware.</span><span class="sxs-lookup"><span data-stu-id="ff31d-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="ff31d-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ff31d-111">Click New.</span></span>
3. <span data-ttu-id="ff31d-112">No campo ID da estação de hardware, digite 'TestHWProfile'.</span><span class="sxs-lookup"><span data-stu-id="ff31d-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="ff31d-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ff31d-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="ff31d-114">No campo Número da porta, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ff31d-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="ff31d-115">No campo Perfil de hardware, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ff31d-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ff31d-116">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="ff31d-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="ff31d-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ff31d-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ff31d-118">No campo Nome do pacote, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ff31d-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="ff31d-119">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ff31d-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ff31d-120">Este é o pacote padrão vindo com um novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="ff31d-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="ff31d-121">O número de versão pode variar.</span><span class="sxs-lookup"><span data-stu-id="ff31d-121">The version number may vary.</span></span>  
11. <span data-ttu-id="ff31d-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ff31d-122">Click Save.</span></span>
12. <span data-ttu-id="ff31d-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ff31d-123">Close the page.</span></span>
13. <span data-ttu-id="ff31d-124">Vá para Retail e Commerce > Canais > Todas as lojas.</span><span class="sxs-lookup"><span data-stu-id="ff31d-124">Go to Retail and Commerce > Channels > All stores.</span></span>
14. <span data-ttu-id="ff31d-125">Na lista, selecione a linha 17.</span><span class="sxs-lookup"><span data-stu-id="ff31d-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="ff31d-126">Se você estiver usando a empresa de dados de demonstração USRT, esta é a loja Houston.</span><span class="sxs-lookup"><span data-stu-id="ff31d-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="ff31d-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ff31d-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="ff31d-128">Ative/desative a expansão da seção Estações de hardware.</span><span class="sxs-lookup"><span data-stu-id="ff31d-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="ff31d-129">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ff31d-129">Click Add.</span></span>
18. <span data-ttu-id="ff31d-130">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ff31d-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="ff31d-131">No campo ID do perfil, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ff31d-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="ff31d-132">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ff31d-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ff31d-133">Este deve ser o novo perfil da estação de hardware criado nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="ff31d-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="ff31d-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ff31d-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="ff31d-135">No campo Nome do host, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ff31d-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="ff31d-136">No campo ID do terminal de TEF, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ff31d-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="ff31d-137">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ff31d-137">Click Save.</span></span>
