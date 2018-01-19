---
title: "Visão geral de recomendações de produtos personalizados"
description: "Este tópico contém informações sobre recomendações de produtos do Dynamics 365 for Retail que podem ser exibidas no dispositivo de ponto de venda (POS)."
author: ashishmsft
manager: AnnBe
ms.date: 11/14/2017
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
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: fde7face188bbfd3bfdf66fbff81969f75704302
ms.contentlocale: pt-br
ms.lasthandoff: 01/19/2018

---

# <a name="personalized-product-recommendations-overview"></a><span data-ttu-id="51b5a-103">Visão geral de recomendações de produtos personalizados</span><span class="sxs-lookup"><span data-stu-id="51b5a-103">Personalized product recommendations overview</span></span>

[!include[banner](includes/banner.md)]


> [!NOTE]
> <span data-ttu-id="51b5a-104">Esse recurso estará disponível somente em topologias de implantação de área restrita e produção (alta disponibilidade).</span><span class="sxs-lookup"><span data-stu-id="51b5a-104">This feature is currently available on sandbox and production (high-availability) deployment topologies only.</span></span> 

<span data-ttu-id="51b5a-105">No Dynamics 365 for Retail, as recomendações de produtos podem ser exibidas no dispositivo de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="51b5a-105">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="51b5a-106">As recomendações são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas.</span><span class="sxs-lookup"><span data-stu-id="51b5a-106">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="51b5a-107">Para fornecedores com grandes catálogos, recomendações ajudam o cliente com descoberta de produto.</span><span class="sxs-lookup"><span data-stu-id="51b5a-107">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="51b5a-108">Ao exibir produtos para determinado público de interesse e hábitos de compra, as recomendações de produto podem ajudar os varejistas com venda direta e cruzada, e pode aumentar a retenção de cliente.</span><span class="sxs-lookup"><span data-stu-id="51b5a-108">By showcasing products targeted to a customer’s interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="51b5a-109">No Dynamics 365 for Retail, as recomendações de produtos são suportadas por serviços cognitivos e aprendizado de máquina do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="51b5a-109">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>


<a name="scenarios"></a><span data-ttu-id="51b5a-110">Cenários</span><span class="sxs-lookup"><span data-stu-id="51b5a-110">Scenarios</span></span>
---------

<span data-ttu-id="51b5a-111">As recomendações de produto são habilitadas para os seguintes cenários de PDV.</span><span class="sxs-lookup"><span data-stu-id="51b5a-111">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="51b5a-112">Estão disponíveis no Cloud POS ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="51b5a-112">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1.  <span data-ttu-id="51b5a-113">Na página **Detalhes de produto**:</span><span class="sxs-lookup"><span data-stu-id="51b5a-113">On the **Product details** page:</span></span>

-   <span data-ttu-id="51b5a-114">Se um associado da loja visita uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o mecanismo de recomendação sugere itens adicionais que provavelmente podem ser comprados juntos.</span><span class="sxs-lookup"><span data-stu-id="51b5a-114">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
-   <span data-ttu-id="51b5a-115">Se o associado da loja adicionar um cliente à transação e depois visitar uma página de **Detalhes de produto**, o mecanismo de recomendação fornece recomendações personalizadas usando o histórico de transação do cliente.</span><span class="sxs-lookup"><span data-stu-id="51b5a-115">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

<span data-ttu-id="51b5a-116">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="51b5a-116">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2.  <span data-ttu-id="51b5a-117">Na página **Transação**:</span><span class="sxs-lookup"><span data-stu-id="51b5a-117">On the **Transaction** page:</span></span>

-   <span data-ttu-id="51b5a-118">O mecanismo de recomendação sugere itens com base na lista inteira de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="51b5a-118">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
-   <span data-ttu-id="51b5a-119">Se o associado da loja adicionar um cliente à transação, o mecanismo de recomendação fornece recomendações pessoais usando o histórico de transação do cliente e a lista de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="51b5a-119">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer’s transaction history and the list of items in the basket.</span></span>

> [!NOTE]
> <span data-ttu-id="51b5a-120">Para exibir as recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="51b5a-120">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="51b5a-121">O controle das **Recomendações** deve ser colocado na página de **Transação**.</span><span class="sxs-lookup"><span data-stu-id="51b5a-121">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span> <span data-ttu-id="51b5a-122">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="51b5a-122">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3.  <span data-ttu-id="51b5a-123">Na página **Detalhes de cliente**:</span><span class="sxs-lookup"><span data-stu-id="51b5a-123">On the **Customer details** page:</span></span>
    -   <span data-ttu-id="51b5a-124">O mecanismo de recomendação sugere itens com base na ID de usuário e itens na lista de desejo do cliente.</span><span class="sxs-lookup"><span data-stu-id="51b5a-124">The recommendation engine suggests items based on the user ID and items in the customer’s wish list.</span></span>

<span data-ttu-id="51b5a-125">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="51b5a-125">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="51b5a-126">Configurar o Dynamics 365 for Retail para habilitar recomendações de PDV</span><span class="sxs-lookup"><span data-stu-id="51b5a-126">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>
<span data-ttu-id="51b5a-127">Para configurar recomendações de produto, você precisa fazer o seguinte.</span><span class="sxs-lookup"><span data-stu-id="51b5a-127">To set up product recommendations, you need to do the following.</span></span>

1.  <span data-ttu-id="51b5a-128">Verifique se você escolheu correto a **Entidade legal** correta.</span><span class="sxs-lookup"><span data-stu-id="51b5a-128">Make sure that you have selected the correct **Legal entity**.</span></span>
2.  <span data-ttu-id="51b5a-129">Navegue até **Repositório de entidades**, selecione **Vendas de varejo** e clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="51b5a-129">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.</span></span> <span data-ttu-id="51b5a-130">Isso usará os dados de demonstração (ou seus dados) do banco de dados operacional e irá movê-los para o repositório de entidades.</span><span class="sxs-lookup"><span data-stu-id="51b5a-130">This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3.  <span data-ttu-id="51b5a-131">Opcional: Para exibir recomendações na tela de transação, vá para **Layout de tela**, escolha seu layout de tela, inicie o **Designer do layout da tela** e depois deixe o controle de **recomendações** onde necessário.</span><span class="sxs-lookup"><span data-stu-id="51b5a-131">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>

4.  <span data-ttu-id="51b5a-132">Vá para **Parâmetros de varejo**, selecione **Aprendizado de máquina**, selecione **Sim** em **Habilitar recomendações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="51b5a-132">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5.  <span data-ttu-id="51b5a-133">Para consultar recomendações no PDV, rode o trabalho de configuração global **1110**.</span><span class="sxs-lookup"><span data-stu-id="51b5a-133">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="51b5a-134">Para refletir as alterações feitas ao designer de layout de tela do PDV, rode o trabalho de configuração de canal **1070**.</span><span class="sxs-lookup"><span data-stu-id="51b5a-134">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="51b5a-135">[]()Como funciona?</span><span class="sxs-lookup"><span data-stu-id="51b5a-135">[]()How does it work?</span></span>
<span data-ttu-id="51b5a-136">Quando você atualiza a entidade **Loja de entidade**, as ações a seguir ocorrem.</span><span class="sxs-lookup"><span data-stu-id="51b5a-136">When you refresh the **Entity store** entity, the following actions take place.</span></span>

-   <span data-ttu-id="51b5a-137">Os dados no formato exigido pelos serviços cognitivos são extraídos do banco de dados operacional do Dynamics 365 for Retail e enviados para a loja de entidade.</span><span class="sxs-lookup"><span data-stu-id="51b5a-137">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
-   <span data-ttu-id="51b5a-138">Os dados são usados por Azure Data Factory (ADF) para limpar os dados usando scripts em conjunto como parte das atividades do ADF.</span><span class="sxs-lookup"><span data-stu-id="51b5a-138">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="51b5a-139">Os dados limpos são armazenados no armazenamento blob.</span><span class="sxs-lookup"><span data-stu-id="51b5a-139">Cleansed data is stored in blob storage.</span></span>
-   <span data-ttu-id="51b5a-140">Os dados do armazenamento de blob são usados pelo API dos serviços cognitivos para treinar um modelo de recomendação.</span><span class="sxs-lookup"><span data-stu-id="51b5a-140">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="51b5a-141">Quando você ativa **Habilitar recomendações** e executa os trabalhos de configuração, as ações a seguir ocorrem.</span><span class="sxs-lookup"><span data-stu-id="51b5a-141">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

-   <span data-ttu-id="51b5a-142">As credenciais de modelo e ID são coletados da API e armazenadas no banco de dados operacional do Dynamics 365 for Retail, no web.config para AOS, bem como no servidor de varejo.</span><span class="sxs-lookup"><span data-stu-id="51b5a-142">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
-   <span data-ttu-id="51b5a-143">As credenciais de modelo e ID tornam-se disponíveis ao CRT para que as chamadas de recomendações de produto do Cloud POS e MPOS no modo online podem ser liquidadas.</span><span class="sxs-lookup"><span data-stu-id="51b5a-143">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>


<a name="see-also"></a><span data-ttu-id="51b5a-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="51b5a-144">See also</span></span>
--------

[<span data-ttu-id="51b5a-145">Adicionar um controle de recomendações à página de transação em um dispositivo do PDV</span><span class="sxs-lookup"><span data-stu-id="51b5a-145">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)




