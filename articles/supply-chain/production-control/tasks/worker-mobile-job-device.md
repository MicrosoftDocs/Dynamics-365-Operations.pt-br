---
title: Configurar um trabalhador usando um dispositivo de trabalho móvel
description: Este tópico explica como atribuir as funções corretas na conta de usuário de um trabalhador e, em seguida, habilitá-lo para fazer registros de chão de fábrica.
author: ShylaThompson
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6e45ea8fdbe30436badd88d4972fda970755275
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835757"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="0e74a-103">Configurar um trabalhador usando um dispositivo de trabalho móvel</span><span class="sxs-lookup"><span data-stu-id="0e74a-103">Configure a worker using the mobile job device</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0e74a-104">Este tópico explica como atribuir as funções corretas na conta de usuário de um trabalhador e, em seguida, habilitá-lo para fazer registros de chão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="0e74a-104">This topic explains how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a><span data-ttu-id="0e74a-105">Verificar se um trabalhador teve uma determinada função atribuída a ele</span><span class="sxs-lookup"><span data-stu-id="0e74a-105">Verify that a worker is assigned a certain role</span></span>

<span data-ttu-id="0e74a-106">Por exemplo, verifique se a usuária "SHANNON" obteve a função de operadora de máquina antes de configurar a conta de trabalhador.</span><span class="sxs-lookup"><span data-stu-id="0e74a-106">For this example, verify that user "SHANNON" is assigned the machine operator role before you configure the worker account.</span></span>

1. <span data-ttu-id="0e74a-107">Vá para **Painel de navegação > Módulos > Administração do sistema > Usuários > Usuários**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="0e74a-108">Procure um usuário no filtro rápido.</span><span class="sxs-lookup"><span data-stu-id="0e74a-108">Search for a user in the quick filter.</span></span> <span data-ttu-id="0e74a-109">Neste exemplo, insira `shannon`.</span><span class="sxs-lookup"><span data-stu-id="0e74a-109">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="0e74a-110">Selecione o link na coluna **ID do usuário** da conta de usuário que aparece.</span><span class="sxs-lookup"><span data-stu-id="0e74a-110">Select the link in the **User ID** column of the user account that appears.</span></span>
4. <span data-ttu-id="0e74a-111">Na árvore **Funções do usuário**, selecione **Funções > Operador de máquina**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-111">In the **User's roles** tree, select **Roles > Machine operator**.</span></span>
5. <span data-ttu-id="0e74a-112">Feche as páginas **detalhes do usuário** e **usuários** para retornar à home page.</span><span class="sxs-lookup"><span data-stu-id="0e74a-112">Close the **user details** and **users** pages to return to the home page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="0e74a-113">Configurar a conta do trabalhador</span><span class="sxs-lookup"><span data-stu-id="0e74a-113">Configure worker account</span></span>
1. <span data-ttu-id="0e74a-114">Vá para **Painel de navegação > Módulos > Recursos humanos > Trabalhadores > Trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-114">Go to **Navigation pane > Modules > Human resources > Workers > Workers**.</span></span>
2. <span data-ttu-id="0e74a-115">Procure um usuário no filtro rápido.</span><span class="sxs-lookup"><span data-stu-id="0e74a-115">Search for a user in the quick filter.</span></span> <span data-ttu-id="0e74a-116">Neste exemplo, insira `shannon`.</span><span class="sxs-lookup"><span data-stu-id="0e74a-116">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="0e74a-117">Selecione o link na coluna **Nome** da conta de usuário que aparece.</span><span class="sxs-lookup"><span data-stu-id="0e74a-117">Select the link in the **Name** column of the user account that appears.</span></span>
4. <span data-ttu-id="0e74a-118">Selecione a guia **Registro de horas**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-118">Select the **Time registration** tab.</span></span>
5. <span data-ttu-id="0e74a-119">Selecione **Ativar nos terminais de registro**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-119">Select **Activate on registration terminals**.</span></span>
6. <span data-ttu-id="0e74a-120">Insira ou selecione os valores nos seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="0e74a-120">Enter or select values in the following fields:</span></span>  

    - <span data-ttu-id="0e74a-121">**Grupo de cálculo**</span><span class="sxs-lookup"><span data-stu-id="0e74a-121">**Calculation group**</span></span>  
    - <span data-ttu-id="0e74a-122">**Grupo de cálculos padrão**</span><span class="sxs-lookup"><span data-stu-id="0e74a-122">**Default calculation group**</span></span>  
    - <span data-ttu-id="0e74a-123">**Grupo de aprovação**</span><span class="sxs-lookup"><span data-stu-id="0e74a-123">**Approval group**</span></span>  
    - <span data-ttu-id="0e74a-124">**Perfil padrão**</span><span class="sxs-lookup"><span data-stu-id="0e74a-124">**Standard profile**</span></span>  
    - <span data-ttu-id="0e74a-125">**Grupo de perfis**</span><span class="sxs-lookup"><span data-stu-id="0e74a-125">**Profile group**</span></span>  

7. <span data-ttu-id="0e74a-126">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-126">Select **OK**.</span></span>
8. <span data-ttu-id="0e74a-127">Selecione **Editar** para inserir um número do crachá para o novo trabalhador de registro de horário.</span><span class="sxs-lookup"><span data-stu-id="0e74a-127">Select **Edit** to enter a badge number for the new time registration worker.</span></span> <span data-ttu-id="0e74a-128">Insira um valor no campo **ID do Crachá**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-128">Enter a value in the **Badge ID** field.</span></span>
9. <span data-ttu-id="0e74a-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-129">Select **Save**.</span></span>
10. <span data-ttu-id="0e74a-130">Feche as páginas **Detalhes do trabalhador** e **Trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-130">Close the **Worker details** and **Workers** pages.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="0e74a-131">Atribuir o trabalhador ao grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0e74a-131">Assign worker to device group</span></span>
1. <span data-ttu-id="0e74a-132">Vá para **Controle de produção > Configuração > Execução de fabricação > Configurar cartão de trabalho para dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-132">Go to **Production control > Setup > Manufacturing execution > Configure job card for devices**.</span></span>
2. <span data-ttu-id="0e74a-133">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-133">Select **Add**.</span></span>
3. <span data-ttu-id="0e74a-134">Na lista, selecione o trabalhador desejado.</span><span class="sxs-lookup"><span data-stu-id="0e74a-134">In the list, select the desired worker.</span></span> <span data-ttu-id="0e74a-135">Neste exemplo, selecione **SHANNON**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-135">For this example, select **SHANNON**.</span></span>
4. <span data-ttu-id="0e74a-136">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-136">Select **OK**.</span></span>
5. <span data-ttu-id="0e74a-137">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0e74a-137">Select **Edit**.</span></span>
6. <span data-ttu-id="0e74a-138">No campo **Unidade de produção**, você pode definir o filtro padrão para o trabalhador.</span><span class="sxs-lookup"><span data-stu-id="0e74a-138">In the **Production unit** field, you can set the default filter for the worker.</span></span> <span data-ttu-id="0e74a-139">Isso garantirá que somente os trabalhos de produção da unidade de produção selecionada serão exibidos quando o trabalhador fizer logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e74a-139">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span> <span data-ttu-id="0e74a-140">Insira o valor desejado.</span><span class="sxs-lookup"><span data-stu-id="0e74a-140">Enter the desired value.</span></span>
7. <span data-ttu-id="0e74a-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0e74a-141">Close the page.</span></span>

