---
title: Recomendações de produtos personalizados
description: Este tópico contém informações sobre recomendações de produtos do Dynamics 365 for Retail que podem ser exibidas no dispositivo de ponto de venda (PDV).
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d6706cbb7630aeb230bc9eb1c187397897c9de68
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "326460"
---
# <a name="personalized-product-recommendations"></a><span data-ttu-id="106b0-103">Recomendações personalizadas de produtos</span><span class="sxs-lookup"><span data-stu-id="106b0-103">Personalized product recommendations</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="106b0-104">Estamos removendo a versão atual do serviço de recomendação de produto, pois estamos remodelando esse recurso em um algoritmo melhor com recursos mais novos orientados ao varejo.</span><span class="sxs-lookup"><span data-stu-id="106b0-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="106b0-105">Para obter mais informações consulte [Recursos removidos ou substituídos](../dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="106b0-105">For more information see [Removed or deprecated features](../dev-itpro/migration-upgrade/deprecated-features.md).</span></span>

<span data-ttu-id="106b0-106">No Dynamics 365 for Retail, as recomendações de produtos podem ser exibidas no dispositivo de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="106b0-106">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="106b0-107">As recomendações são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas.</span><span class="sxs-lookup"><span data-stu-id="106b0-107">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="106b0-108">Para fornecedores com grandes catálogos, recomendações ajudam o cliente com descoberta de produto.</span><span class="sxs-lookup"><span data-stu-id="106b0-108">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="106b0-109">Ao exibir produtos de acordo com os interesses e hábitos de compras de um cliente, as recomendações de produto podem ajudar os varejistas nas vendas suplementar e cruzada, e pode aumentar a retenção de clientes.</span><span class="sxs-lookup"><span data-stu-id="106b0-109">By showcasing products targeted to a customer's interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="106b0-110">No Dynamics 365 for Retail, as recomendações do produto são habilitadas pelos serviços cognitivos e aprendizado de máquina do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="106b0-110">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>

## <a name="scenarios"></a><span data-ttu-id="106b0-111">Cenários</span><span class="sxs-lookup"><span data-stu-id="106b0-111">Scenarios</span></span>

<span data-ttu-id="106b0-112">As recomendações de produto são habilitadas para os seguintes cenários de PDV.</span><span class="sxs-lookup"><span data-stu-id="106b0-112">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="106b0-113">Estão disponíveis no Cloud POS ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="106b0-113">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1. <span data-ttu-id="106b0-114">Na página **Detalhes de produto**:</span><span class="sxs-lookup"><span data-stu-id="106b0-114">On the **Product details** page:</span></span>

    - <span data-ttu-id="106b0-115">Se um associado da loja visita uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o mecanismo de recomendação sugere itens adicionais que provavelmente podem ser comprados juntos.</span><span class="sxs-lookup"><span data-stu-id="106b0-115">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
    - <span data-ttu-id="106b0-116">Se o associado da loja adicionar um cliente à transação e depois visitar uma página de **Detalhes de produto**, o mecanismo de recomendação fornece recomendações personalizadas usando o histórico de transação do cliente.</span><span class="sxs-lookup"><span data-stu-id="106b0-116">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

    <span data-ttu-id="106b0-117">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="106b0-117">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2. <span data-ttu-id="106b0-118">Na página **Transação**:</span><span class="sxs-lookup"><span data-stu-id="106b0-118">On the **Transaction** page:</span></span>

    - <span data-ttu-id="106b0-119">O mecanismo de recomendação sugere itens com base na lista inteira de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="106b0-119">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
    - <span data-ttu-id="106b0-120">Se o associado da loja adicionar um cliente à transação, o mecanismo de recomendação fornecerá recomendações pessoais usando o histórico de transação do cliente e a lista de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="106b0-120">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer's transaction history and the list of items in the basket.</span></span>

    > [!NOTE]
    > <span data-ttu-id="106b0-121">Para exibir recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="106b0-121">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="106b0-122">O controle das **Recomendações** deve ser colocado na página de **Transação**.</span><span class="sxs-lookup"><span data-stu-id="106b0-122">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span>

    <span data-ttu-id="106b0-123">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="106b0-123">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3. <span data-ttu-id="106b0-124">Na página **Detalhes de cliente**:</span><span class="sxs-lookup"><span data-stu-id="106b0-124">On the **Customer details** page:</span></span>

    - <span data-ttu-id="106b0-125">O mecanismo de recomendação sugere itens com base na ID de usuário e itens na lista de desejos do cliente.</span><span class="sxs-lookup"><span data-stu-id="106b0-125">The recommendation engine suggests items based on the user ID and items in the customer's wish list.</span></span>

    <span data-ttu-id="106b0-126">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="106b0-126">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="106b0-127">Configurar o Dynamics 365 for Retail para permitir recomendações PDV</span><span class="sxs-lookup"><span data-stu-id="106b0-127">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>

<span data-ttu-id="106b0-128">Para configurar recomendações de produto, você precisa fazer o seguinte.</span><span class="sxs-lookup"><span data-stu-id="106b0-128">To set up product recommendations, you need to do the following.</span></span>

1. <span data-ttu-id="106b0-129">Verifique se você escolheu correto a **Entidade legal** correta.</span><span class="sxs-lookup"><span data-stu-id="106b0-129">Make sure that you have selected the correct **Legal entity**.</span></span>
2. <span data-ttu-id="106b0-130">Navegue até **Repositório de entidades**, selecione **Vendas de varejo** e clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="106b0-130">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.</span></span> <span data-ttu-id="106b0-131">Isso usará os dados de demonstração (ou seus dados) do banco de dados operacional e irá movê-los para o repositório de entidades.</span><span class="sxs-lookup"><span data-stu-id="106b0-131">This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3. <span data-ttu-id="106b0-132">Opcional: Para exibir recomendações na tela de transação, vá para **Layout de tela**, escolha seu layout de tela, inicie o **Designer do layout da tela** e depois deixe o controle de **recomendações** onde necessário.</span><span class="sxs-lookup"><span data-stu-id="106b0-132">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>
4. <span data-ttu-id="106b0-133">Vá para **Parâmetros de varejo**, selecione **Aprendizado de máquina**, selecione **Sim** em **Habilitar recomendações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="106b0-133">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5. <span data-ttu-id="106b0-134">Para consultar recomendações no PDV, rode o trabalho de configuração global **1110**.</span><span class="sxs-lookup"><span data-stu-id="106b0-134">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="106b0-135">Para refletir as alterações feitas ao designer de layout de tela do PDV, rode o trabalho de configuração de canal **1070**.</span><span class="sxs-lookup"><span data-stu-id="106b0-135">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="106b0-136">Como funciona?</span><span class="sxs-lookup"><span data-stu-id="106b0-136">How does it work?</span></span>

<span data-ttu-id="106b0-137">Quando você atualiza a entidade **Loja de entidade**, as ações a seguir ocorrem.</span><span class="sxs-lookup"><span data-stu-id="106b0-137">When you refresh the **Entity store** entity, the following actions take place.</span></span>

- <span data-ttu-id="106b0-138">Os dados no formato exigido pelos serviços cognitivos são extraídos do banco de dados operacional do Dynamics 365 for Retail e enviados para a loja de entidade.</span><span class="sxs-lookup"><span data-stu-id="106b0-138">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
- <span data-ttu-id="106b0-139">Os dados são usados por Azure Data Factory (ADF) para limpar os dados usando scripts em conjunto como parte das atividades do ADF.</span><span class="sxs-lookup"><span data-stu-id="106b0-139">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="106b0-140">Os dados limpos são armazenados no armazenamento blob.</span><span class="sxs-lookup"><span data-stu-id="106b0-140">Cleansed data is stored in blob storage.</span></span>
- <span data-ttu-id="106b0-141">Os dados do armazenamento de blob são usados pelo API dos serviços cognitivos para treinar um modelo de recomendação.</span><span class="sxs-lookup"><span data-stu-id="106b0-141">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="106b0-142">Quando você ativa **Habilitar recomendações** e executa os trabalhos de configuração, as ações a seguir ocorrem.</span><span class="sxs-lookup"><span data-stu-id="106b0-142">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

- <span data-ttu-id="106b0-143">As credenciais de modelo e ID são coletados da API e armazenadas no banco de dados operacional do Dynamics 365 for Retail, no web.config para AOS, bem como no servidor de varejo.</span><span class="sxs-lookup"><span data-stu-id="106b0-143">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
- <span data-ttu-id="106b0-144">As credenciais de modelo e ID tornam-se disponíveis ao CRT para que as chamadas de recomendações de produto do Cloud POS e MPOS no modo online podem ser liquidadas.</span><span class="sxs-lookup"><span data-stu-id="106b0-144">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="106b0-145">Solucionar problemas em que as Recomendações de produto já estejam habilitadas</span><span class="sxs-lookup"><span data-stu-id="106b0-145">Troubleshoot issues where you have Product recommendations already enabled</span></span>

- <span data-ttu-id="106b0-146">Navegue até **Parâmetros de Varejo** \> **Aprendizado de máquina** \> **Desabilitar recomendações de produtos** e execute **Trabalho de configuração global \[1110\]**.</span><span class="sxs-lookup"><span data-stu-id="106b0-146">Navigate to **Retail Parameters** \> **Machine learning** \> **Disable product recommendations** and run **Global configuration job \[1110\]**.</span></span> <span data-ttu-id="106b0-147">Se não conseguir localizar a guia **Aprendizado de máquina**, entre em contato com o suporte do Dynamics.</span><span class="sxs-lookup"><span data-stu-id="106b0-147">If you are not able to locate **Machine learning** tab, please contact Dynamics Support.</span></span>
- <span data-ttu-id="106b0-148">Se você adicionou o **Controle de recomendações** à sua tela de transação usando o **Designer do layout da tela**, remova-o também.</span><span class="sxs-lookup"><span data-stu-id="106b0-148">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="106b0-149">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="106b0-149">Additional resources</span></span>

[<span data-ttu-id="106b0-150">Adicionar um controle de recomendações à página de transação em um dispositivo do PDV</span><span class="sxs-lookup"><span data-stu-id="106b0-150">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)
