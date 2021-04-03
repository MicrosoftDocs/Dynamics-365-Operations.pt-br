---
title: Fabricantes e modelos de ativo
description: Este tópico explica como configurar fabricantes de ativo e modelos relacionados no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cec4f644af4a087464635d9a7ca825eb354747eb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259952"
---
# <a name="asset-manufacturers-and-models"></a><span data-ttu-id="25f4c-103">Fabricantes e modelos de ativo</span><span class="sxs-lookup"><span data-stu-id="25f4c-103">Asset manufacturers and models</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="25f4c-104">Este tópico explica como configurar fabricantes de ativo e modelos relacionados no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="25f4c-104">This topic explains how to set up asset manufacturers and related models in Asset Management.</span></span> <span data-ttu-id="25f4c-105">Os modelos podem ser relacionados aos tipos de ativo.</span><span class="sxs-lookup"><span data-stu-id="25f4c-105">Models can be related to asset types.</span></span>

## <a name="set-up-product-model-relations"></a><span data-ttu-id="25f4c-106">Configurar relações entre produtos e modelos</span><span class="sxs-lookup"><span data-stu-id="25f4c-106">Set up product-model relations</span></span>

1. <span data-ttu-id="25f4c-107">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Fabricante e modelo**.</span><span class="sxs-lookup"><span data-stu-id="25f4c-107">Select **Asset management** \> **Setup** \> **Assets** \> **Manufacturer and model**.</span></span>
2. <span data-ttu-id="25f4c-108">Selecione **Novo** para criar um novo produto.</span><span class="sxs-lookup"><span data-stu-id="25f4c-108">Select **New** to create a new product.</span></span>
3. <span data-ttu-id="25f4c-109">No campo **Fabricante**, insira um nome para o fabricante do ativo.</span><span class="sxs-lookup"><span data-stu-id="25f4c-109">In the **Manufacturer** field, enter a name for the asset manufacturer.</span></span>
4. <span data-ttu-id="25f4c-110">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="25f4c-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="25f4c-111">Na Guia Rápida **Modelos**, selecione **Adicionar** para criar um modelo de ativo que deva estar relacionado ao fabricante do ativo.</span><span class="sxs-lookup"><span data-stu-id="25f4c-111">On the **Models** FastTab, select **Add** to create an asset model that should be related to the asset manufacturer.</span></span>
6. <span data-ttu-id="25f4c-112">No campo **Modelo**, insira um nome para o modelo do ativo.</span><span class="sxs-lookup"><span data-stu-id="25f4c-112">In the **Model** field, enter a name for the asset model.</span></span>
7. <span data-ttu-id="25f4c-113">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="25f4c-113">In the **Description** field, enter a description.</span></span>
8. <span data-ttu-id="25f4c-114">No campo **Tipo de ativo**, selecione o tipo de ativo ao qual o modelo do fabricante deve estar relacionado.</span><span class="sxs-lookup"><span data-stu-id="25f4c-114">In the **Asset type** field, select the asset type that the manufacturer model should be related to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25f4c-115">Você também pode configurar relações para tipos, fabricantes e modelos de ativo na pesquisa **Tipos de ativo**.</span><span class="sxs-lookup"><span data-stu-id="25f4c-115">You can also set up relations for asset types, manufacturers, and models in the **Asset types** lookup.</span></span> <span data-ttu-id="25f4c-116">Para saber mais, consulte [Tipos de ativo](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="25f4c-116">For more information, see [Asset types](../setup-for-objects/object-types.md).</span></span>

    <span data-ttu-id="25f4c-117">Na Guia Rápida **Detalhes**, o campo **Modelos** mostra o número de modelos de ativo configurados no fabricante do ativo selecionado.</span><span class="sxs-lookup"><span data-stu-id="25f4c-117">In the **Details** FastTab, the **Models** field shows the number of asset models that are set up on the selected asset manufacturer.</span></span> <span data-ttu-id="25f4c-118">O campo **Ativos** mostra o número de ativos que usam o fabricante selecionado.</span><span class="sxs-lookup"><span data-stu-id="25f4c-118">The **Assets** field shows the number of assets that are using the selected manufacturer.</span></span>
    
    <span data-ttu-id="25f4c-119">O campo **Ativos** mostra o número de objetos que usam o modelo do fabricante.</span><span class="sxs-lookup"><span data-stu-id="25f4c-119">The **Assets** field shows the number of objects that are using the manufacturer model.</span></span>

> [!NOTE]
> <span data-ttu-id="25f4c-120">Um tipo de ativo pode não ter nenhuma relação de modelo do fabricante, pode estar relacionado a um modelo do fabricante do ativo ou pode estar relacionado a vários modelos do fabricante do ativo.</span><span class="sxs-lookup"><span data-stu-id="25f4c-120">An asset type can have no asset manufacturer model relations, it can be related to one asset manufacturer model, or it can be related multiple asset manufacturer models.</span></span> <span data-ttu-id="25f4c-121">Se um tipo de ativo estiver relacionado a pelo menos um modelo do fabricante, apenas as combinações configuradas na pesquisa **Modelo do fabricante** poderão ser selecionadas nas páginas do Asset Management onde uma combinação de um tipo, fabricante e modelo de ativo pode ser configurada.</span><span class="sxs-lookup"><span data-stu-id="25f4c-121">If an asset type is related to at least one manufacturer model, only the combinations that are set up in the **Manufacturer model** lookup can be selected on those Asset Management pages where a combination of an asset type, manufacturer, and model can be set up.</span></span> <span data-ttu-id="25f4c-122">Essas páginas incluem **Todos os ativos**, **Níveis de serviço de ativo**, **Padrões do tipo de trabalho** e **Linhas de orçamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="25f4c-122">These pages include **All assets**, **Asset service levels**, **Job type defaults**, and **Maintenance budget lines**.</span></span> <span data-ttu-id="25f4c-123">Se alguns tipos de ativo não estiverem relacionados a um modelo do fabricante, somente esses tipos de ativo, e os modelos do fabricante que também não tenham relação aos tipos de ativo, serão mostrados nas páginas.</span><span class="sxs-lookup"><span data-stu-id="25f4c-123">If some asset types aren't related to any manufacturer model, only those asset types, and manufacturer models that also have no relation to asset types, are shown on the pages.</span></span>

## <a name="select-a-manufacturer-and-model-on-an-object"></a><span data-ttu-id="25f4c-124">Selecionar um fabricante e modelo em um objeto</span><span class="sxs-lookup"><span data-stu-id="25f4c-124">Select a manufacturer and model on an object</span></span>

1. <span data-ttu-id="25f4c-125">Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos**.</span><span class="sxs-lookup"><span data-stu-id="25f4c-125">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="25f4c-126">Na coluna **Ativo**, selecione o link para o ativo.</span><span class="sxs-lookup"><span data-stu-id="25f4c-126">In the **Asset** column, select the link for the asset.</span></span> <span data-ttu-id="25f4c-127">A página **Detalhes** aparece.</span><span class="sxs-lookup"><span data-stu-id="25f4c-127">The **Details** page appears.</span></span>
3. <span data-ttu-id="25f4c-128">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25f4c-128">Select **Edit**.</span></span>
4. <span data-ttu-id="25f4c-129">Na Guia Rápida **Geral**, selecione valores nos campos **Fabricante** e **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="25f4c-129">On the **General** FastTab, select values in the **Manufacturer** and **Model** fields.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]