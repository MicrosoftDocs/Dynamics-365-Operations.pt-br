---
title: Habilitar revisão de fluxo de caixa (versão prévia)
description: Este tópico explica como habilitar o recurso de previsões de fluxo de caixa no Finance Insights.
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
ms.openlocfilehash: ba8acb2191291e2abed5cabf234c19fe09e6c8ff
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222549"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="7dce5-103">Habilitar revisão de fluxo de caixa (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="7dce5-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="7dce5-104">Este tópico explica como habilitar o recurso de previsões de fluxo de caixa no Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="7dce5-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="7dce5-105">Para usar previsões de pagamento no fluxo de caixa, você deve configurar o recurso de previsões de pagamento de cliente conforme descrito em [Habilitar previsões de pagamento de cliente](enable-cust-paymnt-prediction.md).</span><span class="sxs-lookup"><span data-stu-id="7dce5-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="7dce5-106">Use as informações da página de ambiente no Microsoft Dynamics Lifecycle Services (LCs) para se conectar à instância principal do Azure SQL para esse ambiente.</span><span class="sxs-lookup"><span data-stu-id="7dce5-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="7dce5-107">Execute o comando Transact-SQL (T-SQL) a seguir para ativar as versões piloto no ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="7dce5-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="7dce5-108">(Talvez seja necessário ativar o acesso ao seu endereço IP no LCS antes de se conectar remotamente ao servidor de objetos de aplicativo \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="7dce5-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="7dce5-109">Ignore esta etapa se você estiver usando a versão 10.0.20 ou posterior, ou se você estiver usando uma implantação do Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="7dce5-109">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="7dce5-110">A equipe do Finance Insights já deve ter ativado a versão piloto para você.</span><span class="sxs-lookup"><span data-stu-id="7dce5-110">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="7dce5-111">Se você não vir o recurso no espalho de trabalho **Gerenciamento de recurso**, ou se você tiver problemas ao tentar ativá-lo, entre em contato com <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="7dce5-111">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="7dce5-112">Abra o espaço de trabalho **Gerenciamento de recursos** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7dce5-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="7dce5-113">Selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="7dce5-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="7dce5-114">Ativar os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="7dce5-114">Turn on the following features:</span></span>

        - <span data-ttu-id="7dce5-115">Novo controle de grade</span><span class="sxs-lookup"><span data-stu-id="7dce5-115">New grid control</span></span>
        - <span data-ttu-id="7dce5-116">Agrupamento em grades (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="7dce5-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="7dce5-117">Previsões de pagamento do cliente (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="7dce5-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="7dce5-118">Previsões de fluxo de caixa (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="7dce5-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="7dce5-119">Acesse **Gerenciamento de caixa e bancário \> Configuração de previsão do fluxo de caixa** e adiciona as contas de liquidez que deveriam ser incluídas nas previsões.</span><span class="sxs-lookup"><span data-stu-id="7dce5-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7dce5-120">Se as contas de liquidez não estiverem configuradas, o fluxo de caixa não poderá ser gerado.</span><span class="sxs-lookup"><span data-stu-id="7dce5-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="7dce5-121">Acesse **Gerenciamento de caixa e bancário \> Configuração \> Finance Insights (versão prévia) \> Previsões de fluxo de caixa (versão prévia)** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7dce5-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="7dce5-122">Na guia **Previsão de fluxo de caixa**, selecione **Habilitar recurso**.</span><span class="sxs-lookup"><span data-stu-id="7dce5-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="7dce5-123">Selecione **Criar modelo de previsão**.</span><span class="sxs-lookup"><span data-stu-id="7dce5-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="7dce5-124">Para obter mais informações sobre o recurso de previsão de fluxo de caixa, consulte [Previsão de fluxo de caixa](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="7dce5-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
