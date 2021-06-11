---
title: Configuração da gravação dupla do Lifecycle Services
description: Este tópico explica como configurar uma conexão de gravação dupla do Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103560"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="8f10b-103">Configuração da gravação dupla do Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="8f10b-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="8f10b-104">Este tópico explica como habilitar a gravação dupla do Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8f10b-104">This topic explains how to enable dual-write from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8f10b-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8f10b-105">Prerequisites</span></span>

<span data-ttu-id="8f10b-106">Você deve concluir a integração da Power Platform conforme descrito nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="8f10b-106">You must complete the Power Platform integration as described in the following topics:</span></span>

+ [<span data-ttu-id="8f10b-107">Integração do Power Platform - Habilitar durante a implantação do ambiente</span><span class="sxs-lookup"><span data-stu-id="8f10b-107">Power Platform Integration - Enable during environment deployment</span></span>](../../power-platform/overview.md#enable-during-environment-deployment)
+ [<span data-ttu-id="8f10b-108">Integração do Power Platform - Configurar depois da implantação do ambiente</span><span class="sxs-lookup"><span data-stu-id="8f10b-108">Power Platform integration - Set up after environment deployment</span></span>](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a><span data-ttu-id="8f10b-109">Configurar a gravação dupla para novos ambientes do Dataverse</span><span class="sxs-lookup"><span data-stu-id="8f10b-109">Set up dual-write for new Dataverse environments</span></span>

<span data-ttu-id="8f10b-110">Siga estas etapas para configurar a gravação dupla da página **Detalhes de ambiente** do LCS:</span><span class="sxs-lookup"><span data-stu-id="8f10b-110">Follow these steps to set up dual-write from LCS **Environment Details** page:</span></span>

1. <span data-ttu-id="8f10b-111">Na página **Detalhes de ambiente**, expanda a seção **Integração da Power Platform**.</span><span class="sxs-lookup"><span data-stu-id="8f10b-111">On the **Environment Details** page, expand the **Power Platform Integration** section.</span></span>

2. <span data-ttu-id="8f10b-112">Selecione o botão **Aplicativo de gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="8f10b-112">Select the **Dual-write application** button.</span></span>

    ![Integração com o Power Platform](media/powerplat_integration_step2.png)

3. <span data-ttu-id="8f10b-114">Analise os termos e condições e selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="8f10b-114">Review the terms and conditions, and then select **Configure**.</span></span>

4. <span data-ttu-id="8f10b-115">Selecione **OK** para continuar.</span><span class="sxs-lookup"><span data-stu-id="8f10b-115">Select **OK** to continue.</span></span>

5. <span data-ttu-id="8f10b-116">Você pode monitorar o progresso atualizando periodicamente a página de detalhes do ambiente.</span><span class="sxs-lookup"><span data-stu-id="8f10b-116">You can monitor the progress by periodically refreshing the environment details page.</span></span> <span data-ttu-id="8f10b-117">A configuração geralmente leva 30 minutos ou menos.</span><span class="sxs-lookup"><span data-stu-id="8f10b-117">Setup typically takes 30 minutes or less.</span></span>  

6. <span data-ttu-id="8f10b-118">Quando a configuração for concluída, uma mensagem informará a você se o processo foi bem-sucedido ou se houve uma falha.</span><span class="sxs-lookup"><span data-stu-id="8f10b-118">When the setup is complete, a message will inform you if the process was successful or if there was a failure.</span></span> <span data-ttu-id="8f10b-119">Se a configuração falhar, uma mensagem de erro relacionada será exibida.</span><span class="sxs-lookup"><span data-stu-id="8f10b-119">If the setup failed, then a related error message is displayed.</span></span> <span data-ttu-id="8f10b-120">Você deve corrigir qualquer erro antes de passar para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="8f10b-120">You must fix any errors before moving to the next step.</span></span>

7. <span data-ttu-id="8f10b-121">Selecione **Vincular ao ambiente da Power Platform** para criar um link entre o Dataverse e os bancos de dados do ambiente atual.</span><span class="sxs-lookup"><span data-stu-id="8f10b-121">Select **Link to Power Platform environment** to create a link between Dataverse and the current environment's databases.</span></span> <span data-ttu-id="8f10b-122">Isso geralmente leva menos de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="8f10b-122">This typically takes less than 5 minutes.</span></span>

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Vincular ao ambiente da Power Platform":::

8. <span data-ttu-id="8f10b-124">Quando a vinculação for concluída, um hiperlink será exibido.</span><span class="sxs-lookup"><span data-stu-id="8f10b-124">When the linking is complete, a hyperlink is displayed.</span></span> <span data-ttu-id="8f10b-125">Use a vinculação para entrar na área de administração de gravação dupla no ambiente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8f10b-125">Use the link to sign in to the dual-write administration area in the Finance and Operations environment.</span></span> <span data-ttu-id="8f10b-126">A partir daí, você pode configurar mapeamentos de entidade.</span><span class="sxs-lookup"><span data-stu-id="8f10b-126">From there, you can set up entity mappings.</span></span>

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a><span data-ttu-id="8f10b-127">Configurar a gravação dupla para um ambiente do Dataverse existente</span><span class="sxs-lookup"><span data-stu-id="8f10b-127">Set up dual-write for an existing Dataverse environment</span></span>

<span data-ttu-id="8f10b-128">Para configurar a gravação dupla para um ambiente do Dataverse existente, você deve criar um [tíquete de suporte](../../lifecycle-services/lcs-support.md) da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8f10b-128">To set up dual-write for an existing Dataverse environment, you must create a Microsoft [support ticket](../../lifecycle-services/lcs-support.md).</span></span> <span data-ttu-id="8f10b-129">O tíquete deve incluir:</span><span class="sxs-lookup"><span data-stu-id="8f10b-129">The ticket must include:</span></span>

+ <span data-ttu-id="8f10b-130">Sua ID de ambiente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8f10b-130">Your Finance and Operations environment ID.</span></span>
+ <span data-ttu-id="8f10b-131">O nome do seu ambiente do Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="8f10b-131">Your environment name from Lifecycle Services.</span></span>
+ <span data-ttu-id="8f10b-132">A ID da organização do Dataverse ou a ID do ambiente da Power Platform a partir do centro de administração da Power Platform.</span><span class="sxs-lookup"><span data-stu-id="8f10b-132">The Dataverse organization ID or Power Platform Environment ID from Power Platform Admin Center.</span></span> <span data-ttu-id="8f10b-133">Em seu tíquete, solicite que a ID seja a instância usada para integração da Power Platform.</span><span class="sxs-lookup"><span data-stu-id="8f10b-133">In your ticket, request that the ID be the instance used for Power Platform integration.</span></span>

> [!NOTE]
> <span data-ttu-id="8f10b-134">Não é possível desvincular ambientes usando o LCS.</span><span class="sxs-lookup"><span data-stu-id="8f10b-134">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="8f10b-135">Para desvincular um ambiente, abra o espaço de trabalho da **Integração de dados** no ambiente do Finance and Operations e selecione **Desvincular**.</span><span class="sxs-lookup"><span data-stu-id="8f10b-135">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
