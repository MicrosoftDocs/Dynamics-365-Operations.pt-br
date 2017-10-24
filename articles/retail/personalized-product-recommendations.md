---
title: "Visão geral de recomendações de produtos personalizados"
description: "No Dynamics 365 for Retail, as recomendações de produtos podem ser exibidas no dispositivo de ponto de venda (PDV). As recomendações são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas. Para fornecedores com grandes catálogos, recomendações ajudam o cliente com descoberta de produto. Ao exibir produtos para determinado público de interesse e hábitos de compra, as recomendações de produto podem ajudar os varejistas com venda direta e cruzada, e pode aumentar a retenção de cliente. No Dynamics 365 for Retail, as recomendações de produtos são suportadas por serviços cognitivos e aprendizado de máquina do Microsoft Azure."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d727718442f94a2a78a3864741e93439d7c36473
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="personalized-product-recommendations-overview"></a><span data-ttu-id="7d2b1-107">Visão geral de recomendações de produtos personalizados</span><span class="sxs-lookup"><span data-stu-id="7d2b1-107">Personalized product recommendations overview</span></span>

[!include[banner](includes/banner.md)]


> [!NOTE]
> <span data-ttu-id="7d2b1-108">Esse recurso estará disponível somente em topologias de implantação de área restrita e produção (alta disponibilidade).</span><span class="sxs-lookup"><span data-stu-id="7d2b1-108">This feature is currently available on sandbox and production (high-availability) deployment topologies only.</span></span> 

<span data-ttu-id="7d2b1-109">No Dynamics 365 for Retail, as recomendações de produtos podem ser exibidas no dispositivo de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="7d2b1-109">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="7d2b1-110">As recomendações são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-110">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="7d2b1-111">Para fornecedores com grandes catálogos, recomendações ajudam o cliente com descoberta de produto.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-111">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="7d2b1-112">Ao exibir produtos para determinado público de interesse e hábitos de compra, as recomendações de produto podem ajudar os varejistas com venda direta e cruzada, e pode aumentar a retenção de cliente.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-112">By showcasing products targeted to a customer’s interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="7d2b1-113">No Dynamics 365 for Retail, as recomendações de produtos são suportadas por serviços cognitivos e aprendizado de máquina do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-113">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>


<a name="scenarios"></a><span data-ttu-id="7d2b1-114">Cenários</span><span class="sxs-lookup"><span data-stu-id="7d2b1-114">Scenarios</span></span>
---------

<span data-ttu-id="7d2b1-115">As recomendações de produto são habilitadas para os seguintes cenários de PDV.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-115">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="7d2b1-116">Estão disponíveis no Cloud POS ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="7d2b1-116">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1.  <span data-ttu-id="7d2b1-117">Na página **Detalhes de produto**:</span><span class="sxs-lookup"><span data-stu-id="7d2b1-117">On the **Product details** page:</span></span>

-   <span data-ttu-id="7d2b1-118">Se um associado da loja visita uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o mecanismo de recomendação sugere itens adicionais que provavelmente podem ser comprados juntos.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-118">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
-   <span data-ttu-id="7d2b1-119">Se o associado da loja adicionar um cliente à transação e depois visitar uma página de **Detalhes de produto**, o mecanismo de recomendação fornece recomendações personalizadas usando o histórico de transação do cliente.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-119">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

<span data-ttu-id="7d2b1-120">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="7d2b1-120">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2.  <span data-ttu-id="7d2b1-121">Na página **Transação**:</span><span class="sxs-lookup"><span data-stu-id="7d2b1-121">On the **Transaction** page:</span></span>

-   <span data-ttu-id="7d2b1-122">O mecanismo de recomendação sugere itens com base na lista inteira de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-122">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
-   <span data-ttu-id="7d2b1-123">Se o associado da loja adicionar um cliente à transação, o mecanismo de recomendação fornece recomendações pessoais usando o histórico de transação do cliente e a lista de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-123">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer’s transaction history and the list of items in the basket.</span></span>

> [!NOTE]
> <span data-ttu-id="7d2b1-124">Para exibir as recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-124">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="7d2b1-125">O controle das **Recomendações** deve ser colocado na página de **Transação**.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-125">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span> <span data-ttu-id="7d2b1-126">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="7d2b1-126">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3.  <span data-ttu-id="7d2b1-127">Na página **Detalhes de cliente**:</span><span class="sxs-lookup"><span data-stu-id="7d2b1-127">On the **Customer details** page:</span></span>
    -   <span data-ttu-id="7d2b1-128">O mecanismo de recomendação sugere itens com base na ID de usuário e itens na lista de desejo do cliente.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-128">The recommendation engine suggests items based on the user ID and items in the customer’s wish list.</span></span>

<span data-ttu-id="7d2b1-129">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="7d2b1-129">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="7d2b1-130">Configurar o Dynamics 365 for Retail para habilitar recomendações de PDV</span><span class="sxs-lookup"><span data-stu-id="7d2b1-130">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>
<span data-ttu-id="7d2b1-131">Para configurar recomendações de produto, você precisa fazer o seguinte.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-131">To set up product recommendations, you need to do the following.</span></span>

1.  <span data-ttu-id="7d2b1-132">Verifique se você escolheu correto a **Entidade legal** correta.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-132">Make sure that you have selected the correct **Legal entity**.</span></span>
2.  <span data-ttu-id="7d2b1-133">Navegue até o **Repositório de entidades**, selecione **Vendas no varejo** e em **Atualizar**. Isso usará os dados de demonstração (ou seus dados) de seu banco de dados operacional e os moverá para o repositório de entidades.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-133">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3.  <span data-ttu-id="7d2b1-134">Opcional: Para exibir recomendações na tela de transação, vá para **Layout de tela**, escolha seu layout de tela, inicie o **Designer do layout da tela** e depois deixe o controle de **recomendações** onde necessário.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-134">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**,and then drop the **recommendations** control where needed.</span></span>
4.  <span data-ttu-id="7d2b1-135">Vá para **Parâmetros de varejo**, selecione **Aprendizado de máquina**, selecione **Sim** em **Habilitar recomendações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-135">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5.  <span data-ttu-id="7d2b1-136">Para consultar recomendações no PDV, rode o trabalho de configuração global **1110**.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-136">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="7d2b1-137">Para refletir as alterações feitas ao designer de layout de tela do PDV, rode o trabalho de configuração de canal **1070**.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-137">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="7d2b1-138">[]()Como funciona?</span><span class="sxs-lookup"><span data-stu-id="7d2b1-138">[]()How does it work?</span></span>
<span data-ttu-id="7d2b1-139">Quando você atualiza a entidade **Loja de entidade**, as ações a seguir ocorrem.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-139">When you refresh the **Entity store** entity, the following actions take place.</span></span>

-   <span data-ttu-id="7d2b1-140">Os dados no formato exigido pelos serviços cognitivos são extraídos do banco de dados operacional do Dynamics 365 for Retail e enviados para a loja de entidade.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-140">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
-   <span data-ttu-id="7d2b1-141">Os dados são usados por Azure Data Factory (ADF) para limpar os dados usando scripts em conjunto como parte das atividades do ADF.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-141">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="7d2b1-142">Os dados limpos são armazenados no armazenamento blob.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-142">Cleansed data is stored in blob storage.</span></span>
-   <span data-ttu-id="7d2b1-143">Os dados do armazenamento de blob são usados pelo API dos serviços cognitivos para treinar um modelo de recomendação.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-143">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="7d2b1-144">Quando você ativa **Habilitar recomendações** e executa os trabalhos de configuração, as ações a seguir ocorrem.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-144">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

-   <span data-ttu-id="7d2b1-145">As credenciais de modelo e ID são coletados da API e armazenadas no banco de dados operacional do Dynamics 365 for Retail, no web.config para AOS, bem como no servidor de varejo.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-145">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
-   <span data-ttu-id="7d2b1-146">As credenciais de modelo e ID tornam-se disponíveis ao CRT para que as chamadas de recomendações de produto do Cloud POS e MPOS no modo online podem ser liquidadas.</span><span class="sxs-lookup"><span data-stu-id="7d2b1-146">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>


<a name="see-also"></a><span data-ttu-id="7d2b1-147">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7d2b1-147">See also</span></span>
--------

[<span data-ttu-id="7d2b1-148">Adicionar um controle de recomendações à página de transação em um dispositivo do PDV</span><span class="sxs-lookup"><span data-stu-id="7d2b1-148">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)




