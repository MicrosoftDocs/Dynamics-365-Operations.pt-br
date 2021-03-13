---
title: Configuração da gravação dupla do Lifecycle Services
description: Este tópico explica como configurar uma conexão de gravação dupla do Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: df67e498b963af3ded7464f46f37bb4b2ca7d852
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127584"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="d9a2c-103">Configuração da gravação dupla do Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="d9a2c-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d9a2c-104">Este tópico explica como configurar uma conexão de gravação dupla entre um novo ambiente do Finance and Operations e um novo ambiente do Dataverse a partir do Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d9a2c-104">This topic explains how to set up a dual-write connection between a new Finance and Operations environment and a new Dataverse environment from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d9a2c-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d9a2c-105">Prerequisites</span></span>

<span data-ttu-id="d9a2c-106">Você deve ser um administrador para configurar uma conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-106">You must be an admin to set up a dual-write connection.</span></span>

+ <span data-ttu-id="d9a2c-107">Você deve ter acesso ao locatário.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-107">You must have access to the tenant.</span></span>
+ <span data-ttu-id="d9a2c-108">Você deve ser um administrador em ambientes de Finance and Operations e ambientes de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-108">You must be an admin in both Finance and Operations environments and Dataverse environments.</span></span>

## <a name="set-up-a-dual-write-connection"></a><span data-ttu-id="d9a2c-109">Configurar uma conexão de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="d9a2c-109">Set up a dual-write connection</span></span>

<span data-ttu-id="d9a2c-110">Siga essas etapas para configurar a conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-110">Follow these steps to set up the dual-write connection.</span></span>

1. <span data-ttu-id="d9a2c-111">Em LCS, vá para seu projeto.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-111">In LCS, go to your project.</span></span>
2. <span data-ttu-id="d9a2c-112">Selecione **Configurar** para implantar um novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-112">Select **Configure** to deploy a new environment.</span></span>
3. <span data-ttu-id="d9a2c-113">Selecione a versão.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-113">Select the version.</span></span> 
4. <span data-ttu-id="d9a2c-114">Selecione a topologia.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-114">Select the topology.</span></span> <span data-ttu-id="d9a2c-115">Se houver apenas uma topologia disponível, ela será automaticamente selecionada.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-115">If only one topology is available, it's automatically selected.</span></span>
5. <span data-ttu-id="d9a2c-116">Conclua as primeiras etapas do assistente de **Configurações de implantação**.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-116">Complete the first steps in the **Deployment settings** wizard.</span></span>
6. <span data-ttu-id="d9a2c-117">Na guia **Dataverse**, siga uma das etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="d9a2c-117">On the **Dataverse** tab, follow one of these steps:</span></span>

    - <span data-ttu-id="d9a2c-118">Se um ambiente do Dataverse já estiver provisionado para o seu locatário, você poderá selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-118">If a Dataverse environment is already provisioned for your tenant, you can select it.</span></span>

        1. <span data-ttu-id="d9a2c-119">Defina a opção **Configurar Dataverse** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-119">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="d9a2c-120">Na coluna **Ambientes disponíveis**, selecione o ambiente para integração com os dados de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-120">In the **Available environments** column, select the environment to integrate with your Finance and Operations data.</span></span> <span data-ttu-id="d9a2c-121">A lista inclui todos os ambientes nos quais você tem privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-121">The list includes all environments where you have admin privileges.</span></span>
        3. <span data-ttu-id="d9a2c-122">Marque a caixa de seleção **Concordar** para indicar que você concorda com os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-122">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![A guia Dataverse quando um ambiente do Dataverse já estiver provisionado para o seu locatário](../dual-write/media/lcs_setup_1.png)

    - <span data-ttu-id="d9a2c-124">Se o seu locatário ainda não tiver um ambiente do Dataverse, será fornecido um novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-124">If your tenant doesn't already have a Dataverse environment, a new environment will be provisioned.</span></span>

        1. <span data-ttu-id="d9a2c-125">Defina a opção **Configurar Dataverse** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-125">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="d9a2c-126">Inserir um nome para o ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-126">Enter a name for the Dataverse environment.</span></span>
        3. <span data-ttu-id="d9a2c-127">Selecione a região em que o ambiente será implantado.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-127">Select the region to deploy the environment in.</span></span>
        4. <span data-ttu-id="d9a2c-128">Selecione o idioma e a moeda padrão para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-128">Select the default language and currency for the environment.</span></span>

            > [!NOTE]
            > <span data-ttu-id="d9a2c-129">Não é possível alterar o idioma e a moeda posteriormente.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-129">You can't change the language and currency later.</span></span>

        5. <span data-ttu-id="d9a2c-130">Marque a caixa de seleção **Concordar** para indicar que você concorda com os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-130">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![A guia Dataverse quando seu locatário ainda não tiver um ambiente do Dataverse](../dual-write/media/lcs_setup_2.png)

7. <span data-ttu-id="d9a2c-132">Conclua as etapas restantes do assistente de **Configurações de implantação**.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-132">Complete the remaining steps in the **Deployment settings** wizard.</span></span>
8. <span data-ttu-id="d9a2c-133">Depois que o ambiente tiver um status de **Implantado**, abra a página de detalhes do ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-133">After the environment has a status of **Deployed**, open the environment details page.</span></span> <span data-ttu-id="d9a2c-134">A seção **Integração do Power Platform** mostra os nomes do ambiente Finance and Operations e do ambiente Dataverse vinculado.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-134">The **Power Platform Integration** section shows the names of the Finance and Operations environment and the Dataverse environment that are linked.</span></span>

    ![Seção Integração do Power Platform](../dual-write/media/lcs_setup_3.png)

9. <span data-ttu-id="d9a2c-136">Um administrador do ambiente Finance and Operations deve efetuar login nas LCS e selecionar **Vincular a CDS para que os aplicativos** concluam o link.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-136">An admin of the Finance and Operations environment must sign in to LCS and select **Link to CDS for Apps** to complete the link.</span></span> <span data-ttu-id="d9a2c-137">A página detalhes do ambiente mostra as informações de contato do administrador.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-137">The environment details page shows the admin's contact information.</span></span>

    <span data-ttu-id="d9a2c-138">Depois que o link for concluído, o status será atualizado para **Vincular ambiente concluído com êxito**.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-138">After the link is completed, the status is updated to **Environment linking successfully completed**.</span></span>

10. <span data-ttu-id="d9a2c-139">Para abrir o espaço de trabalho **Integração de dados** no ambiente do Finance and Operations e controlar os modelos que estão disponíveis, selecione **Vincular ao CDS para aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-139">To open the **Data integration** workspace in the Finance and Operations environment and control the templates that are available, select **Link to CDS for Apps**.</span></span>

    ![Botão Link para o CDS para aplicativos na seção informações sobre a seção Integração do Power Platform](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> <span data-ttu-id="d9a2c-141">Não é possível desvincular ambientes usando o LCS.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-141">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="d9a2c-142">Para desvincular um ambiente, abra o espaço de trabalho da **Integração de dados** no ambiente do Finance and Operations e selecione **Desvincular**.</span><span class="sxs-lookup"><span data-stu-id="d9a2c-142">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>

