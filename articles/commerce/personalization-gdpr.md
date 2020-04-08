---
title: Cancelar recomendações personalizadas
description: Este tópico explica como você pode permitir que os clientes optem por receber recomendações personalizadas no Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
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
ms.openlocfilehash: 1e88980ef6ad585826762c8be35304aecbcc02ab
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154286"
---
# <a name="opt-out-of-personalized-recommendations"></a><span data-ttu-id="88b0a-103">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="88b0a-103">Opt out of personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="88b0a-104">Este tópico explica como você pode permitir que os clientes optem por receber recomendações personalizadas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="88b0a-104">This topic explains how you can let customers opt out of receiving personalized recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="88b0a-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="88b0a-105">Overview</span></span>

<span data-ttu-id="88b0a-106">Durante a criação da conta, novos clientes são configurados automaticamente para receber recomendações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="88b0a-106">During account creation, new customers are automatically set up to receive personalized recommendations.</span></span> <span data-ttu-id="88b0a-107">No entanto, o Dynamics 365 Commerce fornece várias maneiras para os varejistas permitirem que os usuários cancelem o recebimento dessas recomendações e restrinjam o processamento de seus dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="88b0a-107">However, Dynamics 365 Commerce provides various ways for retailers to let users opt out of receiving these recommendations and restrict the processing of their personal data.</span></span> <span data-ttu-id="88b0a-108">Os usuários autenticados que optarem por receber recomendações personalizadas irão parar imediatamente de ver as listas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="88b0a-108">Authenticated users who opt out of receiving personalized recommendations will immediately stop seeing personalized lists.</span></span> <span data-ttu-id="88b0a-109">Além disso, todos os dados pessoais coletados para personalização serão removidos dos modelos de recomendações personalizados.</span><span class="sxs-lookup"><span data-stu-id="88b0a-109">Additionally, all personal data that is collected for personalization will be removed from personalized recommendations models.</span></span>

<span data-ttu-id="88b0a-110">Para obter mais informações sobre recomendações personalizadas de produtos, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="88b0a-110">For more information about personalized product recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a><span data-ttu-id="88b0a-111">Maneiras de os varejistas implementarem uma experiência de recusa</span><span class="sxs-lookup"><span data-stu-id="88b0a-111">Ways for retailers to implement an opt-out experience</span></span>

<span data-ttu-id="88b0a-112">Os varejistas podem implementar uma experiência de recusa de três maneiras.</span><span class="sxs-lookup"><span data-stu-id="88b0a-112">Retailers have three ways to implement an opt-out experience.</span></span>

### <a name="opting-out-on-behalf-of-users"></a><span data-ttu-id="88b0a-113">Recusar em nome de usuários</span><span class="sxs-lookup"><span data-stu-id="88b0a-113">Opting out on behalf of users</span></span>

<span data-ttu-id="88b0a-114">No gerenciamento de contas do back office do Commerce, os varejistas podem recusar em nome de usuários.</span><span class="sxs-lookup"><span data-stu-id="88b0a-114">In Account management in Commerce back office, retailers can opt out on behalf of users.</span></span>

1. <span data-ttu-id="88b0a-115">Na home page de back-office, procure **todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="88b0a-115">From the back-office home page, search for **all customers**.</span></span>
1. <span data-ttu-id="88b0a-116">Procure e selecione um cliente e a guia rápida **Retail**.</span><span class="sxs-lookup"><span data-stu-id="88b0a-116">Search for and select a customer, and then select the **Retail** FastTab.</span></span>

    ![Guia rápida Retail](./media/Disablepersonalizationpart1.png)

1. <span data-ttu-id="88b0a-118">Em **Privacidade**, defina a opção **Desabilitar personalização** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="88b0a-118">Under **Privacy**, set the **Disable personalization** option to **Yes**.</span></span>

    ![Configurações de privacidade](./media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="88b0a-120">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="88b0a-120">Select **Save**, and close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="88b0a-121">Experiência de recusa baseada em módulo</span><span class="sxs-lookup"><span data-stu-id="88b0a-121">Module-based opt-out experience</span></span>

<span data-ttu-id="88b0a-122">Os varejistas podem permitir que os usuários autenticados cancelem as recomendações personalizadas sozinhos.</span><span class="sxs-lookup"><span data-stu-id="88b0a-122">Retailers can let authenticated users opt out of personalized recommendations by themselves.</span></span> <span data-ttu-id="88b0a-123">Para fornecer essa experiência de recusa, adicione o módulo de recusa de usuário às páginas de perfil de conta de cliente.</span><span class="sxs-lookup"><span data-stu-id="88b0a-123">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="88b0a-124">Extensões personalizadas</span><span class="sxs-lookup"><span data-stu-id="88b0a-124">Custom extensions</span></span>

<span data-ttu-id="88b0a-125">Os varejistas podem criar suas próprias extensões para gerenciar a experiência de recusa dos usuários.</span><span class="sxs-lookup"><span data-stu-id="88b0a-125">Retailers can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="88b0a-126">Para obter mais informações, consulte [Chamar APIs do Retail Server](e-commerce-extensibility/call-retail-server-apis.md) e a [extensibilidade de canal online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="88b0a-126">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a><span data-ttu-id="88b0a-127">Obtenha uma cópia digital de dados de recomendações personalizados em nome de um usuário autenticado</span><span class="sxs-lookup"><span data-stu-id="88b0a-127">Obtain a digital copy of personalized recommendations data on behalf of an authenticated user</span></span>

<span data-ttu-id="88b0a-128">Talvez os clientes desejem obter uma cópia digital de dados pessoais e também uma exibição exportada dos resultados de recomendações.</span><span class="sxs-lookup"><span data-stu-id="88b0a-128">Customers might want to obtain a digital copy of their personal data and also see an exported view of their recommendations results.</span></span> <span data-ttu-id="88b0a-129">Se um cliente solicitar essas informações, o varejista deverá criar uma extensão personalizada que chame a API (interface de programação de aplicativo) do servidor de varejo e consultas para obter os resultados da lista **Seleções para você**, com base na ID de cliente do cliente.</span><span class="sxs-lookup"><span data-stu-id="88b0a-129">If a customer requests this information, the retailer must create a customized extension that calls the Retail Server application programming interface (API) and queries for the full results from the **Picks for you** list, based on the customer's customer ID.</span></span> <span data-ttu-id="88b0a-130">Os resultados podem ser exportados no formato de valores separados por vírgulas (CSV) e compartilhados com o cliente.</span><span class="sxs-lookup"><span data-stu-id="88b0a-130">The results can then be exported in comma-separated values (CSV) format and shared with the customer.</span></span>

<span data-ttu-id="88b0a-131">O exemplo a seguir mostra como um varejista pode realizar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="88b0a-131">The following example shows how a retailer can accomplish this task.</span></span>

1. <span data-ttu-id="88b0a-132">O varejista cria uma extensão personalizada para receber dados de recomendações pessoais em nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="88b0a-132">The retailer creates a custom extension to pull personal recommendations data on behalf of the user.</span></span> <span data-ttu-id="88b0a-133">Para obter informações sobre como criar módulos, clonar módulos existentes, chamar APIs do Retail Server e chamar ações de dados, consulte [Extensibilidade do canal online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="88b0a-133">For information about how to create modules, clone existing modules, call Retail Server APIs, and call data actions, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
2. <span data-ttu-id="88b0a-134">A extensão personalizada faz uma chamada para a ação de dados principais **get-recommendations** e passa as informações necessárias para ela, com base nos requisitos da lista.</span><span class="sxs-lookup"><span data-stu-id="88b0a-134">The custom extension makes a call to the **get-recommendations** core data action and passes the required information to it, based on the requirements of the list.</span></span> <span data-ttu-id="88b0a-135">No caso da lista **Seleções para Você**, a extensão deve passar o nome da lista e a ID do cliente corretos para a ação de dados.</span><span class="sxs-lookup"><span data-stu-id="88b0a-135">In the case of the **Picks for you** list, the extension must pass the correct list name and customer ID to the data action.</span></span>

    <span data-ttu-id="88b0a-136">Uma forma de criar a extensão personalizada é clonar o módulo de coleção de produtos existente usado para devolver resultados de recomendações.</span><span class="sxs-lookup"><span data-stu-id="88b0a-136">One way to create the custom extension is to clone the existing product collection module that is used to return recommendations results.</span></span> <span data-ttu-id="88b0a-137">Ao clonar este módulo existente, um varejista pode modificar o código existente e adicionar um novo botão que exporte os resultados de recomendações para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="88b0a-137">By cloning this existing module, a retailer can modify the existing code and add a new button that exports the recommendations results to a CSV file.</span></span> <span data-ttu-id="88b0a-138">Para obter mais informações, consulte [Clonar um módulo de kit de início](e-commerce-extensibility/clone-starter-module.md) e [módulos de coleção de produtos](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="88b0a-138">For more information, see [Clone a starter kit module](e-commerce-extensibility/clone-starter-module.md) and [Product collection modules](product-collection-module-overview.md).</span></span>

    <span data-ttu-id="88b0a-139">Para obter uma exibição completa da biblioteca da API do Retail Server, consulte [Cliente do Retail Server e APIs de consumo](dev-itpro/retail-server-customer-consumer-api.md).</span><span class="sxs-lookup"><span data-stu-id="88b0a-139">For a full view of the Retail Server API library, see [Retail Server Customer and Consumer APIs](dev-itpro/retail-server-customer-consumer-api.md).</span></span>

3. <span data-ttu-id="88b0a-140">Depois que a extensão personalizada é criada, o varejista pode exportar um arquivo CSV de todos os resultados de recomendações, com base na ID exclusiva do cliente do usuário autenticado.</span><span class="sxs-lookup"><span data-stu-id="88b0a-140">After the custom extension is created, the retailer can export a CSV file of all recommendations results, based on the unique customer ID of the authenticated user.</span></span>
4. <span data-ttu-id="88b0a-141">O varejista pode compartilhar o arquivo CSV exportado que contém a lista completa personalizada de produtos recomendados com o usuário autenticado.</span><span class="sxs-lookup"><span data-stu-id="88b0a-141">The retailer can share the exported CSV file that contains the full personalized list of recommended products with the authenticated user.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88b0a-142">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="88b0a-142">Additional resources</span></span>

[<span data-ttu-id="88b0a-143">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="88b0a-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="88b0a-144">Habilitar ADLS em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="88b0a-144">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="88b0a-145">Habilitar recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="88b0a-145">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="88b0a-146">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="88b0a-146">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="88b0a-147">Adicionar recomendações dos produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="88b0a-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="88b0a-148">Adicionar recomendações à tela de transação</span><span class="sxs-lookup"><span data-stu-id="88b0a-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="88b0a-149">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="88b0a-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="88b0a-150">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="88b0a-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="88b0a-151">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="88b0a-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="88b0a-152">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="88b0a-152">Product recommendations FAQ</span></span>](faq-recommendations.md)
