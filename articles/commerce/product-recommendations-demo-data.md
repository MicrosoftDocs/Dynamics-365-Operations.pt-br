---
title: Criar recomendações com dados de demonstração
description: Este documento oferece orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.
author: bebeale
manager: AnnBe
ms.date: 03/19/20
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 59cb5e5c9b59ff2127149e3e47b6c30c9c938a27
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154240"
---
# <a name="create-recommendations-with-demo-data"></a><span data-ttu-id="1a89f-103">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="1a89f-103">Create recommendations with demo data</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1a89f-104">Este documento oferece orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.</span><span class="sxs-lookup"><span data-stu-id="1a89f-104">This document provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="1a89f-105">As recomendações de produtos do omnicanal fornecem um conjunto de listas de produtos editorialmente organizados ou gerados de forma programática.</span><span class="sxs-lookup"><span data-stu-id="1a89f-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="1a89f-106">Essas listas podem ser usadas em vários cenários, conforme a necessidade comercial.</span><span class="sxs-lookup"><span data-stu-id="1a89f-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="1a89f-107">Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="1a89f-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="1a89f-108">Para ambientes do Dynamics 365 da Camada 2 e mais altas, as recomendações de produtos são computadas automaticamente com base nos dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="1a89f-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="1a89f-109">Usar dados de demonstração das recomendações de produtos não desabilita nenhuma solução de recomendações de produtos já provisionada no ambiente e nenhum custo associado ao seu uso.</span><span class="sxs-lookup"><span data-stu-id="1a89f-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="1a89f-110">Para ambientes da Camada 1, as recomendações de produtos são baseadas somente nos dados estáticos de demonstração armazenados em um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="1a89f-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="1a89f-111">Ativando dados de demonstração das recomendações de produtos em um ambiente</span><span class="sxs-lookup"><span data-stu-id="1a89f-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="1a89f-112">Para habilitar a data de demonstração das recomendações do produto, você precisa implantar a Extensão da Demonstração da Versão Prévia do Dynamics 365 Commerce para o respectivo ambiente.</span><span class="sxs-lookup"><span data-stu-id="1a89f-112">To enable product recommendations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="1a89f-113">Esta ação habilita automaticamente os dados de demonstração das recomendações.</span><span class="sxs-lookup"><span data-stu-id="1a89f-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="1a89f-114">Dados de demonstração padrão</span><span class="sxs-lookup"><span data-stu-id="1a89f-114">Default demo data</span></span>
<span data-ttu-id="1a89f-115">Cada tipo de ambiente do Onebox vem com um conjunto pré-carregado de dados de demonstração das recomendações de produtos no arquivo separado por vírgulas 'reco_demo_data.csv', localizado no Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="1a89f-115">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated 'reco_demo_data.csv' file, located on the Commerce Scale Unit.</span></span>

<span data-ttu-id="1a89f-116">Os dados são estruturados ao longo das seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="1a89f-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="1a89f-117">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="1a89f-117">Column name</span></span>         | <span data-ttu-id="1a89f-118">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="1a89f-118">Mandatory</span></span>          | <span data-ttu-id="1a89f-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="1a89f-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="1a89f-120">Valores Possíveis</span><span class="sxs-lookup"><span data-stu-id="1a89f-120">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="1a89f-121">RecoList</span><span class="sxs-lookup"><span data-stu-id="1a89f-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="1a89f-123">O tipo específico da lista de recomendações de produtos que o ponto de dados de demonstração vai gerar.</span><span class="sxs-lookup"><span data-stu-id="1a89f-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="1a89f-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="1a89f-124">RecoBestSelling</span></span></li><li><span data-ttu-id="1a89f-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="1a89f-125">RecoNew</span></span></li><li><span data-ttu-id="1a89f-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="1a89f-126">RecoTrending</span></span></li><li><span data-ttu-id="1a89f-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="1a89f-127">RecoCart</span></span></li><li><span data-ttu-id="1a89f-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="1a89f-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="1a89f-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="1a89f-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="1a89f-131">O número específico da unidade operacional na qual espera-se que surjam as recomendações de produtos.</span><span class="sxs-lookup"><span data-stu-id="1a89f-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="1a89f-132">Categoria</span><span class="sxs-lookup"><span data-stu-id="1a89f-132">Category</span></span>            |                    |    <span data-ttu-id="1a89f-133">A categoria para a qual a lista específica deve ser retornada.</span><span class="sxs-lookup"><span data-stu-id="1a89f-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="1a89f-134">Se nenhuma categoria for especificada, a lista será somente para a parte superior da hierarquia de navegação.</span><span class="sxs-lookup"><span data-stu-id="1a89f-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="1a89f-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="1a89f-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="1a89f-136">Para listas que exigem semente (RecoPeopleAlsoBuy and RecoCart), o produto para o qual essas listas devem mostrar produtos adicionais.</span><span class="sxs-lookup"><span data-stu-id="1a89f-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="1a89f-137">ItemIds</span><span class="sxs-lookup"><span data-stu-id="1a89f-137">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="1a89f-139">Um ou mais produtos a serem retornados como o resultado, separados por ';'.</span><span class="sxs-lookup"><span data-stu-id="1a89f-139">One or more products to be returned as the result, separated by ';'.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="1a89f-140">Personalizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="1a89f-140">Customize demo data</span></span>
<span data-ttu-id="1a89f-141">Você pode editar os dados de demonstração padrão com quaisquer informações de produtos e categorias configurados na matriz.</span><span class="sxs-lookup"><span data-stu-id="1a89f-141">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="1a89f-142">Depois que o .csv for atualizado, as recomendações de produtos retornadas para os clientes refletirão imediatamente as alterações.</span><span class="sxs-lookup"><span data-stu-id="1a89f-142">Once you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="1a89f-143">A extensão contém um arquivo de dados chamado 'RecoMockDataset.csv' que permite que você controle o conjunto de dados usado para fornecer os resultados fictícios das recomendações.</span><span class="sxs-lookup"><span data-stu-id="1a89f-143">The extension contains a datafile called 'RecoMockDataset.csv' which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="1a89f-144">O nome de arquivo pode ser controlado por meio da configuração da extensão usando a configuração **ext.Recommendations.DemoFilePath** .</span><span class="sxs-lookup"><span data-stu-id="1a89f-144">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="1a89f-145">Isso permite que você tenha vários conjuntos de dados disponíveis que podem ser alternados com facilidade por meio da configuração.</span><span class="sxs-lookup"><span data-stu-id="1a89f-145">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a><span data-ttu-id="1a89f-146">Recursos Adicionais</span><span class="sxs-lookup"><span data-stu-id="1a89f-146">Additional Resources</span></span>

[<span data-ttu-id="1a89f-147">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="1a89f-147">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="1a89f-148">Habilitar ADLS em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1a89f-148">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="1a89f-149">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="1a89f-149">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="1a89f-150">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="1a89f-150">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="1a89f-151">Cancelar recomendações personalizados</span><span class="sxs-lookup"><span data-stu-id="1a89f-151">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="1a89f-152">Adicionar recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="1a89f-152">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="1a89f-153">Adicionar recomendações à tela de transação</span><span class="sxs-lookup"><span data-stu-id="1a89f-153">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="1a89f-154">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="1a89f-154">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="1a89f-155">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="1a89f-155">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="1a89f-156">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="1a89f-156">Product recommendations FAQ</span></span>](faq-recommendations.md)
