---
title: Habilitar propostas de orçamento (versão prévia)
description: Este tópico explica como habilitar o recurso de proposta de orçamento no Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: d8443c4e3e6f3d3a90acedc7c05b2846d6b68369
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646196"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="b739d-103">Habilitar propostas de orçamento (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="b739d-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="b739d-104">Este tópico explica como habilitar o recurso de proposta de orçamento no Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="b739d-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="b739d-105">Use as informações da página de ambiente no Microsoft Dynamics Lifecycle Services (LCs) para se conectar à instância principal do Azure SQL para esse ambiente.</span><span class="sxs-lookup"><span data-stu-id="b739d-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="b739d-106">Execute o comando Transact-SQL (T-SQL) a seguir para ativar as versões piloto no ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="b739d-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="b739d-107">(Talvez seja necessário ativar o acesso ao seu endereço IP no LCS antes de se conectar remotamente ao servidor de objetos de aplicativo \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="b739d-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="b739d-108">Se a sua implantação do Microsoft Dynamics 365 Finance for uma implantação do Service Fabric, você pode ignorar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="b739d-108">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="b739d-109">A equipe do Finance Insights já deve ter ativado a versão piloto para você.</span><span class="sxs-lookup"><span data-stu-id="b739d-109">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="b739d-110">Se você não vir o recurso no espaço de trabalho **Gerenciamento de recursos** ou se tiver problemas ao tentar ativá-lo, envie um email para a [Equipe de versão prévia do aplicativo Finance Insights](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b739d-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, send email to the [Finance Insights App Preview team](mailto:fiap@microsoft.com).</span></span>

2. <span data-ttu-id="b739d-111">Abra o espaço de trabalho **Gerenciamento de recursos** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b739d-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="b739d-112">Selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="b739d-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="b739d-113">Procure por **Propostas de orçamento** e ative esse recurso.</span><span class="sxs-lookup"><span data-stu-id="b739d-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="b739d-114">Acesse **Orçamento \> Configuração \> Orçamento básico \> Proposta de orçamento (versão prévia)** e selecione **Habilitar recurso**.</span><span class="sxs-lookup"><span data-stu-id="b739d-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="b739d-115">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="b739d-115">Privacy notice</span></span>
<span data-ttu-id="b739d-116">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="b739d-116">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
