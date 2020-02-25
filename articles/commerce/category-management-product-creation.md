---
title: Gerenciar produtos e categorias de produtos
description: Este tópico descreve como os gerentes de mercadorias podem usar categorias de produtos para gerenciar relacionamentos entre a hierarquia de produtos de comércio e os detalhes dos produtos liberados.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 6e0c6a8048b5a2ef9a48495cd5e2609a1324a6e2
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021575"
---
# <a name="manage-product-categories-and-products"></a><span data-ttu-id="b1009-103">Gerenciar produtos e categorias de produtos</span><span class="sxs-lookup"><span data-stu-id="b1009-103">Manage product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="b1009-104">Este tópico descreve um modo avançado de gerenciar categorias de produtos e produtos no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b1009-104">This topic describes an enhanced way to manage product categories and products in Dynamics 365 Commerce.</span></span> <span data-ttu-id="b1009-105">Os aprimoramentos permitem que os gerentes de mercadoria visualizem uma estrutura de propriedades de produtos que é compartilhada entre a hierarquia de produtos e os detalhes de produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="b1009-105">The enhancements let merchandising managers view a structure of product properties that is shared between the product hierarchy and released product details.</span></span>

<span data-ttu-id="b1009-106">Para saber mais sobre como gerenciar categorias de produtos, no espaço de trabalho **Gerenciamento de categorias e produtos**, selecione o bloco **Hierarquia de produtos de comércio**.</span><span class="sxs-lookup"><span data-stu-id="b1009-106">To learn more about how to manage product categories, in the **Category and product management** workspace, select the **Commerce product hierarchy** tile.</span></span>

<span data-ttu-id="b1009-107">Observe a estrutura aprimorada da página **Hierarquia de produtos de comércio** que é exibida.</span><span class="sxs-lookup"><span data-stu-id="b1009-107">Notice the enhanced structure of the **Commerce product hierarchy** page that appears.</span></span> <span data-ttu-id="b1009-108">Em versões anteriores do aplicativo, as propriedades dos produtos eram divididas em *Propriedades básicas de produto* e *Propriedades de produto de varejo*, de acordo com o escopo de sua aplicabilidade.</span><span class="sxs-lookup"><span data-stu-id="b1009-108">In previous versions of the app, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="b1009-109">As propriedades de produto de varejo são *globais* no escopo de aplicabilidade.</span><span class="sxs-lookup"><span data-stu-id="b1009-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="b1009-110">Em outras palavras, para uma determinada propriedade do produto, o mesmo valor é compartilhado em todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="b1009-110">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="b1009-111">Por outro lado, as Propriedades básicas de produto são *específicas da entidade legal*.</span><span class="sxs-lookup"><span data-stu-id="b1009-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="b1009-112">Em outras palavras, para uma determinada Propriedade básica de produto, o valor pode ser diferente nas entidades legais, dependendo dos requisitos de negócios individuais de cada entidade legal.</span><span class="sxs-lookup"><span data-stu-id="b1009-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="b1009-113">Na estrutura avançada de categorias de produto, as propriedades de produto são separadas de forma lógica com base em sua aplicabilidade em um grupo, para refletir a estrutura do formulário de detalhes do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="b1009-113">In the enhanced product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Agrupamento de campos baseado no escopo de aplicabilidade das propriedades](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="b1009-115">Você pode alternar entre gerenciar propriedades específicas da entidade legal em todas as entidades legais e gerenciá-las para uma entidade legal específica.</span><span class="sxs-lookup"><span data-stu-id="b1009-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="b1009-116">Para gerenciar propriedades em todas as entidades legais, selecione **Exibir todas as entidades legais** (ou **Editar todas as entidades legais**).</span><span class="sxs-lookup"><span data-stu-id="b1009-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Exibir/Editar todas as entidades legais](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="b1009-118">Para gerenciar propriedades de uma entidade legal específica, selecione **Exibir uma entidade legal específica** (ou **Editar uma entidade legal específica**).</span><span class="sxs-lookup"><span data-stu-id="b1009-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Exibir/Editar uma entidade legal específica](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="b1009-120">Além disso, na estrutura de categorias de produto aprimorada, agora um gerente de mercadorias pode definir valores padrão para um conjunto adicional de propriedades de produto no nível da categoria individual.</span><span class="sxs-lookup"><span data-stu-id="b1009-120">Additionally, in the enhanced product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="b1009-121">Depois, quando os produtos forem criados, eles herdarão os valores padrão de suas propriedades de produto com base na associação dessas propriedades com uma categoria individual da hierarquia de produtos.</span><span class="sxs-lookup"><span data-stu-id="b1009-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in the product hierarchy.</span></span> <span data-ttu-id="b1009-122">Essas propriedades de produto herdadas também podem ser modificadas para cada produto para atender a requisitos de negócios individuais.</span><span class="sxs-lookup"><span data-stu-id="b1009-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a><span data-ttu-id="b1009-123">Selecionar propriedades para atualizar produtos na página Hierarquia de produtos de comércio</span><span class="sxs-lookup"><span data-stu-id="b1009-123">Selecting properties to update products on the Commerce product hierarchy page</span></span>

<span data-ttu-id="b1009-124">Você pode usar a nova estrutura aprimorada das propriedades de produtos para selecionar as propriedades de produto que devem ser enviadas aos produtos associados.</span><span class="sxs-lookup"><span data-stu-id="b1009-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="b1009-125">Na página **Hierarquia de produtos de comércio**, no Painel de Ação, selecione **Categoria** e, depois, selecione **Atualizar produtos** para abrir a caixa de diálogo **Atualizar produtos**.</span><span class="sxs-lookup"><span data-stu-id="b1009-125">On the **Commerce product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Caixa de diálogo Atualizar produtos](media/NewUpdateProductsEnhancedView.PNG)
