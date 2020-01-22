---
title: Dados de demonstração das recomendações de produtos do Omnicanal
description: Este documento visa oferecer orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.
author: bebeale
manager: AnnBe
ms.date: 12/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 31aa5dbd2fa814fd572024a4ae36b9d9b46a2fb0
ms.sourcegitcommit: 398c0652acde12c953de007d06055456d6e0a516
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2019
ms.locfileid: "2872317"
---
# <a name="omni-channel-product-recommendations-demo-data"></a><span data-ttu-id="5f475-103">Dados de demonstração das recomendações de produtos do Omnicanal</span><span class="sxs-lookup"><span data-stu-id="5f475-103">Omni-channel product recommendations demo data</span></span>

<span data-ttu-id="5f475-104">Este documento visa oferecer orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.</span><span class="sxs-lookup"><span data-stu-id="5f475-104">This document aims to provide guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="5f475-105">As recomendações de produtos do omnicanal fornecem um conjunto de listas de produtos editorialmente organizado ou gerado de forma programática.</span><span class="sxs-lookup"><span data-stu-id="5f475-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated ordered list of products.</span></span> <span data-ttu-id="5f475-106">Essas listas podem ser usadas em vários cenários, conforme a necessidade comercial.</span><span class="sxs-lookup"><span data-stu-id="5f475-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="5f475-107">Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="5f475-107">For more information about product recommendation lists, see [Product recommendations overview.](../commerce/product-recommendations.md)</span></span>

<span data-ttu-id="5f475-108">Para Ambientes do Dynamics da Camada 2 e mais altas, as recomendações de produtos são computadas automaticamente com base nos dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="5f475-108">For Tier-2 and higher Dynamics Environments product recommendations are automatically computed based on customer data.</span></span>
<span data-ttu-id="5f475-109">Usar dados de demonstração das recomendações de produtos não desabilita nenhuma solução de recomendações de produtos já provisionada no ambiente e nenhum custo associado ao seu uso.</span><span class="sxs-lookup"><span data-stu-id="5f475-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="5f475-110">Para ambientes da Camada 1, as recomendações de produtos são baseadas somente nos dados estáticos de demonstração armazenados em um arquivo csv.</span><span class="sxs-lookup"><span data-stu-id="5f475-110">For Tier-1 environments product recommendations are based only off the static demo data stored in a csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="5f475-111">Ativando dados de demonstração das recomendações de produtos em um ambiente</span><span class="sxs-lookup"><span data-stu-id="5f475-111">Enabling product recommendations demo data in an environment</span></span>

<span data-ttu-id="5f475-112">Os clientes devem implantar a **Extensão da Demonstração da Versão Prévia do Dynamics 365 Commerce** ao respectivo ambiente, a qual habilita automaticamente os dados de demonstração das recomendações de produtos.</span><span class="sxs-lookup"><span data-stu-id="5f475-112">Customers need to deploy the **Dynamics 365 Commerce Preview Demo Extension** to the respective environment, which automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="5f475-113">Dados de demonstração padrão</span><span class="sxs-lookup"><span data-stu-id="5f475-113">Default demo data</span></span>
<span data-ttu-id="5f475-114">Cada tipo de ambiente do Onebox vem com um conjunto pré-carregado de dados de demonstração das recomendações de produtos armazenados no arquivo separado por vírgulas **“reco_demo_data.csv”**, localizado na mesma pasta que este documento no Retail Server.</span><span class="sxs-lookup"><span data-stu-id="5f475-114">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated **‘reco_demo_data.csv’** file, located in the same folder as this document on Retail Server.</span></span>

<span data-ttu-id="5f475-115">Esses dados são estruturados ao longo das seguintes colunas</span><span class="sxs-lookup"><span data-stu-id="5f475-115">This data is structured along the following columns</span></span>

| <span data-ttu-id="5f475-116">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="5f475-116">Column name</span></span>         | <span data-ttu-id="5f475-117">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5f475-117">Mandatory</span></span>          | <span data-ttu-id="5f475-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f475-118">Description</span></span>                                                                                                                                 | <span data-ttu-id="5f475-119">Valores Possíveis</span><span class="sxs-lookup"><span data-stu-id="5f475-119">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="5f475-120">RecoList</span><span class="sxs-lookup"><span data-stu-id="5f475-120">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="5f475-122">O tipo específico da lista de recomendações de produtos que o ponto de dados de demonstração vai gerar.</span><span class="sxs-lookup"><span data-stu-id="5f475-122">The specific product   recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="5f475-123">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="5f475-123">RecoBestSelling</span></span></li><li><span data-ttu-id="5f475-124">RecoNew</span><span class="sxs-lookup"><span data-stu-id="5f475-124">RecoNew</span></span></li><li><span data-ttu-id="5f475-125">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="5f475-125">RecoTrending</span></span></li><li><span data-ttu-id="5f475-126">RecoCart</span><span class="sxs-lookup"><span data-stu-id="5f475-126">RecoCart</span></span></li><li><span data-ttu-id="5f475-127">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="5f475-127">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="5f475-128">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="5f475-128">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="5f475-130">O número específico da unidade operacional na qual espera-se que surjam as recomendações de produtos.</span><span class="sxs-lookup"><span data-stu-id="5f475-130">The specific   operating unit number where product recommendations are expected to be   surfaced in.</span></span>                                        |                                                                              |
| <span data-ttu-id="5f475-131">Categoria</span><span class="sxs-lookup"><span data-stu-id="5f475-131">Category</span></span>            |                    |    <span data-ttu-id="5f475-132">A categoria para a qual a lista específica deve ser retornada.</span><span class="sxs-lookup"><span data-stu-id="5f475-132">The category the   specific list should be returned for.</span></span> <span data-ttu-id="5f475-133">Se nenhuma categoria for especificada, a lista será somente para a parte superior da hierarquia de navegação.</span><span class="sxs-lookup"><span data-stu-id="5f475-133">If no category is specified, list is   for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="5f475-134">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="5f475-134">SeedItemId</span></span>          |                    |    <span data-ttu-id="5f475-135">Para listas que exigem a semente (RecoPeopleAlsoBuy e RecoCart) os produtos para os quais essas listas devem mostrar produtos adicionais.</span><span class="sxs-lookup"><span data-stu-id="5f475-135">For lists that   require seed (RecoPeopleAlsoBuy and RecoCart) the product those lists should   show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="5f475-136">ItemIds</span><span class="sxs-lookup"><span data-stu-id="5f475-136">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="5f475-138">Um ou mais produtos a serem retornados como o resultado, separados por **“;”**.</span><span class="sxs-lookup"><span data-stu-id="5f475-138">One or more products   to be returned as the result, separated by **‘;’**.</span></span>                                                                  |                                                                              |


## <a name="customize-demo-data"></a><span data-ttu-id="5f475-139">Personalizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="5f475-139">Customize demo data</span></span>
<span data-ttu-id="5f475-140">Os clientes podem editar os dados de demonstração padrão com todas as informações de produtos e categorias que são configurada na matriz.</span><span class="sxs-lookup"><span data-stu-id="5f475-140">Customers can edit the default demo data with any product and category information that is configured in HQ.</span></span> <span data-ttu-id="5f475-141">Depois que o CSV for atualizado, as recomendações de produtos retornadas para os clientes refletirão imediatamente as alterações.</span><span class="sxs-lookup"><span data-stu-id="5f475-141">Once the CSV is updated, the Product Recommendations returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="5f475-142">A extensão contém um arquivo de dados chamado RecoMockDataset.csv que permite que o cliente controle o conjunto de dados usado para fornecer os resultados fictícios de recomendações.</span><span class="sxs-lookup"><span data-stu-id="5f475-142">The extension contains a datafile called RecoMockDataset.csv which allows the customer to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="5f475-143">O nome de arquivo pode ser controlado por meio da configuração da extensão usando a configuração **ext.Recommendations.DemoFilePath** .</span><span class="sxs-lookup"><span data-stu-id="5f475-143">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="5f475-144">Isso permite que os clientes tenham vários conjunto de dados disponíveis que podem ser alternados com facilidade por meio da configuração.</span><span class="sxs-lookup"><span data-stu-id="5f475-144">This enables the customers to have multiple datasets available that can be switched between easily through configuration.</span></span>

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="5f475-145">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5f475-145">Additional resources</span></span>

[<span data-ttu-id="5f475-146">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="5f475-146">Product recommendations overview</span></span>](../commerce/product-recommendations.md)

[<span data-ttu-id="5f475-147">Planejamento de ambiente</span><span class="sxs-lookup"><span data-stu-id="5f475-147">Environment planning</span></span>](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
