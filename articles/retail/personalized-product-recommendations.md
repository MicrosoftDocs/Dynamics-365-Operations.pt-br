---
title: "Recomendações personalizadas de produtos"
description: "Este tópico contém informações sobre recomendações de produtos do Dynamics 365 for Retail que podem ser exibidas no dispositivo de ponto de venda (POS)."
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 368468a1c1cd023862f1405dddf3a90574edce22
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="personalized-product-recommendations"></a><span data-ttu-id="871ca-103">Recomendações personalizadas de produtos</span><span class="sxs-lookup"><span data-stu-id="871ca-103">Personalized product recommendations</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="871ca-104">Estamos removendo a versão atual do serviço de recomendação de produto, pois estamos remodelando esse recurso em um algoritmo melhor com recursos mais novos orientados ao varejo.</span><span class="sxs-lookup"><span data-stu-id="871ca-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="871ca-105">Para obter mais informações consulte [Recursos removidos ou substituídos](../dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="871ca-105">For more information see [Removed or deprecated features](../dev-itpro/migration-upgrade/deprecated-features.md).</span></span> <span data-ttu-id="871ca-106">Navegue até a parte inferior da página se estiver enfrentando problemas com recomendações de produto já habilitadas para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="871ca-106">Navigate to the bottom of the page if you are facing issues with already-enabled product recommendations for your environment.</span></span> 

<span data-ttu-id="871ca-107">No Dynamics 365 for Retail, as recomendações de produtos podem ser exibidas no dispositivo de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="871ca-107">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="871ca-108">As recomendações são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas.</span><span class="sxs-lookup"><span data-stu-id="871ca-108">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="871ca-109">Para fornecedores com grandes catálogos, recomendações ajudam o cliente com descoberta de produto.</span><span class="sxs-lookup"><span data-stu-id="871ca-109">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="871ca-110">Ao exibir produtos para determinado público de interesse e hábitos de compra, as recomendações de produto podem ajudar os varejistas com venda direta e cruzada, e pode aumentar a retenção de cliente.</span><span class="sxs-lookup"><span data-stu-id="871ca-110">By showcasing products targeted to a customer’s interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="871ca-111">No Dynamics 365 for Retail, as recomendações de produtos são suportadas por serviços cognitivos e aprendizado de máquina do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="871ca-111">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>


<a name="scenarios"></a><span data-ttu-id="871ca-112">Cenários</span><span class="sxs-lookup"><span data-stu-id="871ca-112">Scenarios</span></span>
---------

<span data-ttu-id="871ca-113">As recomendações de produto são habilitadas para os seguintes cenários de PDV.</span><span class="sxs-lookup"><span data-stu-id="871ca-113">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="871ca-114">Estão disponíveis no Cloud POS ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="871ca-114">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1.  <span data-ttu-id="871ca-115">Na página **Detalhes de produto**:</span><span class="sxs-lookup"><span data-stu-id="871ca-115">On the **Product details** page:</span></span>

-   <span data-ttu-id="871ca-116">Se um associado da loja visita uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o mecanismo de recomendação sugere itens adicionais que provavelmente podem ser comprados juntos.</span><span class="sxs-lookup"><span data-stu-id="871ca-116">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
-   <span data-ttu-id="871ca-117">Se o associado da loja adicionar um cliente à transação e depois visitar uma página de **Detalhes de produto**, o mecanismo de recomendação fornece recomendações personalizadas usando o histórico de transação do cliente.</span><span class="sxs-lookup"><span data-stu-id="871ca-117">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

<span data-ttu-id="871ca-118">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="871ca-118">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2.  <span data-ttu-id="871ca-119">Na página **Transação**:</span><span class="sxs-lookup"><span data-stu-id="871ca-119">On the **Transaction** page:</span></span>

-   <span data-ttu-id="871ca-120">O mecanismo de recomendação sugere itens com base na lista inteira de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="871ca-120">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
-   <span data-ttu-id="871ca-121">Se o associado da loja adicionar um cliente à transação, o mecanismo de recomendação fornece recomendações pessoais usando o histórico de transação do cliente e a lista de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="871ca-121">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer’s transaction history and the list of items in the basket.</span></span>

> [!NOTE]
> <span data-ttu-id="871ca-122">Para exibir as recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="871ca-122">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="871ca-123">O controle das **Recomendações** deve ser colocado na página de **Transação**.</span><span class="sxs-lookup"><span data-stu-id="871ca-123">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span> <span data-ttu-id="871ca-124">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="871ca-124">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3.  <span data-ttu-id="871ca-125">Na página **Detalhes de cliente**:</span><span class="sxs-lookup"><span data-stu-id="871ca-125">On the **Customer details** page:</span></span>
    -   <span data-ttu-id="871ca-126">O mecanismo de recomendação sugere itens com base na ID de usuário e itens na lista de desejo do cliente.</span><span class="sxs-lookup"><span data-stu-id="871ca-126">The recommendation engine suggests items based on the user ID and items in the customer’s wish list.</span></span>

<span data-ttu-id="871ca-127">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="871ca-127">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="871ca-128">Configurar o Dynamics 365 for Retail para habilitar recomendações de PDV</span><span class="sxs-lookup"><span data-stu-id="871ca-128">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>
<span data-ttu-id="871ca-129">Para configurar recomendações de produto, você precisa fazer o seguinte.</span><span class="sxs-lookup"><span data-stu-id="871ca-129">To set up product recommendations, you need to do the following.</span></span>

1.  <span data-ttu-id="871ca-130">Verifique se você escolheu correto a **Entidade legal** correta.</span><span class="sxs-lookup"><span data-stu-id="871ca-130">Make sure that you have selected the correct **Legal entity**.</span></span>
2.  <span data-ttu-id="871ca-131">Navegue até **Repositório de entidades**, selecione **Vendas de varejo** e clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="871ca-131">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.</span></span> <span data-ttu-id="871ca-132">Isso usará os dados de demonstração (ou seus dados) do banco de dados operacional e irá movê-los para o repositório de entidades.</span><span class="sxs-lookup"><span data-stu-id="871ca-132">This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3.  <span data-ttu-id="871ca-133">Opcional: Para exibir recomendações na tela de transação, vá para **Layout de tela**, escolha seu layout de tela, inicie o **Designer do layout da tela** e depois deixe o controle de **recomendações** onde necessário.</span><span class="sxs-lookup"><span data-stu-id="871ca-133">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>

4.  <span data-ttu-id="871ca-134">Vá para **Parâmetros de varejo**, selecione **Aprendizado de máquina**, selecione **Sim** em **Habilitar recomendações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="871ca-134">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5.  <span data-ttu-id="871ca-135">Para consultar recomendações no PDV, rode o trabalho de configuração global **1110**.</span><span class="sxs-lookup"><span data-stu-id="871ca-135">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="871ca-136">Para refletir as alterações feitas ao designer de layout de tela do PDV, rode o trabalho de configuração de canal **1070**.</span><span class="sxs-lookup"><span data-stu-id="871ca-136">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="871ca-137">Como funciona?</span><span class="sxs-lookup"><span data-stu-id="871ca-137">How does it work?</span></span>
<span data-ttu-id="871ca-138">Quando você atualiza a entidade **Loja de entidade**, as ações a seguir ocorrem.</span><span class="sxs-lookup"><span data-stu-id="871ca-138">When you refresh the **Entity store** entity, the following actions take place.</span></span>

-   <span data-ttu-id="871ca-139">Os dados no formato exigido pelos serviços cognitivos são extraídos do banco de dados operacional do Dynamics 365 for Retail e enviados para a loja de entidade.</span><span class="sxs-lookup"><span data-stu-id="871ca-139">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
-   <span data-ttu-id="871ca-140">Os dados são usados por Azure Data Factory (ADF) para limpar os dados usando scripts em conjunto como parte das atividades do ADF.</span><span class="sxs-lookup"><span data-stu-id="871ca-140">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="871ca-141">Os dados limpos são armazenados no armazenamento blob.</span><span class="sxs-lookup"><span data-stu-id="871ca-141">Cleansed data is stored in blob storage.</span></span>
-   <span data-ttu-id="871ca-142">Os dados do armazenamento de blob são usados pelo API dos serviços cognitivos para treinar um modelo de recomendação.</span><span class="sxs-lookup"><span data-stu-id="871ca-142">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="871ca-143">Quando você ativa **Habilitar recomendações** e executa os trabalhos de configuração, as ações a seguir ocorrem.</span><span class="sxs-lookup"><span data-stu-id="871ca-143">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

-   <span data-ttu-id="871ca-144">As credenciais de modelo e ID são coletados da API e armazenadas no banco de dados operacional do Dynamics 365 for Retail, no web.config para AOS, bem como no servidor de varejo.</span><span class="sxs-lookup"><span data-stu-id="871ca-144">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
-   <span data-ttu-id="871ca-145">As credenciais de modelo e ID tornam-se disponíveis ao CRT para que as chamadas de recomendações de produto do Cloud POS e MPOS no modo online podem ser liquidadas.</span><span class="sxs-lookup"><span data-stu-id="871ca-145">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>

> ## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="871ca-146">Solucionar problemas em que as Recomendações de produto já estejam habilitadas</span><span class="sxs-lookup"><span data-stu-id="871ca-146">Troubleshoot issues where you have Product recommendations already enabled</span></span> 
> - <span data-ttu-id="871ca-147">Navegue até **Parâmetros de varejo** > **Aprendizado de máquina** > **Desabilitar recomendações de produtos** e execute **Trabalho de configuração global [1110]**.</span><span class="sxs-lookup"><span data-stu-id="871ca-147">Navigate to **Retail Parameters** > **Machine learning** > **Disable product recommendations** and run **Global configuration job [1110]**.</span></span> <span data-ttu-id="871ca-148">Se não conseguir localizar a guia **Aprendizado de máquina**, entre em contato com o suporte do Dynamics.</span><span class="sxs-lookup"><span data-stu-id="871ca-148">If you are not able to locate **Machine learning** tab, please contact Dynamics Support.</span></span> 
> 
> - <span data-ttu-id="871ca-149">Se você adicionou o **Controle de recomendações** à sua tela de transação usando o **Designer do layout da tela**, remova-o também.</span><span class="sxs-lookup"><span data-stu-id="871ca-149">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span> 



<a name="additional-resources"></a><span data-ttu-id="871ca-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="871ca-150">Additional resources</span></span>
--------

[<span data-ttu-id="871ca-151">Adicionar um controle de recomendações à página de transação em um dispositivo do PDV</span><span class="sxs-lookup"><span data-stu-id="871ca-151">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)




