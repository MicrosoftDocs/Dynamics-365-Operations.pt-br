---
title: Obter recomendações de produtos usando dados de demonstração
description: Este documento oferece orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
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
ms.openlocfilehash: 6abac72b7530dc7b82c8e95faebdce791cf7dbd1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003225"
---
# <a name="get-product-recommendations-using-demo-data"></a><span data-ttu-id="9bbb6-103">Obter recomendações de produtos usando dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="9bbb6-103">Get product recommendations using demo data</span></span>
<span data-ttu-id="9bbb6-104">Este documento oferece orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-104">This document provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="9bbb6-105">As recomendações de produtos do omnicanal fornecem um conjunto de listas de produtos editorialmente organizados ou gerados de forma programática.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="9bbb6-106">Essas listas podem ser usadas em vários cenários, conforme a necessidade comercial.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="9bbb6-107">Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="9bbb6-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="9bbb6-108">Para ambientes do Dynamics 365 da Camada 2 e mais altas, as recomendações de produtos são computadas automaticamente com base nos dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="9bbb6-109">Usar dados de demonstração das recomendações de produtos não desabilita nenhuma solução de recomendações de produtos já provisionada no ambiente e nenhum custo associado ao seu uso.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="9bbb6-110">Para ambientes da Camada 1, as recomendações de produtos são baseadas somente nos dados estáticos de demonstração armazenados em um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="9bbb6-111">Ativando dados de demonstração das recomendações de produtos em um ambiente</span><span class="sxs-lookup"><span data-stu-id="9bbb6-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="9bbb6-112">Para habilitar a data de demonstração das recomendações do produto, você precisa implantar a Extensão da Demonstração da Versão Prévia do Dynamics 365 Commerce para o respectivo ambiente.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-112">To enable product recommensations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="9bbb6-113">Esta ação habilita automaticamente os dados de demonstração das recomendações.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="9bbb6-114">Dados de demonstração padrão</span><span class="sxs-lookup"><span data-stu-id="9bbb6-114">Default demo data</span></span>
<span data-ttu-id="9bbb6-115">Cada tipo de ambiente do Onebox vem com um conjunto pré-carregado de dados de demonstração das recomendações de produtos no arquivo separado por vírgulas ‘reco_demo_data.csv’, localizado no Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-115">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated ‘reco_demo_data.csv’ file, located on the Commerce Scale Unit.</span></span>

<span data-ttu-id="9bbb6-116">Os dados são estruturados ao longo das seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="9bbb6-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="9bbb6-117">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="9bbb6-117">Column name</span></span>         | <span data-ttu-id="9bbb6-118">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="9bbb6-118">Mandatory</span></span>          | <span data-ttu-id="9bbb6-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="9bbb6-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="9bbb6-120">Valores Possíveis</span><span class="sxs-lookup"><span data-stu-id="9bbb6-120">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="9bbb6-121">RecoList</span><span class="sxs-lookup"><span data-stu-id="9bbb6-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="9bbb6-123">O tipo específico da lista de recomendações de produtos que o ponto de dados de demonstração vai gerar.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="9bbb6-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="9bbb6-124">RecoBestSelling</span></span></li><li><span data-ttu-id="9bbb6-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="9bbb6-125">RecoNew</span></span></li><li><span data-ttu-id="9bbb6-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="9bbb6-126">RecoTrending</span></span></li><li><span data-ttu-id="9bbb6-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="9bbb6-127">RecoCart</span></span></li><li><span data-ttu-id="9bbb6-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="9bbb6-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="9bbb6-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="9bbb6-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="9bbb6-131">O número específico da unidade operacional na qual espera-se que surjam as recomendações de produtos.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="9bbb6-132">Categoria</span><span class="sxs-lookup"><span data-stu-id="9bbb6-132">Category</span></span>            |                    |    <span data-ttu-id="9bbb6-133">A categoria para a qual a lista específica deve ser retornada.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="9bbb6-134">Se nenhuma categoria for especificada, a lista será somente para a parte superior da hierarquia de navegação.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="9bbb6-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="9bbb6-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="9bbb6-136">Para listas que exigem semente (RecoPeopleAlsoBuy and RecoCart), o produto para o qual essas listas devem mostrar produtos adicionais.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="9bbb6-137">ItemIds</span><span class="sxs-lookup"><span data-stu-id="9bbb6-137">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="9bbb6-139">Um ou mais produtos a serem retornados como o resultado, separados por ‘;’.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-139">One or more products to be returned as the result, separated by ‘;’.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="9bbb6-140">Personalizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="9bbb6-140">Customize demo data</span></span>
<span data-ttu-id="9bbb6-141">Você pode editar os dados de demonstração padrão com quaisquer informações de produtos e categorias configurados na matriz.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-141">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="9bbb6-142">Depois que o .csv for atualizado, as recomendações de produtos retornadas para os clientes refletirão imediatamente as alterações.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-142">Once you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="9bbb6-143">A extensão contém um arquivo de dados chamado 'RecoMockDataset.csv' que permite que você controle o conjunto de dados usado para fornecer os resultados fictícios das recomendações.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-143">The extension contains a datafile called 'RecoMockDataset.csv' which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="9bbb6-144">O nome de arquivo pode ser controlado por meio da configuração da extensão usando a configuração **ext.Recommendations.DemoFilePath** .</span><span class="sxs-lookup"><span data-stu-id="9bbb6-144">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="9bbb6-145">Isso permite que você tenha vários conjuntos de dados disponíveis que podem ser alternados com facilidade por meio da configuração.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-145">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="9bbb6-146">Recursos Adicionais</span><span class="sxs-lookup"><span data-stu-id="9bbb6-146">Additional Resources</span></span>

[<span data-ttu-id="9bbb6-147">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="9bbb6-147">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="9bbb6-148">Planejamento de ambiente</span><span class="sxs-lookup"><span data-stu-id="9bbb6-148">Environment planning</span></span>](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
