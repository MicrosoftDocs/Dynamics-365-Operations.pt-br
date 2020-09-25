---
title: Estender entidades de dados disponíveis em estoque
description: Este tópico fornece um exemplo que mostra como adicionar campos estendidos às exibições INVENTORSITEONHANDENTITY e INVENTWAREHOUSEONHANDENTITY, de forma que os recursos das entidades de dados disponíveis de estoque possam trabalhar com as extensões.
author: sherry-zheng
manager: tfehr
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e3bf3a7d48b0aa3e48845882be0ee86da17ed040
ms.sourcegitcommit: e276348a63bfdb9e712c0ea86e6c2a68c50872c0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665395"
---
# <a name="extend-inventory-on-hand-data-entities"></a><span data-ttu-id="44468-103">Estender entidades de dados disponíveis em estoque</span><span class="sxs-lookup"><span data-stu-id="44468-103">Extend inventory on-hand data entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="44468-104">O Microsoft Dynamics 365 Supply Chain Management fornece recursos de [extensibilidade](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) que permitem [adicionar campos a tabelas por meio da extensão](../../fin-ops-core/dev-itpro/extensibility/add-field-extension).</span><span class="sxs-lookup"><span data-stu-id="44468-104">Microsoft Dynamics 365 Supply Chain Management provides [extensibility](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) features that let you [add fields to tables through extension](../../fin-ops-core/dev-itpro/extensibility/add-field-extension).</span></span> <span data-ttu-id="44468-105">Este tópico fornece um exemplo que mostra como adicionar campos estendidos às exibições `INVENTORSITEONHANDENTITY` e `INVENTWAREHOUSEONHANDENTITY`, de forma que os recursos das entidades de dados disponíveis de estoque possam trabalhar com as extensões.</span><span class="sxs-lookup"><span data-stu-id="44468-105">This topic provides an example that shows how to add extended fields to the `INVENTORSITEONHANDENTITY` and `INVENTWAREHOUSEONHANDENTITY` views, so that the capabilities of the inventory on-hand data entities can work with the extensions.</span></span> <span data-ttu-id="44468-106">Para obter mais informações sobre entidades de dados, consulte [Visão geral de gerenciamento de dados](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span><span class="sxs-lookup"><span data-stu-id="44468-106">For more information about data entities, see [Data management overview](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="44468-107">Esta é uma lista de algumas entidades de dados disponíveis em estoque:</span><span class="sxs-lookup"><span data-stu-id="44468-107">Here is a list of some of the inventory on-hand data entities:</span></span>
>
> - <span data-ttu-id="44468-108">Estoque disponível por site</span><span class="sxs-lookup"><span data-stu-id="44468-108">Inventory on-hand by site</span></span>
> - <span data-ttu-id="44468-109">Estoque disponível por site V2</span><span class="sxs-lookup"><span data-stu-id="44468-109">Inventory on-hand by site V2</span></span>
> - <span data-ttu-id="44468-110">Estoque disponível por depósito</span><span class="sxs-lookup"><span data-stu-id="44468-110">Inventory on-hand by warehouse</span></span>
> - <span data-ttu-id="44468-111">Estoque disponível por depósito v2</span><span class="sxs-lookup"><span data-stu-id="44468-111">Inventory on-hand by warehouse v2</span></span>

<span data-ttu-id="44468-112">Depois de adicionar campos às tabelas que são usadas pela exibição `inventSiteOnHandView`, você deve sincronizar o mecanismo para que as extensões sejam reconhecidas corretamente.</span><span class="sxs-lookup"><span data-stu-id="44468-112">After you add fields to tables that are used by the `inventSiteOnHandView` view, you must sync the engine so that the extensions are correctly recognized.</span></span>

1. <span data-ttu-id="44468-113">Estenda a exibição `InventSiteOnHandView` adicionando o campo de extensão.</span><span class="sxs-lookup"><span data-stu-id="44468-113">Extend the `InventSiteOnHandView` view by adding the extension field.</span></span>
1. <span data-ttu-id="44468-114">Estenda a exibição `InventSiteOnHandAggregatedView` com os campos de extensão.</span><span class="sxs-lookup"><span data-stu-id="44468-114">Extend the `InventSiteOnHandAggregatedView` view with the extension fields.</span></span>
1. <span data-ttu-id="44468-115">Estenda a classe de viewBuilder `InventSiteOnHandAggregatedViewBuilder` modificando o método `getExtensionFields()`.</span><span class="sxs-lookup"><span data-stu-id="44468-115">Extend the `InventSiteOnHandAggregatedViewBuilder` viewBuilder class by modifying the `getExtensionFields()` method.</span></span> <span data-ttu-id="44468-116">Dessa forma, você mapeia os campos de exibição antigos para novos campos de exibição quando a sincronização do viewBuilder é executada.</span><span class="sxs-lookup"><span data-stu-id="44468-116">In this way, you map old view fields to new view fields when viewBuilder synchronization is run.</span></span>

<span data-ttu-id="44468-117">Por exemplo, você adicionou os seguintes quatro campos à tabela `InventTable` por meio de extensão:</span><span class="sxs-lookup"><span data-stu-id="44468-117">For example, you've added the following four fields to the `InventTable` table through extension:</span></span>

- <span data-ttu-id="44468-118">Campo personalizado 1</span><span class="sxs-lookup"><span data-stu-id="44468-118">Custom field 1</span></span>
- <span data-ttu-id="44468-119">Campo personalizado 2</span><span class="sxs-lookup"><span data-stu-id="44468-119">Custom field 2</span></span>
- <span data-ttu-id="44468-120">Campo personalizado 3</span><span class="sxs-lookup"><span data-stu-id="44468-120">Custom field 3</span></span>
- <span data-ttu-id="44468-121">Campo personalizado 4</span><span class="sxs-lookup"><span data-stu-id="44468-121">Custom field 4</span></span>

<span data-ttu-id="44468-122">No caso, você deve modificar o método `getExtensionFields()` conforme descrito a seguir.</span><span class="sxs-lookup"><span data-stu-id="44468-122">In the case, you must modify the `getExtensionFields()` method in the following way.</span></span>

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

<span data-ttu-id="44468-123">Depois de concluir essas etapas, você pode estender o estoque disponível por site e estoque disponível, por entidades de dados de depósito, adicionando os novos campos.</span><span class="sxs-lookup"><span data-stu-id="44468-123">After you complete these steps, you can extend the inventory on-hand by site and inventory on-hand by warehouse data entities by adding the new fields.</span></span> <span data-ttu-id="44468-124">Dessa forma, você garante que os campos estendidos sejam reconhecidos e incluídos durante a migração de dados que usa essas entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="44468-124">In this way, you ensure that the extended fields are recognized and included during data migration that uses those data entities.</span></span>