---
title: Habilitar o Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce
description: Este tópico explica como habilitar e testar o Azure Data Lake Storage para um ambiente do Dynamics 365 Commerce, que é um pré-requisito para habilitar recomendações de produto.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5887ae7983fd817a929a185327671b301808b354
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478227"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="a6344-103">Habilitar o Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a6344-103">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a6344-104">Este tópico explica como habilitar e testar o Azure Data Lake Storage para um ambiente do Dynamics 365 Commerce, que é um pré-requisito para habilitar recomendações de produto.</span><span class="sxs-lookup"><span data-stu-id="a6344-104">This topic explains how to enable and test Azure Data Lake Storage for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

<span data-ttu-id="a6344-105">Na solução Dynamics 365 Commerce, todas as informações de produto e de transação são rastreadas no Repositório de entidades do ambiente.</span><span class="sxs-lookup"><span data-stu-id="a6344-105">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="a6344-106">Para tornar esses dados acessíveis a outros serviços do Dynamics 365, como análises de dados, business intelligence e recomendações personalizadas, é necessário conectar o ambiente a uma solução Azure Data Lake Storage Gen 2 de propriedade do cliente.</span><span class="sxs-lookup"><span data-stu-id="a6344-106">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 solution.</span></span>

<span data-ttu-id="a6344-107">Como o Azure Data Lake Storage é configurado em um ambiente, todos os dados necessários são espelhados do Repositório de entidades e estão protegidos e sob controle do cliente.</span><span class="sxs-lookup"><span data-stu-id="a6344-107">As Azure Data Lake Storage is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="a6344-108">Se as recomendações de produto ou personalizadas também forem habilitadas no ambiente, a pilha de recomendações de produto receberá acesso à pasta dedicada no Azure Data Lake Storage para recuperar os dados do cliente e computar as recomendações com base nela.</span><span class="sxs-lookup"><span data-stu-id="a6344-108">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in Azure Data Lake Storage to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a6344-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a6344-109">Prerequisites</span></span>

<span data-ttu-id="a6344-110">Os clientes precisam ter o Azure Data Lake Storage configurado em uma assinatura do Azure de propriedade deles.</span><span class="sxs-lookup"><span data-stu-id="a6344-110">Customers need to have Azure Data Lake Storage configured in an Azure subscription that they own.</span></span> <span data-ttu-id="a6344-111">Este tópico não aborda a compra de uma assinatura do Azure nem a configuração de uma conta de armazenamento habilitada para o Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="a6344-111">This topic does not cover the purchase of an Azure subscription or the setup of an Azure Data Lake Storage-enabled storage account.</span></span>

<span data-ttu-id="a6344-112">Para obter mais informações sobre o Azure Data Lake Storage, consulte a [documentação oficial do Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="a6344-112">For more information about Azure Data Lake Storage, see [Azure Data Lake Storage Gen2 official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="a6344-113">Etapas da configuração</span><span class="sxs-lookup"><span data-stu-id="a6344-113">Configuration steps</span></span>

<span data-ttu-id="a6344-114">Esta seção aborda as etapas de configuração necessárias para habilitar o Azure Data Lake Storage em um ambiente conforme ele se relaciona com recomendações do produto.</span><span class="sxs-lookup"><span data-stu-id="a6344-114">This section covers the configuration steps necessary for enabling Azure Data Lake Storage in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="a6344-115">Para obter uma visão geral mais detalhada das etapas necessárias para habilitar o Azure Data Lake Storage, consulte [Disponibilizar o repositório de entidades como um Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="a6344-115">For a more in-depth overview of the steps required to enable Azure Data Lake Storage, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-azure-data-lake-storage-in-the-environment"></a><span data-ttu-id="a6344-116">Habilitar o Azure Data Lake Storage no ambiente</span><span class="sxs-lookup"><span data-stu-id="a6344-116">Enable Azure Data Lake Storage in the environment</span></span>

1. <span data-ttu-id="a6344-117">Faça logon no portal do back office do ambiente.</span><span class="sxs-lookup"><span data-stu-id="a6344-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="a6344-118">Procure **Parâmetros do Sistema** e navegue até a guia **Conexões de dados**.</span><span class="sxs-lookup"><span data-stu-id="a6344-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="a6344-119">Defina **Habilitar a integração do Data Lake** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a6344-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="a6344-120">Defina **Fluxo para Atualizar Data Lake** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a6344-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="a6344-121">Em seguida, insira as seguintes informações necessárias:</span><span class="sxs-lookup"><span data-stu-id="a6344-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="a6344-122">**ID do Aplicativo** // **Segredo do Aplicativo** // **Nome DNS** - necessárias para se conectar ao KeyVault onde o segredo do Azure Data Lake Storage está armazenado.</span><span class="sxs-lookup"><span data-stu-id="a6344-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the Azure Data Lake Storage secret is stored.</span></span>
    1. <span data-ttu-id="a6344-123">**Nome do segredo** - o nome do segredo armazenado no KeyVault e usado para autenticação com o Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="a6344-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with Azure Data Lake Storage.</span></span>
1. <span data-ttu-id="a6344-124">Salve as alterações no canto superior esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="a6344-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="a6344-125">A imagem a seguir mostra um exemplo de configuração do Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="a6344-125">The following image shows an example Azure Data Lake Storage configuration.</span></span>

![Exemplo de configuração do Azure Data Lake Storage](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a><span data-ttu-id="a6344-127">Testar a conexão do Azure Data Lake Storage</span><span class="sxs-lookup"><span data-stu-id="a6344-127">Test the Azure Data Lake Storage connection</span></span>

1. <span data-ttu-id="a6344-128">Teste a conexão com o KeyVault usando o link **Testar Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="a6344-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="a6344-129">Teste a conexão com o Azure Data Lake Storage usando o link **Testar Armazenamento do Azure**.</span><span class="sxs-lookup"><span data-stu-id="a6344-129">Test the connection to Azure Data Lake Storage using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="a6344-130">Se os testes falharem, verifique novamente se todas as informações do KeyVault adicionadas acima estão corretas e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="a6344-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="a6344-131">Depois que os testes de conexão forem bem-sucedidos, você deverá habilitar a atualização automática para o Repositório de entidades.</span><span class="sxs-lookup"><span data-stu-id="a6344-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="a6344-132">Para habilitar a atualização automática para o Repositório de entidades, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a6344-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="a6344-133">Procure **Repositório de entidades**.</span><span class="sxs-lookup"><span data-stu-id="a6344-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="a6344-134">Na lista à esquerda, navegue até a entrada **RetailSales** e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a6344-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="a6344-135">Certifique-se de que **Atualização Automática Habilitada** esteja definida como **Sim**, selecione **Atualizar** e, em seguida, **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a6344-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="a6344-136">A imagem a seguir mostra um exemplo de Repositório de entidades com atualização automática habilitada.</span><span class="sxs-lookup"><span data-stu-id="a6344-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Exemplo de Repositório de entidades com atualização automática habilitada](./media/exampleADLSConfig2.png)

<span data-ttu-id="a6344-138">O Azure Data Lake Storage agora está configurado para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="a6344-138">Azure Data Lake Storage is now configured for the environment.</span></span> 

<span data-ttu-id="a6344-139">Caso ainda não tenha sido concluído, siga as etapas para [habilitar as recomendações e personalização do produto](enable-product-recommendations.md) para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="a6344-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a6344-140">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a6344-140">Additional resources</span></span>

[<span data-ttu-id="a6344-141">Disponibilizar o Repositório de Entidades como um Data Lake</span><span class="sxs-lookup"><span data-stu-id="a6344-141">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="a6344-142">Visão geral das recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="a6344-142">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="a6344-143">Habilitar recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="a6344-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="a6344-144">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="a6344-144">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="a6344-145">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="a6344-145">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="a6344-146">Habilitar recomendações de "comprar looks semelhantes"</span><span class="sxs-lookup"><span data-stu-id="a6344-146">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="a6344-147">Adicionar recomendações dos produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="a6344-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="a6344-148">Adicionar recomendações à tela de transações</span><span class="sxs-lookup"><span data-stu-id="a6344-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="a6344-149">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="a6344-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="a6344-150">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="a6344-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="a6344-151">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="a6344-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="a6344-152">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="a6344-152">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
