---
title: Gerenciar classificações e opiniões
description: Este tópico explica como gerenciar classificações e opiniões no construtor de site do Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3fc88bc5a5868dce7c0539bf3f0ddc5b751e7b75
ms.sourcegitcommit: 83ec80382bfeb693d5c5949b6f65296bd50eed12
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973997"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="828e1-103">Gerenciar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="828e1-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="828e1-104">Este tópico explica como gerenciar classificações e opiniões no construtor de site do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="828e1-104">This topic explains how to manage ratings and reviews in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="828e1-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="828e1-105">Overview</span></span>

<span data-ttu-id="828e1-106">O Dynamics 365 Commerce usa o Serviço Cognitivo do Microsoft Azure para moderar automaticamente o texto da opinião, redigindo palavras profanas.</span><span class="sxs-lookup"><span data-stu-id="828e1-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="828e1-107">Além disso, os moderadores podem usar o construtor de site do Dynamics 365 Commerce para implementar as seguintes tarefas manuais:</span><span class="sxs-lookup"><span data-stu-id="828e1-107">In addition, moderators can use Dynamics 365 Commerce site builder to implement the following manual tasks:</span></span>

- <span data-ttu-id="828e1-108">Moderar as opiniões, respondendo-as ou removendo-as.</span><span class="sxs-lookup"><span data-stu-id="828e1-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="828e1-109">Excluir opiniões de um cliente na solicitação do cliente.</span><span class="sxs-lookup"><span data-stu-id="828e1-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="828e1-110">Importar em massa dados de classificações e opiniões de todos os produtos para um modelo do Power BI , para que as tendências para classificações e opiniões possam ser analisadas.</span><span class="sxs-lookup"><span data-stu-id="828e1-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="828e1-111">Ler uma opinião</span><span class="sxs-lookup"><span data-stu-id="828e1-111">Read a review</span></span> 

<span data-ttu-id="828e1-112">Para ler uma opinião no construtor de site do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="828e1-112">To read to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="828e1-113">Vá para **Início \> Opiniões \> Moderação**.</span><span class="sxs-lookup"><span data-stu-id="828e1-113">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="828e1-114">Use o campo de pesquisa no canto superior direito da página para filtrar as opiniões mostradas por ID do produto, nome do produto ou texto da opinião.</span><span class="sxs-lookup"><span data-stu-id="828e1-114">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="828e1-115">Os filtros adicionais permitem delimitar as opiniões por período, classificação, canal, status de interesse (obtidas, respondidas ou reportadas).</span><span class="sxs-lookup"><span data-stu-id="828e1-115">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Home page de moderação](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="828e1-117">Responder a uma opinião</span><span class="sxs-lookup"><span data-stu-id="828e1-117">Respond to a review</span></span> 

<span data-ttu-id="828e1-118">Às vezes, os clientes que compraram um produto expressam sua satisfação ou insatisfação ou não sabem como usá-lo.</span><span class="sxs-lookup"><span data-stu-id="828e1-118">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="828e1-119">Como moderador, você pode publicar uma resposta a uma opinião.</span><span class="sxs-lookup"><span data-stu-id="828e1-119">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="828e1-120">Esta resposta aparece junto com a opinião no site.</span><span class="sxs-lookup"><span data-stu-id="828e1-120">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="828e1-121">Para responder uma opinião no construtor de site do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="828e1-121">To respond to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="828e1-122">Vá para **Início \> Opiniões \> Moderação**.</span><span class="sxs-lookup"><span data-stu-id="828e1-122">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="828e1-123">Encontre e selecione a opinião que requer uma resposta.</span><span class="sxs-lookup"><span data-stu-id="828e1-123">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="828e1-124">No painel de propriedades à direita, selecione **Adicionar uma resposta**.</span><span class="sxs-lookup"><span data-stu-id="828e1-124">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="828e1-125">Insira o texto de resposta e o nome que devem ser mostrado para o respondente.</span><span class="sxs-lookup"><span data-stu-id="828e1-125">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="828e1-126">O nome do respondente padrão é **Moderador**.</span><span class="sxs-lookup"><span data-stu-id="828e1-126">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="828e1-127">Quando terminar, selecione **Postar resposta**.</span><span class="sxs-lookup"><span data-stu-id="828e1-127">When you've finished, select **Post response**.</span></span>

![Respondendo uma opinião](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="828e1-129">Desativar uma opinião</span><span class="sxs-lookup"><span data-stu-id="828e1-129">Take down a review</span></span> 

<span data-ttu-id="828e1-130">Às vezes, há uma justificativa comercial para que os moderadores desativem as opiniões dos clientes.</span><span class="sxs-lookup"><span data-stu-id="828e1-130">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="828e1-131">Para desativar uma opinião no construtor de site do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="828e1-131">To take down a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="828e1-132">Vá para **Início \> Opiniões \> Moderação**.</span><span class="sxs-lookup"><span data-stu-id="828e1-132">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="828e1-133">Localize e selecione a opinião que deve ser desativada.</span><span class="sxs-lookup"><span data-stu-id="828e1-133">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="828e1-134">No painel de propriedades à direita, selecione o motivo da desativação em **Desativação da Opinião** e depois selecione **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="828e1-134">In the properties pane on the right, select a takedown reason under **Takedown Review**, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="828e1-135">Excluir opiniões de um cliente na solicitação do cliente</span><span class="sxs-lookup"><span data-stu-id="828e1-135">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="828e1-136">Às vezes, os clientes querem que seus dados de classificações e opiniões sejam excluídos permanentemente de um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="828e1-136">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="828e1-137">Um moderador que recebe uma solicitação de remoção de um cliente pode remover os dados do cliente usando o recurso de exclusão da opinião.</span><span class="sxs-lookup"><span data-stu-id="828e1-137">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="828e1-138">Para localizar e excluir os dados de um cliente, o moderador exige o endereço de email que o cliente usou para entrar e dar as opiniões.</span><span class="sxs-lookup"><span data-stu-id="828e1-138">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="828e1-139">Para localizar e excluir dados do cliente no construtor de site do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="828e1-139">To find and delete customer data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="828e1-140">Vá para **Início \> Opiniões \> Excluir**.</span><span class="sxs-lookup"><span data-stu-id="828e1-140">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="828e1-141">Na caixa **Procurar usuários por endereço de email** , insira o endereço de email do cliente e selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="828e1-141">In the **Search for users by email address** box, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="828e1-142">Se o cliente tiver alguma atividade de opinião (por exemplo, envios de opiniões, votos sobre a utilidade das opiniões de outro cliente ou comentários sobre a opinião de outro cliente), os resultados serão mostrados.</span><span class="sxs-lookup"><span data-stu-id="828e1-142">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="828e1-143">Para cada item, há um botão **Excluir** .</span><span class="sxs-lookup"><span data-stu-id="828e1-143">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="828e1-144">Para cada item a ser excluído, selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="828e1-144">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="828e1-145">Quando for solicitado a confirmação, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="828e1-145">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Excluindo dados do cliente](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="828e1-147">Pode levar até sete dias para que os dados sejam completamente removidos do sistema.</span><span class="sxs-lookup"><span data-stu-id="828e1-147">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="828e1-148">Os moderadores devem notificar aos clientes sobre esse atraso.</span><span class="sxs-lookup"><span data-stu-id="828e1-148">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="828e1-149">Se os clientes alteraram o nome nas configurações da conta, vários itens podem aparecer nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="828e1-149">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="828e1-150">Nesse caso, para excluir completamente os dados do cliente, o moderador deve selecionar **Excluir** para cada item.</span><span class="sxs-lookup"><span data-stu-id="828e1-150">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="828e1-151">Fazendo download de dados de classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="828e1-151">Download ratings and reviews data</span></span>

<span data-ttu-id="828e1-152">O construtor de site do Commerce permite que os moderadores importem dados de classificações e opiniões em massa, para que possam analisar tendências.</span><span class="sxs-lookup"><span data-stu-id="828e1-152">Commerce site builder lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="828e1-153">Um modelo do Power BI que inclui métricas básicas estará disponível.</span><span class="sxs-lookup"><span data-stu-id="828e1-153">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="828e1-154">Os moderadores podem usar esse modelo para conectar dados importados em massa e visualizar um painel.</span><span class="sxs-lookup"><span data-stu-id="828e1-154">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="828e1-155">Eles não precisam criar um painel personalizado.</span><span class="sxs-lookup"><span data-stu-id="828e1-155">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="828e1-156">Os moderadores também podem personalizar o modelo do Power BI para atender às suas necessidades específicas.</span><span class="sxs-lookup"><span data-stu-id="828e1-156">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="828e1-157">Para baixar dados de classificações e opiniões no construtor de site do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="828e1-157">To download ratings and reviews data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="828e1-158">Vá para **Início \> Opiniões \> Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="828e1-158">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="828e1-159">Selecione **Baixar dados de opiniões** para baixar dados em massa de classificações e opiniões no formato de valores separados por vírgulas (CSV).</span><span class="sxs-lookup"><span data-stu-id="828e1-159">Select **Download review data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="828e1-160">Visualizar tendência de classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="828e1-160">View ratings and reviews trends</span></span>

<span data-ttu-id="828e1-161">Os moderadores podem fazer download do modelo do Power BI, de forma que possam exibir as tendências em um painel.</span><span class="sxs-lookup"><span data-stu-id="828e1-161">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="828e1-162">Para exibir tendências de classificações e opiniões no construtor de site do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="828e1-162">To view ratings and reviews trends in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="828e1-163">Vá para **Início \> Opiniões \> Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="828e1-163">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="828e1-164">Selecione **Modelo do PowerBI** para baixar o modelo.</span><span class="sxs-lookup"><span data-stu-id="828e1-164">Select **PowerBI template** to download the template.</span></span>

    ![Baixe o modelo do Power BI](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="828e1-166">Abra o modelo baixado usando o aplicativo Power BI.</span><span class="sxs-lookup"><span data-stu-id="828e1-166">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="828e1-167">Feche a caixa de diálogo **Acessar o conteúdo da Web** que é exibida e feche a mensagem de erro "Atualizar" que é exibida.</span><span class="sxs-lookup"><span data-stu-id="828e1-167">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="828e1-168">Vá para **Início**, selecione **Editar consultas** e selecione **Configurações da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="828e1-168">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="828e1-169">Na caixa de diálogo **Configurações da fonte de dados**, selecione **Alterar Origem**.</span><span class="sxs-lookup"><span data-stu-id="828e1-169">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="828e1-170">No campo **URL** , insira o caminho de dados das opiniões baixado no procedimento anterior (por exemplo, **c:\\opiniões\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="828e1-170">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![Campo da URL na caixa de diálogo Valores Separados por Vírgulas](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="828e1-172">Selecione **OK** e, em seguida, selecione **Aplicar alterações**.</span><span class="sxs-lookup"><span data-stu-id="828e1-172">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="828e1-173">Levará um a dois minutos para aplicar suas alterações na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="828e1-173">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="828e1-174">Selecione **Planilha de tendências** para exibir as tendências de classificações e opiniões.</span><span class="sxs-lookup"><span data-stu-id="828e1-174">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Tendência de classificações e opiniões](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="828e1-176">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="828e1-176">Additional resources</span></span>

[<span data-ttu-id="828e1-177">Visão geral de classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="828e1-177">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="828e1-178">Aceitar usar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="828e1-178">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="828e1-179">Configurar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="828e1-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="828e1-180">Sincronizar classificações de produto no Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="828e1-180">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
