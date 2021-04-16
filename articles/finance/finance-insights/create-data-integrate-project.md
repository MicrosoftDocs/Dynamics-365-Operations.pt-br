---
title: Criar um projeto de integrador de dados (versão prévia)
description: Este tópico explica como criar um projeto de integrador de dados.
author: ShivamPandey-msft
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2335721cfe8fd7ff3f76e3c7ca2560a56d45d583
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818671"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="21453-103">Criar um projeto de integrador de dados (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="21453-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="21453-104">Este tópico explica como criar um projeto de integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="21453-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="21453-105">Entre no Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="21453-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="21453-106">Vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione **Entidades de dados**.</span><span class="sxs-lookup"><span data-stu-id="21453-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="21453-107">Aguarde até que todas as entidades de dados tenham sido atualizadas antes de passar para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="21453-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="21453-108">Abra o [portal do Power Apps](https://make.powerapps.com/) e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21453-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="21453-109">Selecione o ambiente apropriado.</span><span class="sxs-lookup"><span data-stu-id="21453-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="21453-110">No painel de navegação esquerdo, selecione **Dados \> Conexões**.</span><span class="sxs-lookup"><span data-stu-id="21453-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="21453-111">Conecte a instâncias apropriadas dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="21453-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="21453-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="21453-112">Dynamics 365</span></span>
        - <span data-ttu-id="21453-113">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="21453-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="21453-114">Abra os [ambientes do Power Apps](https://admin.powerapps.com/environments) e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21453-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="21453-115">Selecione **Integrador de dados**.</span><span class="sxs-lookup"><span data-stu-id="21453-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="21453-116">Selecione **Conjuntos de conexão**.</span><span class="sxs-lookup"><span data-stu-id="21453-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="21453-117">Selecione **Novo conjunto de conexão**.</span><span class="sxs-lookup"><span data-stu-id="21453-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="21453-118">Digite o nome da conexão.</span><span class="sxs-lookup"><span data-stu-id="21453-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="21453-119">Selecione as conexões apropriadas para os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="21453-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="21453-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="21453-120">Dynamics 365</span></span>
        - <span data-ttu-id="21453-121">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="21453-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="21453-122">Selecione o mapeamento de organização apropriado.</span><span class="sxs-lookup"><span data-stu-id="21453-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="21453-123">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="21453-123">Select **Create**.</span></span>

5. <span data-ttu-id="21453-124">Abra os [ambientes do Power Apps](https://admin.powerapps.com/environments) e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21453-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="21453-125">Crie projetos de integração de dados para os seguintes modelos usando o conjunto de conexões que você acabou de criar:</span><span class="sxs-lookup"><span data-stu-id="21453-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="21453-126">Resultados de insights de pagamentos de clientes (CDS para Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="21453-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="21453-127">Resultados de série temporal de fluxo de caixa (CDS a Fin e Ops)</span><span class="sxs-lookup"><span data-stu-id="21453-127">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="21453-128">Resultados de série temporal de orçamento (CDS a Fin e Ops)</span><span class="sxs-lookup"><span data-stu-id="21453-128">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="21453-129">Defina o plano apropriado para cada projeto.</span><span class="sxs-lookup"><span data-stu-id="21453-129">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="21453-130">Se você não vir as entidades necessárias no CDS, vá para **Crédito e cobranças > Configuração > Insights do Finance > Parâmetros de insights do Finance**, habilite o recurso de previsões de pagamento de cliente e clique no botão **Criar modelo de previsão**.</span><span class="sxs-lookup"><span data-stu-id="21453-130">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="21453-131">Quando a implantação do modelo de IA é concluída (bem ou mal sucedida), as entidades do CDS necessárias para criar a integração serão implantadas no CDS.</span><span class="sxs-lookup"><span data-stu-id="21453-131">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="21453-132">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="21453-132">Privacy notice</span></span>

<span data-ttu-id="21453-133">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="21453-133">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]