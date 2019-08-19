---
title: Manutenção dos tipos do atributo
description: Este tópico explica como criar tipos de atributo no Asset Management.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b3247f693f5934b3fbf83b7b831c7ed221514cb
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783062"
---
# <a name="maintenance-attribute-types"></a><span data-ttu-id="0f699-103">Manutenção dos tipos do atributo</span><span class="sxs-lookup"><span data-stu-id="0f699-103">Maintenance attribute types</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="0f699-104">Este tópico explica como criar tipos de atributo no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="0f699-104">This topic explains how to create attribute types in Asset Management.</span></span> <span data-ttu-id="0f699-105">Os atributos são usados para descrever as propriedades dos vários elementos.</span><span class="sxs-lookup"><span data-stu-id="0f699-105">Attributes are used to describe the properties of various elements.</span></span> <span data-ttu-id="0f699-106">Você pode configurar atributos nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="0f699-106">You can set up attributes on the following elements:</span></span>

- [<span data-ttu-id="0f699-107">Tipos de locais funcionais</span><span class="sxs-lookup"><span data-stu-id="0f699-107">Functional location types</span></span>](../setup-for-functional-locations/functional-location-types.md)
- [<span data-ttu-id="0f699-108">Locais funcionais</span><span class="sxs-lookup"><span data-stu-id="0f699-108">Functional locations</span></span>](../functional-locations/create-functional-locations.md)
- [<span data-ttu-id="0f699-109">Tipos de ativo</span><span class="sxs-lookup"><span data-stu-id="0f699-109">Asset types</span></span>](../setup-for-objects/object-types.md)
- <span data-ttu-id="0f699-110">Ativos</span><span class="sxs-lookup"><span data-stu-id="0f699-110">Assets</span></span>

<span data-ttu-id="0f699-111">Os atributos configurados podem variar, dependendo do elemento.</span><span class="sxs-lookup"><span data-stu-id="0f699-111">The attributes that you can set up vary, depending on the element.</span></span> <span data-ttu-id="0f699-112">Por exemplo, para um local funcional, você pode configurar atributos da configuração e do tamanho físico do local.</span><span class="sxs-lookup"><span data-stu-id="0f699-112">For example, for a functional location, you can set up attributes for the configuration and physical size of the location.</span></span> <span data-ttu-id="0f699-113">Para um tipo de ativo ou um ativo, você pode configurar atributos para o volume do motor, consumo de energia e capacidade máxima de carga sob condições diferentes.</span><span class="sxs-lookup"><span data-stu-id="0f699-113">For an asset type or an asset, you can set up attributes for engine volume, power consumption, and maximum load capacity under different conditions.</span></span>

## <a name="create-attribute-types"></a><span data-ttu-id="0f699-114">Criar tipos de atributo</span><span class="sxs-lookup"><span data-stu-id="0f699-114">Create attribute types</span></span>

<span data-ttu-id="0f699-115">Você pode criar seus próprios tipos de atributo.</span><span class="sxs-lookup"><span data-stu-id="0f699-115">You can create your own attribute types.</span></span> <span data-ttu-id="0f699-116">Além disso, você pode transferir dimensões do produto do Microsoft Dynamics 365 for Finance and Operations para a página **Tipos de atributo**.</span><span class="sxs-lookup"><span data-stu-id="0f699-116">Additionally, you can transfer product dimensions from Microsoft Dynamics 365 for Finance and Operations to the **Attribute types** page.</span></span>

1. <span data-ttu-id="0f699-117">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Tipos de atributo**.</span><span class="sxs-lookup"><span data-stu-id="0f699-117">Select **Asset management** \> **Setup** \> **Attribute types**.</span></span>
2. <span data-ttu-id="0f699-118">Na primeira vez que você configurar tipos de atributo, selecione **Criar dimensões do produto** para transferir automaticamente dimensões do produto padrão do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f699-118">The first time that you set up attribute types, select **Create product dimensions** to automatically transfer standard Finance and Operations product dimensions.</span></span>
3. <span data-ttu-id="0f699-119">Selecione **Novo** para criar um novo tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="0f699-119">Select **New** to create a new attribute type.</span></span>
4. <span data-ttu-id="0f699-120">No campo **Tipo de atributo**, insira um nome para o tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="0f699-120">In the **Attribute type** field, enter a name for the attribute type.</span></span>
5. <span data-ttu-id="0f699-121">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="0f699-121">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="0f699-122">No campo **Unidade** , selecione a unidade de atributo relevante, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0f699-122">In the **Unit** field, select the relevant attribute unit, as required.</span></span>
7. <span data-ttu-id="0f699-123">No campo **Tipo de dados**, selecione um tipo de dados para a unidade.</span><span class="sxs-lookup"><span data-stu-id="0f699-123">In the **Data type** field, select a data type for the unit.</span></span>
8. <span data-ttu-id="0f699-124">Se você tiver selecionado **String** como o tipo de dados, siga estas etapas para criar valores para o tipo de atributo:</span><span class="sxs-lookup"><span data-stu-id="0f699-124">If you selected **String** as the data type, follow these steps to create values for the attribute type:</span></span>

    1. <span data-ttu-id="0f699-125">Selecione o tipo de atributo e então selecione **Valores**.</span><span class="sxs-lookup"><span data-stu-id="0f699-125">Select the attribute type, and then select **Values**.</span></span>
    2. <span data-ttu-id="0f699-126">No campo **Valores do atributo**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0f699-126">In the **Attribute values** field, select **New**.</span></span>
    3. <span data-ttu-id="0f699-127">No campo **Tipo de atributo**, selecione um tipo de atributo (dimensão).</span><span class="sxs-lookup"><span data-stu-id="0f699-127">In the **Attribute type** field, select an attribute type (dimension).</span></span>
    4. <span data-ttu-id="0f699-128">No campo **Valor**, insira um valor relacionado.</span><span class="sxs-lookup"><span data-stu-id="0f699-128">In the **Value** field, enter a related value.</span></span>
    5. <span data-ttu-id="0f699-129">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="0f699-129">In the **Description** field, enter a description.</span></span>
    6. <span data-ttu-id="0f699-130">Salve o registro.</span><span class="sxs-lookup"><span data-stu-id="0f699-130">Save the record.</span></span>
    7. <span data-ttu-id="0f699-131">Retorne à página **Tipos de atributo**.</span><span class="sxs-lookup"><span data-stu-id="0f699-131">Return to the **Attribute types** page.</span></span>

9. <span data-ttu-id="0f699-132">Salve o registro.</span><span class="sxs-lookup"><span data-stu-id="0f699-132">Save the record.</span></span>

    <span data-ttu-id="0f699-133">O campo **Tipos de local funcional** mostra o número de locais funcionais que usam o tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="0f699-133">The **Functional location types** field shows the number of functional locations that are using the attribute type.</span></span> <span data-ttu-id="0f699-134">O campo **Tipos de ativo** mostra o número de tipos de ativo que o estão usando.</span><span class="sxs-lookup"><span data-stu-id="0f699-134">The **Asset types** field shows the number of asset types that are using it.</span></span>
