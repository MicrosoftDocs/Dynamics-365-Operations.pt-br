---
title: Habilitar ADLS em um ambiente do Dynamics 365 Commerce
description: Este tópico explica como habilitar e testar o Azure Data Lake Storage (ADLS) para um ambiente do Dynamics 365 Commerce, que é um pré-requisito para habilitar recomendações de produto.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ba428765babb9ca7566da7a457368959b1c29083
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259739"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="1241e-103">Habilitar ADLS em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1241e-103">Enable ADLS in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1241e-104">Este tópico explica como habilitar e testar o Azure Data Lake Storage (ADLS) para um ambiente do Dynamics 365 Commerce, que é um pré-requisito para habilitar recomendações de produto.</span><span class="sxs-lookup"><span data-stu-id="1241e-104">This topic explains how to enable and test Azure Data Lake Storage (ADLS) for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="1241e-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="1241e-105">Overview</span></span>

<span data-ttu-id="1241e-106">Na solução Dynamics 365 Commerce, todas as informações de produto e de transação são rastreadas no Repositório de entidades do ambiente.</span><span class="sxs-lookup"><span data-stu-id="1241e-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="1241e-107">Para tornar esses dados acessíveis a outros serviços do Dynamics 365, como análises de dados, Business Intelligence e recomendações personalizadas, é necessário conectar o ambiente a uma solução Azure Data Lake Storage Gen 2 (ADLS) de propriedade do cliente.</span><span class="sxs-lookup"><span data-stu-id="1241e-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 (ADLS) solution.</span></span>

<span data-ttu-id="1241e-108">Como a ADLS é configurado em um ambiente, todos os dados necessários são espelhados do Repositório de entidades enquanto ainda estão sendo protegidos e sob controle do cliente.</span><span class="sxs-lookup"><span data-stu-id="1241e-108">As ADLS is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="1241e-109">Se as recomendações de produto ou personalizadas também forem habilitadas no ambiente, a pilha de recomendações de produto receberá acesso à pasta dedicada no ADLS para recuperar os dados do cliente e computar as recomendações com base nela.</span><span class="sxs-lookup"><span data-stu-id="1241e-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in ADLS to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1241e-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1241e-110">Prerequisites</span></span>

<span data-ttu-id="1241e-111">Os clientes precisam ter o ADLS configurado em uma assinatura do Azure que eles possuem.</span><span class="sxs-lookup"><span data-stu-id="1241e-111">Customers need to have ADLS configured in an Azure subscription that they own.</span></span> <span data-ttu-id="1241e-112">Este tópico não aborda a compra de uma assinatura do Azure nem a configuração de uma conta de armazenamento habilitada para o ADLS.</span><span class="sxs-lookup"><span data-stu-id="1241e-112">This topic does not cover the purchase of an Azure subscription or the setup of an ADLS-enabled storage account.</span></span>

<span data-ttu-id="1241e-113">Para obter mais informações sobre o ADLS, consulte a [documentação oficial do ADLS](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="1241e-113">For more information about ADLS, see [ADLS official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="1241e-114">Etapas da configuração</span><span class="sxs-lookup"><span data-stu-id="1241e-114">Configuration steps</span></span>

<span data-ttu-id="1241e-115">Esta seção aborda as etapas de configuração necessárias para habilitar o ADLS em um ambiente conforme ele se relaciona com as recomendações do produto.</span><span class="sxs-lookup"><span data-stu-id="1241e-115">This section covers the configuration steps necessary for enabling ADLS in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="1241e-116">Para obter uma visão geral mais detalhada das etapas necessárias para habilitar ADLS, consulte [Disponibilizar o Repositório de Entidades como um Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="1241e-116">For a more in-depth overview of the steps required to enable ADLS, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-adls-in-the-environment"></a><span data-ttu-id="1241e-117">Habilitar o ADLS no ambiente</span><span class="sxs-lookup"><span data-stu-id="1241e-117">Enable ADLS in the environment</span></span>

1. <span data-ttu-id="1241e-118">Faça logon no portal do back office do ambiente.</span><span class="sxs-lookup"><span data-stu-id="1241e-118">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="1241e-119">Procure **Parâmetros do Sistema** e navegue até a guia **Conexões de dados**.</span><span class="sxs-lookup"><span data-stu-id="1241e-119">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="1241e-120">Defina **Habilitar a integração do Data Lake** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="1241e-120">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="1241e-121">Defina **Fluxo para Atualizar Data Lake** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="1241e-121">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="1241e-122">Em seguida, insira as seguintes informações necessárias:</span><span class="sxs-lookup"><span data-stu-id="1241e-122">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="1241e-123">**ID do Aplicativo** // **Segredo do Aplicativo** // **Nome DNS** - necessárias para se conectar ao KeyVault onde o segredo do ADLS está armazenado.</span><span class="sxs-lookup"><span data-stu-id="1241e-123">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the ADLS secret is stored.</span></span>
    1. <span data-ttu-id="1241e-124">**Nome do segredo** - o nome do segredo armazenado no KeyVault e usado para autenticação com o ADLS.</span><span class="sxs-lookup"><span data-stu-id="1241e-124">**Secret name** - The secret name stored in KeyVault and used to authenticate with ADLS.</span></span>
1. <span data-ttu-id="1241e-125">Salve as alterações no canto superior esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="1241e-125">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="1241e-126">A imagem a seguir mostra um exemplo de configuração do ADLS.</span><span class="sxs-lookup"><span data-stu-id="1241e-126">The following image shows an example ADLS configuration.</span></span>

![Exemplo de configuração do ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a><span data-ttu-id="1241e-128">Testar a conexão do ADLS</span><span class="sxs-lookup"><span data-stu-id="1241e-128">Test the ADLS connection</span></span>

1. <span data-ttu-id="1241e-129">Teste a conexão com o KeyVault usando o link **Testar Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="1241e-129">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="1241e-130">Teste a conexão com o ADLS usando o link **Testar Armazenamento do Azure**.</span><span class="sxs-lookup"><span data-stu-id="1241e-130">Test the connection to ADLS using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="1241e-131">Se os testes falharem, verifique novamente se todas as informações do KeyVault adicionadas acima estão corretas e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="1241e-131">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="1241e-132">Depois que os testes de conexão forem bem-sucedidos, você deverá habilitar a atualização automática para o Repositório de entidades.</span><span class="sxs-lookup"><span data-stu-id="1241e-132">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="1241e-133">Para habilitar a atualização automática para o Repositório de entidades, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="1241e-133">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="1241e-134">Procure **Repositório de entidades**.</span><span class="sxs-lookup"><span data-stu-id="1241e-134">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="1241e-135">Na lista à esquerda, navegue até a entrada **RetailSales** e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1241e-135">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="1241e-136">Certifique-se de que **Atualização Automática Habilitada** esteja definida como **Sim**, selecione **Atualizar** e, em seguida, **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1241e-136">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="1241e-137">A imagem a seguir mostra um exemplo de Repositório de entidades com atualização automática habilitada.</span><span class="sxs-lookup"><span data-stu-id="1241e-137">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Exemplo de Repositório de entidades com atualização automática habilitada](./media/exampleADLSConfig2.png)

<span data-ttu-id="1241e-139">O ADLS agora está configurado para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="1241e-139">ADLS is now configured for the environment.</span></span> 

<span data-ttu-id="1241e-140">Caso ainda não tenha sido concluído, siga as etapas para [habilitar as recomendações e personalização do produto](enable-product-recommendations.md) para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="1241e-140">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1241e-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1241e-141">Additional resources</span></span>

[<span data-ttu-id="1241e-142">Disponibilizar o Repositório de Entidades como um Data Lake</span><span class="sxs-lookup"><span data-stu-id="1241e-142">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="1241e-143">Visão geral das recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="1241e-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="1241e-144">Habilitar recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="1241e-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="1241e-145">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="1241e-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="1241e-146">Cancelar recomendações personalizados</span><span class="sxs-lookup"><span data-stu-id="1241e-146">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="1241e-147">Adicionar recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="1241e-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="1241e-148">Adicionar recomendações à tela de transação</span><span class="sxs-lookup"><span data-stu-id="1241e-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="1241e-149">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="1241e-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="1241e-150">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="1241e-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="1241e-151">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="1241e-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="1241e-152">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="1241e-152">Product recommendations FAQ</span></span>](faq-recommendations.md)
