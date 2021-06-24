---
title: Habilitar propostas de orçamento (versão prévia)
description: Este tópico explica como habilitar o recurso de proposta de orçamento no Finance Insights.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.openlocfilehash: 948a3e051e5964c5c773cefd90c8587cf833a450
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222525"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="5a1ff-103">Habilitar propostas de orçamento (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="5a1ff-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5a1ff-104">Este tópico explica como habilitar o recurso de proposta de orçamento no Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="5a1ff-105">Use as informações da página de ambiente no Microsoft Dynamics Lifecycle Services (LCs) para se conectar à instância principal do Azure SQL para esse ambiente.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="5a1ff-106">Execute o comando Transact-SQL (T-SQL) a seguir para ativar as versões piloto no ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="5a1ff-107">(Talvez seja necessário ativar o acesso ao seu endereço IP no LCS antes de se conectar remotamente ao servidor de objetos de aplicativo \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="5a1ff-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="5a1ff-108">Ignore esta etapa se você estiver usando a versão 10.0.20 ou posterior, ou se você estiver usando uma implantação do Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-108">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="5a1ff-109">A equipe do Finance Insights já deve ter ativado a versão piloto para você.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-109">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="5a1ff-110">Se você não vir o recurso no espalho de trabalho **Gerenciamento de recurso**, ou se você tiver problemas ao tentar ativá-lo, entre em contato com <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="5a1ff-111">Abra o espaço de trabalho **Gerenciamento de recursos** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="5a1ff-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="5a1ff-112">Selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="5a1ff-113">Procure por **Propostas de orçamento** e ative esse recurso.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="5a1ff-114">Acesse **Orçamento \> Configuração \> Orçamento básico \> Proposta de orçamento (versão prévia)** e selecione **Habilitar recurso**.</span><span class="sxs-lookup"><span data-stu-id="5a1ff-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
