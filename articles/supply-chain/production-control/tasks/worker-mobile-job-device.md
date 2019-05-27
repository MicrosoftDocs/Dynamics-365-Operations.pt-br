---
title: Configurar um trabalhador usando um dispositivo de trabalho móvel
description: Este procedimento mostra como atribuir as funções corretas na conta de usuário de um trabalhador e, em seguida, habilitá-lo para fazer registros de chão de fábrica.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bb4d806810660e55ef13a9ff21c07e0ce194496
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571349"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="3ec0f-103">Configurar um trabalhador usando um dispositivo de trabalho móvel</span><span class="sxs-lookup"><span data-stu-id="3ec0f-103">Configure a worker using the mobile job device</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3ec0f-104">Este procedimento mostra como atribuir as funções corretas na conta de usuário de um trabalhador e, em seguida, habilitá-lo para fazer registros de chão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-104">This procedure shows you how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>


## <a name="assign-roles-to-user-account"></a><span data-ttu-id="3ec0f-105">Atribua funções à conta do usuário</span><span class="sxs-lookup"><span data-stu-id="3ec0f-105">Assign roles to user account</span></span>
1. <span data-ttu-id="3ec0f-106">Vá para Administração do sistema > Usuários > Usuários.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="3ec0f-107">Use o Filtro Rápido para filtrar pelo nome de um trabalhador no qual a conta de usuário está associada à função do operador de máquina.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-107">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="3ec0f-108">Nos dados de exemplo, o nome será Shannon.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-108">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="3ec0f-109">Realce o registro da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-109">Highlight the user account record.</span></span>
4. <span data-ttu-id="3ec0f-110">Na lista, clique no link “Nome” na linha selecionada para exibir os detalhes da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-110">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="3ec0f-111">Na árvore, selecione 'Funções\operador de Máquina'.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-111">In the tree, select 'Roles\Machine operator'.</span></span>
6. <span data-ttu-id="3ec0f-112">Feche a página detalhes da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-112">Close the user account details page.</span></span>
7. <span data-ttu-id="3ec0f-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-113">Close the page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="3ec0f-114">Configure a conta do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-114">Configure worker account.</span></span>
1. <span data-ttu-id="3ec0f-115">Vá para Recursos humanos > Trabalhadores > Trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-115">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="3ec0f-116">Use o Filtro Rápido para filtrar pelo nome de um trabalhador no qual a conta de usuário está associada à função do operador de máquina.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-116">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="3ec0f-117">Nos dados de exemplo, o nome será Shannon.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-117">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="3ec0f-118">Realce o registro da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-118">Highlight the user account record.</span></span>
4. <span data-ttu-id="3ec0f-119">Na lista, clique no link “Nome” na linha selecionada para exibir os detalhes da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-119">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="3ec0f-120">Clique na guia Emprego.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-120">Click the Employment tab.</span></span>
6. <span data-ttu-id="3ec0f-121">Expanda a Guia Rápida Registro de horário e clique em Ativar nos terminais de registro.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-121">Expand the Time registration FastTab and click Activate on registration terminals.</span></span>
7. <span data-ttu-id="3ec0f-122">Clique em Ativar nos terminais de registro.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-122">Click Activate on registration terminals.</span></span>
8. <span data-ttu-id="3ec0f-123">No campo Grupo de cálculo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-123">In the Calculation group field, enter or select a value.</span></span>
9. <span data-ttu-id="3ec0f-124">No campo Grupo de Cálculo Padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-124">In the Default calculation group field, enter or select a value.</span></span>
10. <span data-ttu-id="3ec0f-125">No campo Grupo de Aprovação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-125">In the Approval group field, enter or select a value.</span></span>
11. <span data-ttu-id="3ec0f-126">No campo Perfil Padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-126">In the Standard profile field, enter or select a value.</span></span>
12. <span data-ttu-id="3ec0f-127">No campo Grupo de Perfil, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-127">In the Profile group field, enter or select a value.</span></span>
13. <span data-ttu-id="3ec0f-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-128">Click OK.</span></span>
14. <span data-ttu-id="3ec0f-129">Clique em Editar para inserir um número do crachá para o novo trabalhador de registro de horário.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-129">Click Edit to enter a badge number for the new time registration worker.</span></span>
15. <span data-ttu-id="3ec0f-130">No campo ID do Crachá, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-130">In the Badge ID field, type a value.</span></span>
16. <span data-ttu-id="3ec0f-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-131">Click Save.</span></span>
17. <span data-ttu-id="3ec0f-132">Use o atalho Salvar Registro.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-132">Use the SaveRecord shortcut.</span></span>
18. <span data-ttu-id="3ec0f-133">Fechar a página de detalhes do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-133">Close the worker details page.</span></span>
19. <span data-ttu-id="3ec0f-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-134">Close the page.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="3ec0f-135">Atribua o trabalhador ao grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-135">Assign worker to device group.</span></span>
1. <span data-ttu-id="3ec0f-136">Vá para Controle de Produção > Configuração > Execução de Fabricação > Configurar o Cartão de Trabalho para Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-136">Go to Production control > Setup > Manufacturing execution > Configure job card for devices.</span></span>
2. <span data-ttu-id="3ec0f-137">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-137">Click Add.</span></span>
3. <span data-ttu-id="3ec0f-138">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="3ec0f-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-139">Click OK.</span></span>
5. <span data-ttu-id="3ec0f-140">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-140">Click Edit.</span></span>
6. <span data-ttu-id="3ec0f-141">No campo Unidade de Produção, você pode definir o filtro padrão para o trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-141">In the Production unit field, you can set the default filter for the worker.</span></span> <span data-ttu-id="3ec0f-142">Isso garantirá que somente os trabalhos de produção da unidade de produção selecionada serão exibidos quando o trabalhador fizer logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-142">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span>
7. <span data-ttu-id="3ec0f-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3ec0f-143">Close the page.</span></span>

