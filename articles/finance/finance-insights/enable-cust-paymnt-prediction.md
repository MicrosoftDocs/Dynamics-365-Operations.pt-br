---
title: Habilitar previsões de pagamento do cliente (versão prévia)
description: Este tópico explica como habilitar e configurar o recurso de previsões de pagamento de cliente no Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 584c1af5f9252a4b8c88a8866a64184bd0595b2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009409"
---
# <a name="enable-customer-payment-predictions-preview"></a><span data-ttu-id="83b25-103">Habilitar previsões de pagamento do cliente (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="83b25-103">Enable customer payment predictions (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="83b25-104">Este tópico explica como habilitar e configurar o recurso de previsões de pagamento de cliente no Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="83b25-104">This topic explains how to turn on and configure the Customer payment predictions feature in Finance insights.</span></span> <span data-ttu-id="83b25-105">Para ativar o recurso no espaço de trabalho **Gerenciamento de recursos** e inserir definições de configuração, acesse a página **Parâmetros do Financial insights**.</span><span class="sxs-lookup"><span data-stu-id="83b25-105">You turn on the feature in the **Feature management** workspace and enter configuration settings on the **Financial insights parameters** page.</span></span> <span data-ttu-id="83b25-106">Este tópico também inclui informações que podem ajudar você a usar o recurso com eficiência.</span><span class="sxs-lookup"><span data-stu-id="83b25-106">This topic also includes information that can help you effectively use the feature.</span></span>

> [!NOTE]
> <span data-ttu-id="83b25-107">Antes de concluir as etapas a seguir, certifique-se de concluir as etapas de pré-requisito no tópico [Configuração do Finance Insights](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="83b25-107">Before you complete the following steps, be sure to complete the prerequisite steps in the [Configure for Finance insights](configure-for-fin-insites.md) topic.</span></span>

1. <span data-ttu-id="83b25-108">Use as informações da página de ambiente no Microsoft Dynamics Lifecycle Services (LCs) para se conectar à instância principal do Azure SQL para esse ambiente.</span><span class="sxs-lookup"><span data-stu-id="83b25-108">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="83b25-109">Execute o comando Transact-SQL (T-SQL) a seguir para ativar as versões piloto no ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="83b25-109">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="83b25-110">(Talvez seja necessário ativar o acesso ao seu endereço IP no LCS antes de se conectar remotamente ao servidor de objetos de aplicativo \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="83b25-110">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > <span data-ttu-id="83b25-111">Se a sua implantação do Microsoft Dynamics 365 Finance for uma implantação do Service Fabric, você pode ignorar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="83b25-111">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="83b25-112">A equipe do Finance Insights já deve ter ativado a versão piloto para você.</span><span class="sxs-lookup"><span data-stu-id="83b25-112">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="83b25-113">Se você não vir o recurso no espaço de trabalho **Gerenciamento de recursos** ou se tiver problemas ao tentar ligá-lo, contate <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="83b25-113">If you don't see the feature in the **Feature management** workspace, or if experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="83b25-114">Habilite o recurso de informações de pagamento do cliente:</span><span class="sxs-lookup"><span data-stu-id="83b25-114">Turn on the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="83b25-115">Vá para **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="83b25-115">Go to **System administration \> Workspaces \> Feature management**.</span></span>
    2. <span data-ttu-id="83b25-116">Localize o recurso que é chamado de **Informações de pagamento do cliente (versão prévia)**.</span><span class="sxs-lookup"><span data-stu-id="83b25-116">Find the feature that is named **Customer payment insights (preview)**.</span></span>
    3. <span data-ttu-id="83b25-117">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="83b25-117">Select **Enable now**.</span></span>

    <span data-ttu-id="83b25-118">O recurso de insights de pagamento do cliente agora está ativado e pronto para ser configurado.</span><span class="sxs-lookup"><span data-stu-id="83b25-118">The Customer payment insights feature is now turned on and ready to be configured.</span></span>

3. <span data-ttu-id="83b25-119">Configure o recurso de informações de pagamento do cliente:</span><span class="sxs-lookup"><span data-stu-id="83b25-119">Configure the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="83b25-120">Acesse **Crédito e cobranças \> Configuração \> Finance Insights \> Parâmetros do Finance Insights**.</span><span class="sxs-lookup"><span data-stu-id="83b25-120">Go to **Credit and collections \> Setup \> Finance insights \> Finance insights parameters**.</span></span>

        <span data-ttu-id="83b25-121">[![Parâmetros de informações financeiras antes do recurso ser configurado](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span><span class="sxs-lookup"><span data-stu-id="83b25-121">[![Financial insights parameters page before the feature is configured](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span></span>

    2. <span data-ttu-id="83b25-122">Na página **Parâmetros de informações financeiras**, na guia **Informações de pagamento do cliente**, selecione **Exibir os campos de dados usados no link do modelo de previsão** para abrir a página **Campos de dados para o modelo de previsão**.</span><span class="sxs-lookup"><span data-stu-id="83b25-122">On the **Financial insights parameters** page, on the **Customer payment insights** tab, select the **View the data fields used in the prediction model** link to open the **Data fields for prediction model** page.</span></span> <span data-ttu-id="83b25-123">Nela, você pode exibir a lista padrão de campos usados para criar o modelo de previsão de inteligência artificial (AI) para previsões de pagamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="83b25-123">There, you can view the default list of fields that are used to create the artificial intelligence (AI) prediction model for customer payment predictions.</span></span>

        <span data-ttu-id="83b25-124">Para usar a lista de campos padrão para criar o modelo de previsão, feche a página **Campos de dados para o modelo de previsão** e, na página **Parâmetros de informações financeiras**, defina a opção **Habilitar recurso** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="83b25-124">To use the default list of fields to create the prediction model, close the **Data fields for prediction model** page, and then, on the **Financial insights parameters** page, set the **Enable feature** option to **Yes**.</span></span>

    3. <span data-ttu-id="83b25-125">Especifique o período da transação "Muito atrasado" para definir o que o bucket de previsão **Muito atrasado** significa para seus negócios.</span><span class="sxs-lookup"><span data-stu-id="83b25-125">Specify the "very late" transaction period to define what the **Very late** prediction bucket means for your business.</span></span>

        <span data-ttu-id="83b25-126">Para cada fatura aberta, o sistema prevê a probabilidade de pagamento em três buckets: **Dentro do prazo**, **Atrasado** e **Muito atrasado**.</span><span class="sxs-lookup"><span data-stu-id="83b25-126">For each open invoice, the system predicts the probability of payment in three buckets: **On time**, **Late**, and **Very late**.</span></span>

        - <span data-ttu-id="83b25-127">**Dentro do prazo** – Esse bucket inclui pagamentos que são previstos na data de vencimento da transação ou antes dela.</span><span class="sxs-lookup"><span data-stu-id="83b25-127">**On time** – This bucket includes payments that are predicted to be paid on or before the transaction due date.</span></span>
        - <span data-ttu-id="83b25-128">**Atrasado** – Esse bucket inclui pagamentos que estão previstos para serem pagos após a data de vencimento da transação, mas antes do início do período "Muito atrasado" de transação.</span><span class="sxs-lookup"><span data-stu-id="83b25-128">**Late** – This bucket includes payments that are predicted to be paid after the transaction due date but before the start of the "very late" transaction period.</span></span>
        - <span data-ttu-id="83b25-129">**Muito atrasado** – Esse bucket inclui pagamentos que estão previstos para serem pagos após o início do período "Muito atrasado" de transação.</span><span class="sxs-lookup"><span data-stu-id="83b25-129">**Very late** – This bucket includes payments that are predicted to be paid after the start of the "very late" transaction period.</span></span>

        > [!NOTE]
        > <span data-ttu-id="83b25-130">Se você alterar o período da transação "Atrasado" e selecionar **Alterar limite de atraso** depois que o modelo de previsão de IA para pagamentos do cliente for criado, o modelo de previsão existente será excluído e um novo modelo será criado.</span><span class="sxs-lookup"><span data-stu-id="83b25-130">If you change the "very late" transaction period and select **Change late threshold** after the AI prediction model for customer payments has been created, the existing prediction model is deleted, and a new model is created.</span></span> <span data-ttu-id="83b25-131">O novo modelo de previsão moverá as transações para o período "Muito atrasado", com base nas configurações que foram inseridas para defini-lo.</span><span class="sxs-lookup"><span data-stu-id="83b25-131">The new prediction model will move transactions into the "very late" period, based on the settings that were entered to define it.</span></span>

    4. <span data-ttu-id="83b25-132">Depois de concluir a definição do período da transação "Muito atrasado", selecione **Criar modelo de previsão** para criar o modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="83b25-132">After you've finished defining the "very late" transaction period, select **Create prediction model** to create the prediction model.</span></span> <span data-ttu-id="83b25-133">A seção **Modelo de previsão** na página **Parâmetros de informações financeiras** mostra o status do modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="83b25-133">The **Prediction model** section on the **Financial insights parameters** page shows the status of the prediction model.</span></span>

        > [!NOTE]
        > <span data-ttu-id="83b25-134">A qualquer momento enquanto o modelo de previsão estiver sendo criado, você pode selecionar **Redefinir criação do modelo** para reiniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="83b25-134">At any time while the prediction model is being created, you can select **Reset model creation** to restart the process.</span></span>

    <span data-ttu-id="83b25-135">O recurso foi configurado e agora está pronto para ser usado.</span><span class="sxs-lookup"><span data-stu-id="83b25-135">The feature has now been configured and is ready to be used.</span></span>

<span data-ttu-id="83b25-136">Depois que o recurso for ativado e configurado e o modelo de previsão tiver sido criado e estiver funcionando, a seção **Modelo de previsão** da página **Parâmetros de informações financeiras** mostrará a precisão do modelo, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="83b25-136">After the feature has been turned on and configured, and the prediction model has been created and is working, the **Prediction model** section of the **Financial insights parameters** page shows the accuracy of the model, as shown in the following illustration.</span></span>

<span data-ttu-id="83b25-137">[![Precisão do modelo de previsão na página Parâmetros de informações financeiras](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span><span class="sxs-lookup"><span data-stu-id="83b25-137">[![Accuracy of the prediction model on the Financial insights parameters page](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span></span>

## <a name="release-details"></a><span data-ttu-id="83b25-138">Detalhes da liberação</span><span class="sxs-lookup"><span data-stu-id="83b25-138">Release details</span></span>

<span data-ttu-id="83b25-139">A versão prévia pública do Finance Insights está disponível para implantações de avaliação nos Estados Unidos da América, Europa e Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="83b25-139">Finance insights public preview is available for trial deployments in the United States of America, Europe, and the United Kingdom.</span></span> <span data-ttu-id="83b25-140">A Microsoft está adicionando suporte para mais regiões de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="83b25-140">Microsoft is incrementally adding support for more regions.</span></span>

<span data-ttu-id="83b25-141">Os recursos de versão preliminar pública só devem ser ativados em ambientes de área restrita de Camada 2.</span><span class="sxs-lookup"><span data-stu-id="83b25-141">Public preview features can and should be turned on only in Tier-2 sandbox environments.</span></span> <span data-ttu-id="83b25-142">A Configuração e os Modelos de IA criados em um ambiente de área restrita não podem ser migrados para o ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="83b25-142">Setup and AI models that are created in a sandbox environment can't be migrated to a production environment.</span></span> <span data-ttu-id="83b25-143">Para obter mais informações, consulte [Termos de uso suplementares para versões preliminares do Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span><span class="sxs-lookup"><span data-stu-id="83b25-143">For more information, see [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="83b25-144">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="83b25-144">Privacy notice</span></span>

<span data-ttu-id="83b25-145">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="83b25-145">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
