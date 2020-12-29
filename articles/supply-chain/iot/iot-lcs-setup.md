---
title: Instale o suplemento de Inteligência de IoT no LCS
description: Este tópico explica como instalar o suplemento de Inteligência de IoT no Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ad8b33633646f27bc368dc4bbedc1eb64c150a9f
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422495"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="cd4bf-103">Instale o suplemento de Inteligência de IoT no LCS</span><span class="sxs-lookup"><span data-stu-id="cd4bf-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cd4bf-104">Este tópico explica como instalar o suplemento de Inteligência de IoT no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="cd4bf-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="cd4bf-105">Observe que não é possível instalar suplementos em um ambiente de demonstração/avaliação.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-105">Note that add-ins cannot be installed on a demo/trial environment.</span></span> <span data-ttu-id="cd4bf-106">Para poder instalar o suplemento, você deve [criar os recursos do Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="cd4bf-106">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="cd4bf-107">Configurar o ambiente LCS</span><span class="sxs-lookup"><span data-stu-id="cd4bf-107">Set up the LCS environment</span></span>

1. <span data-ttu-id="cd4bf-108">Abra o LCS e vá para o seu ambiente do Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-108">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="cd4bf-109">Role até a seção **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-109">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="cd4bf-110">Selecione **Instalar um novo suplemento** para mostrar a lista de suplementos que foram habilitados para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-110">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="cd4bf-111">Na caixa de diálogo **Selecionar um suplemento para instalar**, selecione a **Inteligência de IoT**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-111">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="cd4bf-112">Na caixa de diálogo **Configuração do suplemento**, forneça os detalhes do seu Hub IoT e do cache de Redis.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-112">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="cd4bf-113">Você pode encontrar os valores necessários no cofre de chaves criado em [Criar recursos do Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="cd4bf-113">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="cd4bf-114">**ID do locatário** – No portal do Azure, acesse o cofre de chaves, e no painel à esquerda, selecione **Visão geral** e copie o valor **ID do diretório**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-114">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="cd4bf-115">Cole esse valor na **Suplemento de configuração**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-115">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="cd4bf-116">**URI do cofre de chaves de ponto de extremidade compatível com Hub de eventos IoT** – Vá para o cofre de chaves e, no painel de navegação à esquerda, selecione **Visão geral** e copie o valor **Nome DNS**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-116">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="cd4bf-117">Cole esse valor na **Suplemento de configuração**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-117">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="cd4bf-118">**Nome do segredo da empresa compatível com Hub de eventos IoT** – Vá para o cofre de chaves e, no painel de navegação à esquerda, selecione **Segredos** e copie o nome do segredo no qual a sequência de conexão do Hub de eventos do Hub IoT é armazenada.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-118">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="cd4bf-119">Cole esse valor na **Suplemento de configuração**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-119">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="cd4bf-120">**URI do cofre de chaves de cache Redis** – Vá para o cofre de chaves e, no painel de navegação à esquerda, selecione **Visão geral** e copie o valor **Nome DNS**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-120">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="cd4bf-121">Cole esse valor na **Suplemento de configuração**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-121">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="cd4bf-122">**Nome do segredo do cache Redis** – Vá para o cofre de chaves e, no painel de navegação à esquerda, selecione **Segredos** e copie o nome do segredo no qual a sequência de conexão do cache Redis do Hub IoT é armazenada.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-122">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="cd4bf-123">Cole esse valor na **Suplemento de configuração**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-123">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="cd4bf-124">Marque a caixa de seleção para aceitar os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-124">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="cd4bf-125">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-125">Select **Install**.</span></span>
8. <span data-ttu-id="cd4bf-126">Uma caixa de mensagem é exibida dizendo que "Suplemento foi disparado com êxito para a instalação".</span><span class="sxs-lookup"><span data-stu-id="cd4bf-126">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="cd4bf-127">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-127">Select **OK**.</span></span>

<span data-ttu-id="cd4bf-128">A configuração do LCS está concluída.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-128">LCS setup is now completed.</span></span> <span data-ttu-id="cd4bf-129">A próxima etapa é [configurar os cenários](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="cd4bf-129">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="cd4bf-130">Desinstalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="cd4bf-130">Uninstall the add-in</span></span>

1. <span data-ttu-id="cd4bf-131">Em Supply Chain Management, [desative os cenários](iot-scenario-setup.md#disable-a-scenario).</span><span class="sxs-lookup"><span data-stu-id="cd4bf-131">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#disable-a-scenario).</span></span>
2. <span data-ttu-id="cd4bf-132">Em LCS, navegue até os detalhes do ambiente Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-132">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="cd4bf-133">Role até a seção **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-133">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="cd4bf-134">Selecione **Desinstalar** para o suplemento de inteligência IOT.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-134">Select **Uninstall** for the IoT Intelligence add-in.</span></span>
