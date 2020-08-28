---
title: Habilitar recomendações de produtos
description: Este tópico explica como fazer recomendações de produto com base aprendizado de máquina de inteligência artificial (AI-ML) disponível para Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d2dacd4a94f706be5aa65947c0b6a92e281733ca
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665017"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="93ccb-103">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="93ccb-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="93ccb-104">Este tópico explica como fazer recomendações de produto com base aprendizado de máquina de inteligência artificial (AI-ML) disponível para Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="93ccb-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="93ccb-105">Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="93ccb-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="93ccb-106">Recomendações de pré-verificação</span><span class="sxs-lookup"><span data-stu-id="93ccb-106">Recommendations pre-check</span></span>

<span data-ttu-id="93ccb-107">Antes de habilitar, observe que as recomendações de produto têm suporte apenas para clientes do Commerce que migraram o armazenamento para usar o Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="93ccb-107">Before enabling, note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage.</span></span> 

<span data-ttu-id="93ccb-108">As configurações a seguir devem ser habilitadas no back office antes da habilitação das recomendações:</span><span class="sxs-lookup"><span data-stu-id="93ccb-108">The following configurations must be enabled in the back office before enabling recommendations:</span></span>

1. <span data-ttu-id="93ccb-109">Verifique se o Azure Data Lake Storage foi comprado e verificado com êxito no ambiente.</span><span class="sxs-lookup"><span data-stu-id="93ccb-109">Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment.</span></span> <span data-ttu-id="93ccb-110">Para obter mais informações, consulte [Verificar se o Azure Data Lake Storage foi comprado e verificado com êxito no ambiente](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="93ccb-110">For more information, see [Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment](enable-ADLS-environment.md).</span></span>
2. <span data-ttu-id="93ccb-111">Verifique se a atualização do armazenamento de entidade foi automatizada.</span><span class="sxs-lookup"><span data-stu-id="93ccb-111">Ensure that the entity store refresh has been automated.</span></span> <span data-ttu-id="93ccb-112">Para obter mais informações, consulte [Garantir se a atualização do armazenamento de entidade foi automatizada](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="93ccb-112">For more information, see [Ensure that the Entity store refresh has been automated](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>
3. <span data-ttu-id="93ccb-113">Confirme se a configuração da entidade Azure AD contém uma entrada para Recomendações.</span><span class="sxs-lookup"><span data-stu-id="93ccb-113">Confirm that Azure AD Identity configuration contains an entry for Recommendations.</span></span> <span data-ttu-id="93ccb-114">Veja a seguir mais informações sobre como executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="93ccb-114">More information on how to do this action is below.</span></span>

<span data-ttu-id="93ccb-115">Adicionalmente, verifique se as medições do RetailSale estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="93ccb-115">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="93ccb-116">Para saber mais sobre este processo de configuração, consulte [Trabalhar com medidas](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span><span class="sxs-lookup"><span data-stu-id="93ccb-116">To learn more about this set up process, see [Work with measures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span></span>

## <a name="azure-ad-identity-configuration"></a><span data-ttu-id="93ccb-117">Configuração de identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="93ccb-117">Azure AD Identity configuration</span></span>

<span data-ttu-id="93ccb-118">Essa etapa é necessária para todos os clientes que executam uma configuração de infraestrutura como um serviço (IaaS).</span><span class="sxs-lookup"><span data-stu-id="93ccb-118">This step is required for all customers running an infra-structure as a service (IaaS) configuration.</span></span> <span data-ttu-id="93ccb-119">Para clientes em execução na Service Fabric (IT), essa etapa deve ser automática e recomendamos verificar se a configuração está definida como esperado.</span><span class="sxs-lookup"><span data-stu-id="93ccb-119">For customers running on service fabric (SF), this step should be automatic and we recommend verifying the setting is configured as expected.</span></span>

### <a name="setup"></a><span data-ttu-id="93ccb-120">Instalação</span><span class="sxs-lookup"><span data-stu-id="93ccb-120">Setup</span></span>

1. <span data-ttu-id="93ccb-121">No back office, procure a página **Aplicativos do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="93ccb-121">From the back office, search for the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="93ccb-122">Verifique se existe uma entrada para "RecommendationSystemApplication-1".</span><span class="sxs-lookup"><span data-stu-id="93ccb-122">Verify if an entry exists for "RecommendationSystemApplication-1".</span></span>

<span data-ttu-id="93ccb-123">Se a entrada não existir, adicione uma nova entrada com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="93ccb-123">If the entry does not exist, add a new entry with the following information:</span></span>

- <span data-ttu-id="93ccb-124">**ID do cliente** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span><span class="sxs-lookup"><span data-stu-id="93ccb-124">**Client Id** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span></span>
- <span data-ttu-id="93ccb-125">**Nome** - RecommendationSystemApplication-1</span><span class="sxs-lookup"><span data-stu-id="93ccb-125">**Name** - RecommendationSystemApplication-1</span></span>
- <span data-ttu-id="93ccb-126">**ID do usuário** - RetailServiceAccount</span><span class="sxs-lookup"><span data-stu-id="93ccb-126">**User Id** - RetailServiceAccount</span></span>

<span data-ttu-id="93ccb-127">Salve e feche a página.</span><span class="sxs-lookup"><span data-stu-id="93ccb-127">Save and close the page.</span></span> 

## <a name="turn-on-recommendations"></a><span data-ttu-id="93ccb-128">Ative as recomendações</span><span class="sxs-lookup"><span data-stu-id="93ccb-128">Turn on recommendations</span></span>

<span data-ttu-id="93ccb-129">Para ativar as recomendações de produtos, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="93ccb-129">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="93ccb-130">Acesse **Retail e Commerce &gt; Recomendações de produto &gt; Parâmetros de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="93ccb-130">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="93ccb-131">Na lista de parâmetros compartilhados, selecione **Listas de Recomendação**.</span><span class="sxs-lookup"><span data-stu-id="93ccb-131">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="93ccb-132">Defina a opção **Habilitar recomendações** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="93ccb-132">Set the **Enable recommendations** option to **Yes**.</span></span>

![Ativando as recomendações](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="93ccb-134">Este procedimento inicia o processo de geração de listas recomendação de produto.</span><span class="sxs-lookup"><span data-stu-id="93ccb-134">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="93ccb-135">Pode levar várias horas antes que as listas estejam disponíveis e possam ser vistas no ponto de venda (PDV) ou em Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="93ccb-135">It may take several hours before the lists are available and can be viewed at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="93ccb-136">Configurar parâmetros da lista de recomendação</span><span class="sxs-lookup"><span data-stu-id="93ccb-136">Configure recommendation list parameters</span></span>

<span data-ttu-id="93ccb-137">Por padrão, a lista de recomendação de produtos baseada em AI-ML fornece valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="93ccb-137">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="93ccb-138">Você pode alterar os valores sugeridos padrão para se adequar ao fluxo de seus negócios.</span><span class="sxs-lookup"><span data-stu-id="93ccb-138">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="93ccb-139">Para saber mais sobre como alterar os parâmetros padrão, acesse [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="93ccb-139">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="93ccb-140">Mostrar recomendações em dispositivos POS</span><span class="sxs-lookup"><span data-stu-id="93ccb-140">Show recommendations on POS devices</span></span>

<span data-ttu-id="93ccb-141">Após habilitar recomendações no back office do Commerce, o painel de recomendações deverá ser adicionado à tela PDV de controle por meio da ferramenta de layout.</span><span class="sxs-lookup"><span data-stu-id="93ccb-141">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="93ccb-142">Para saber mais sobre esse processo, consulte [Adicionar um controle de recomendações à tela de transações em dispositivos de PDV](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="93ccb-142">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="93ccb-143">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="93ccb-143">Enable personalized recommendations</span></span>

<span data-ttu-id="93ccb-144">No Dynamics 365 Commerce, os varejistas podem disponibilizar recomendações de produtos personalizados (também conhecidos como personalização).</span><span class="sxs-lookup"><span data-stu-id="93ccb-144">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="93ccb-145">Dessa forma, as recomendações personalizadas podem ser incorporadas na experiência do cliente online e no ponto de venda.</span><span class="sxs-lookup"><span data-stu-id="93ccb-145">In this way, personalized recommendations can be incorporated into the online customer experience and at the point of sale.</span></span> <span data-ttu-id="93ccb-146">Quando a funcionalidade de personalização é ativada, o sistema pode associar as informações de compra e de produto de um usuário para gerar recomendações de produtos individualizadas.</span><span class="sxs-lookup"><span data-stu-id="93ccb-146">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

<span data-ttu-id="93ccb-147">Para saber mais sobre recomendações personalizadas, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="93ccb-147">To learn more about personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93ccb-148">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="93ccb-148">Additional resources</span></span>

[<span data-ttu-id="93ccb-149">Visão geral das recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="93ccb-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="93ccb-150">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="93ccb-150">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="93ccb-151">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="93ccb-151">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="93ccb-152">Habilitar recomendações de "comprar looks semelhantes"</span><span class="sxs-lookup"><span data-stu-id="93ccb-152">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="93ccb-153">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="93ccb-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="93ccb-154">Adicionar recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="93ccb-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="93ccb-155">Adicionar recomendações à tela de transação</span><span class="sxs-lookup"><span data-stu-id="93ccb-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="93ccb-156">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="93ccb-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="93ccb-157">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="93ccb-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="93ccb-158">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="93ccb-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="93ccb-159">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="93ccb-159">Product recommendations FAQ</span></span>](faq-recommendations.md)

