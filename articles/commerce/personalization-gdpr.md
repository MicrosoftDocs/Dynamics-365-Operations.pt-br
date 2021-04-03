---
title: Cancelar recomendações personalizadas
description: Este tópico explica como você pode permitir que os clientes recusem receber recomendações personalizadas no Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: e65fc54f87664caec95b2bc2c579d0820ae08c0f
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477675"
---
# <a name="opt-out-of-personalized-recommendations"></a><span data-ttu-id="731a0-103">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="731a0-103">Opt out of personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="731a0-104">Este tópico explica como você pode permitir que os clientes recusem receber recomendações personalizadas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="731a0-104">This topic explains how you can let customers opt out of receiving personalized recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="731a0-105">Durante a criação da conta, novos clientes são configurados automaticamente para receber recomendações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="731a0-105">During account creation, new customers are automatically set up to receive personalized recommendations.</span></span> <span data-ttu-id="731a0-106">No entanto, o Dynamics 365 Commerce fornece várias maneiras para os varejistas permitirem que os usuários cancelem o recebimento dessas recomendações e restrinjam o processamento de seus dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="731a0-106">However, Dynamics 365 Commerce provides various ways for retailers to let users opt out of receiving these recommendations and restrict the processing of their personal data.</span></span> <span data-ttu-id="731a0-107">Os usuários autenticados que optarem por receber recomendações personalizadas irão parar imediatamente de ver as listas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="731a0-107">Authenticated users who opt out of receiving personalized recommendations will immediately stop seeing personalized lists.</span></span> <span data-ttu-id="731a0-108">Além disso, todos os dados pessoais coletados para personalização serão removidos dos modelos de recomendações personalizados.</span><span class="sxs-lookup"><span data-stu-id="731a0-108">Additionally, all personal data that is collected for personalization will be removed from personalized recommendations models.</span></span>

<span data-ttu-id="731a0-109">Para obter mais informações sobre recomendações personalizadas de produtos, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="731a0-109">For more information about personalized product recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a><span data-ttu-id="731a0-110">Maneiras de os varejistas implementarem uma experiência de recusa</span><span class="sxs-lookup"><span data-stu-id="731a0-110">Ways for retailers to implement an opt-out experience</span></span>

<span data-ttu-id="731a0-111">Os varejistas podem implementar uma experiência de recusa de três maneiras.</span><span class="sxs-lookup"><span data-stu-id="731a0-111">Retailers have three ways to implement an opt-out experience.</span></span>

### <a name="opting-out-on-behalf-of-users"></a><span data-ttu-id="731a0-112">Recusar em nome de usuários</span><span class="sxs-lookup"><span data-stu-id="731a0-112">Opting out on behalf of users</span></span>

<span data-ttu-id="731a0-113">No gerenciamento de contas do back office do Commerce, os varejistas podem recusar em nome de usuários.</span><span class="sxs-lookup"><span data-stu-id="731a0-113">In Account management in Commerce back office, retailers can opt out on behalf of users.</span></span>

1. <span data-ttu-id="731a0-114">Na home page de back-office, procure **todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="731a0-114">From the back-office home page, search for **all customers**.</span></span>
1. <span data-ttu-id="731a0-115">Procure e selecione um cliente e a guia rápida **Retail**.</span><span class="sxs-lookup"><span data-stu-id="731a0-115">Search for and select a customer, and then select the **Retail** FastTab.</span></span>

    ![Guia rápida Retail](./media/Disablepersonalizationpart1.png)

1. <span data-ttu-id="731a0-117">Em **Privacidade**, defina a opção **Desabilitar personalização** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="731a0-117">Under **Privacy**, set the **Disable personalization** option to **Yes**.</span></span>

    ![Configurações de privacidade](./media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="731a0-119">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="731a0-119">Select **Save**, and close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="731a0-120">Experiência de recusa baseada em módulo</span><span class="sxs-lookup"><span data-stu-id="731a0-120">Module-based opt-out experience</span></span>

<span data-ttu-id="731a0-121">Os varejistas podem permitir que os usuários autenticados cancelem as recomendações personalizadas sozinhos.</span><span class="sxs-lookup"><span data-stu-id="731a0-121">Retailers can let authenticated users opt out of personalized recommendations by themselves.</span></span> <span data-ttu-id="731a0-122">Para fornecer essa experiência de recusa, adicione o módulo de recusa de usuário às páginas de perfil de conta de cliente.</span><span class="sxs-lookup"><span data-stu-id="731a0-122">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="731a0-123">Extensões personalizadas</span><span class="sxs-lookup"><span data-stu-id="731a0-123">Custom extensions</span></span>

<span data-ttu-id="731a0-124">Os varejistas podem criar suas próprias extensões para gerenciar a experiência de recusa dos usuários.</span><span class="sxs-lookup"><span data-stu-id="731a0-124">Retailers can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="731a0-125">Para obter mais informações, consulte [Chamar APIs do Retail Server](e-commerce-extensibility/call-retail-server-apis.md) e a [extensibilidade de canal online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="731a0-125">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a><span data-ttu-id="731a0-126">Obtenha uma cópia digital de dados de recomendações personalizados em nome de um usuário autenticado</span><span class="sxs-lookup"><span data-stu-id="731a0-126">Obtain a digital copy of personalized recommendations data on behalf of an authenticated user</span></span>

<span data-ttu-id="731a0-127">Talvez os clientes desejem obter uma cópia digital de dados pessoais e também uma exibição exportada dos resultados de recomendações.</span><span class="sxs-lookup"><span data-stu-id="731a0-127">Customers might want to obtain a digital copy of their personal data and also see an exported view of their recommendations results.</span></span> <span data-ttu-id="731a0-128">Se um cliente solicitar essas informações, o varejista deverá criar uma extensão personalizada que chame a API (interface de programação de aplicativo) do servidor de varejo e consultas para obter os resultados da lista **Seleções para você**, com base na ID de cliente do cliente.</span><span class="sxs-lookup"><span data-stu-id="731a0-128">If a customer requests this information, the retailer must create a customized extension that calls the Retail Server application programming interface (API) and queries for the full results from the **Picks for you** list, based on the customer's customer ID.</span></span> <span data-ttu-id="731a0-129">Os resultados podem ser exportados no formato de valores separados por vírgulas (CSV) e compartilhados com o cliente.</span><span class="sxs-lookup"><span data-stu-id="731a0-129">The results can then be exported in comma-separated values (CSV) format and shared with the customer.</span></span>

<span data-ttu-id="731a0-130">O exemplo a seguir mostra como um varejista pode realizar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="731a0-130">The following example shows how a retailer can accomplish this task.</span></span>

1. <span data-ttu-id="731a0-131">O varejista cria uma extensão personalizada para receber dados de recomendações pessoais em nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="731a0-131">The retailer creates a custom extension to pull personal recommendations data on behalf of the user.</span></span> <span data-ttu-id="731a0-132">Para obter informações sobre como criar módulos, clonar módulos existentes, chamar APIs do Retail Server e chamar ações de dados, consulte [Extensibilidade do canal online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="731a0-132">For information about how to create modules, clone existing modules, call Retail Server APIs, and call data actions, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
2. <span data-ttu-id="731a0-133">A extensão personalizada faz uma chamada para a ação de dados principais **get-recommendations** e passa as informações necessárias para ela, com base nos requisitos da lista.</span><span class="sxs-lookup"><span data-stu-id="731a0-133">The custom extension makes a call to the **get-recommendations** core data action and passes the required information to it, based on the requirements of the list.</span></span> <span data-ttu-id="731a0-134">No caso da lista **Seleções para Você**, a extensão deve passar o nome da lista e a ID do cliente corretos para a ação de dados.</span><span class="sxs-lookup"><span data-stu-id="731a0-134">In the case of the **Picks for you** list, the extension must pass the correct list name and customer ID to the data action.</span></span>

    <span data-ttu-id="731a0-135">Uma forma de criar a extensão personalizada é clonar o módulo de coleção de produtos existente usado para devolver resultados de recomendações.</span><span class="sxs-lookup"><span data-stu-id="731a0-135">One way to create the custom extension is to clone the existing product collection module that is used to return recommendations results.</span></span> <span data-ttu-id="731a0-136">Ao clonar este módulo existente, um varejista pode modificar o código existente e adicionar um novo botão que exporte os resultados de recomendações para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="731a0-136">By cloning this existing module, a retailer can modify the existing code and add a new button that exports the recommendations results to a CSV file.</span></span> <span data-ttu-id="731a0-137">Para obter mais informações, consulte [Clonar um módulo de biblioteca de módulo](e-commerce-extensibility/clone-starter-module.md) e [módulos de coleção de produtos](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="731a0-137">For more information, see [Clone a module library module](e-commerce-extensibility/clone-starter-module.md) and [Product collection modules](product-collection-module-overview.md).</span></span>

    <span data-ttu-id="731a0-138">Para obter uma exibição completa da biblioteca da API do Retail Server, consulte [Cliente do Retail Server e APIs de consumo](dev-itpro/retail-server-customer-consumer-api.md).</span><span class="sxs-lookup"><span data-stu-id="731a0-138">For a full view of the Retail Server API library, see [Retail Server Customer and Consumer APIs](dev-itpro/retail-server-customer-consumer-api.md).</span></span>

3. <span data-ttu-id="731a0-139">Depois que a extensão personalizada é criada, o varejista pode exportar um arquivo CSV de todos os resultados de recomendações, com base na ID exclusiva do cliente do usuário autenticado.</span><span class="sxs-lookup"><span data-stu-id="731a0-139">After the custom extension is created, the retailer can export a CSV file of all recommendations results, based on the unique customer ID of the authenticated user.</span></span>
4. <span data-ttu-id="731a0-140">O varejista pode compartilhar o arquivo CSV exportado que contém a lista completa personalizada de produtos recomendados com o usuário autenticado.</span><span class="sxs-lookup"><span data-stu-id="731a0-140">The retailer can share the exported CSV file that contains the full personalized list of recommended products with the authenticated user.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="731a0-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="731a0-141">Additional resources</span></span>

[<span data-ttu-id="731a0-142">Visão geral das recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="731a0-142">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="731a0-143">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="731a0-143">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="731a0-144">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="731a0-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="731a0-145">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="731a0-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="731a0-146">Habilitar recomendações de "comprar looks semelhantes"</span><span class="sxs-lookup"><span data-stu-id="731a0-146">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="731a0-147">Adicionar recomendações dos produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="731a0-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="731a0-148">Adicionar recomendações à tela de transações</span><span class="sxs-lookup"><span data-stu-id="731a0-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="731a0-149">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="731a0-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="731a0-150">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="731a0-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="731a0-151">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="731a0-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="731a0-152">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="731a0-152">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
