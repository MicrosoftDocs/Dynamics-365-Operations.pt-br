---
title: Gerenciamento de categorias de produtos
description: "Este tópico descreve como gerentes de mercadorias podem usar categorias de produtos de varejo para gerenciar relacionamentos entre a hierarquia de produtos de varejo e os detalhes de produtos liberados."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: pt-br
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a><span data-ttu-id="07285-103">Gerenciamento avançado de categorias e produtos</span><span class="sxs-lookup"><span data-stu-id="07285-103">Enhanced product and category management</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="07285-104">Este tópico descreve um modo avançado de gerenciar categorias de produtos de varejo e produtos no Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="07285-104">This topic describes an enhanced way to manage Retail product categories and products in Dynamics 365 for Retail.</span></span> <span data-ttu-id="07285-105">Esses aprimoramentos permitem que os gerentes de mercadorias visualizem uma estrutura comum de propriedades de produtos entre a hierarquia de produtos de varejo e os detalhes de produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="07285-105">These enhancements let merchandising managers view a common structure of product properties between Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="07285-106">Para saber mais sobre como gerenciar categorias de produtos de varejo, vá para **Hierarquia de produtos de varejo** no espaço de trabalho **Gerenciamento de categorias e produtos** e observe a estrutura avançada da página **Categoria de produto de varejo** .</span><span class="sxs-lookup"><span data-stu-id="07285-106">To learn more about managing Retail product categories, go to **Retail product hierarchy** from the **Category and product management** workspace, and note the enhanced structure of the **Retail product category** page.</span></span>

![Espaço de trabalho de gerenciamento de categorias e produtos](media/LaunchRetailProductHierarchy.png)

<span data-ttu-id="07285-108">Em versões anteriores, as propriedades de produtos eram divididas em **Propriedades básicas do produto** e **Propriedades de produto de varejo**, com base no escopo de sua aplicabilidade.</span><span class="sxs-lookup"><span data-stu-id="07285-108">In previous versions, product properties were divided into **Basic product properties** and **Retail product properties**, based on the scope of their applicability.</span></span> <span data-ttu-id="07285-109">As **Propriedades de produto de varejo** eram *globais* do escopo de aplicabilidade, o que significa que, para uma determinada **Propriedade de produto de varejo**, o mesmo valor é compartilhado em todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="07285-109">**Retail product properties** were *global* by scope of applicability, which means that for a given **Retail product property**, the same value is shared across all legal entities.</span></span> <span data-ttu-id="07285-110">As **Propriedades básicas de produto** são *específicas da entidade legal*.</span><span class="sxs-lookup"><span data-stu-id="07285-110">**Basic product properties** are *legal entity specific*.</span></span> <span data-ttu-id="07285-111">Em outras palavras, para uma determinada **Propriedade básica de produto**, o valor pode ser diferente em entidades legais, com base nos requisitos de negócios individuais.</span><span class="sxs-lookup"><span data-stu-id="07285-111">In other words, for a given **Basic product property** the value can differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="07285-112">Na estrutura avançada de categorias de produto de varejo, as propriedades de produto são separadas de forma lógica com base em sua aplicabilidade dentro de um grupo, para refletir a estrutura de formulário de detalhes do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="07285-112">In the enhanced Retail product category structure, product properties are logically separated based on their applicability within a group, to reflect the released product details form structure.</span></span>

![Agrupamento de campos baseado no escopo de aplicabilidade](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="07285-114">Você pode alternar entre gerenciar propriedades específicas de entidade legal em todas as entidades legais gerenciá-las para uma entidade legal específica.</span><span class="sxs-lookup"><span data-stu-id="07285-114">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="07285-115">Para fazer isso, selecione **Exibir/Editar todas as entidades legais** ou **Exibir/Editar uma entidade legal específica**.</span><span class="sxs-lookup"><span data-stu-id="07285-115">To do this, select either **View/Edit for all legal entities** or **View/Edit for a specific legal entity**.</span></span>

![Ativar exibição entre entidades individuais e todas as entidades legais](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Ativar exibição entre entidades individuais e todas as entidades legais](media/ToggleToEditForAllLegalEntities.PNG)  

<span data-ttu-id="07285-118">Em comparação a versões anteriores, na nova estrutura de categorias de produto de varejo, um gerente de mercadorias também pode definir valores padrão para um conjunto adicional de propriedades de produto a nível de categoria individual.</span><span class="sxs-lookup"><span data-stu-id="07285-118">Compared to previous versions, in the new Retail product category structure a merchandising manager can also define default values for an additional set of product properties at an individual category level.</span></span> <span data-ttu-id="07285-119">No momento da criação do produto, os valores de propriedades padrão de produto são herdados por um produto, com base em sua associação a uma categoria individual da hierarquia de produto de varejo.</span><span class="sxs-lookup"><span data-stu-id="07285-119">At the time of product creation, these default product property values are inherited by a product, based on their association with an individual category from Retail product hierarchy.</span></span> <span data-ttu-id="07285-120">Essas propriedades de produto herdadas também podem ser modificadas para cada produto para atender a requisitos de negócios individuais.</span><span class="sxs-lookup"><span data-stu-id="07285-120">These inherited product properties can also be modified for each product, to meet individual business requirements.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="07285-121">Selecionar propriedades para atualizar os produtos do formulário Categoria de produto de varejo</span><span class="sxs-lookup"><span data-stu-id="07285-121">Select properties to update products from the Retail product category form</span></span> 
 
<span data-ttu-id="07285-122">Você pode usar essa nova estrutura avançada para que as propriedades de produtos selecionem quais propriedades de produto devem ser enviadas a produtos associados.</span><span class="sxs-lookup"><span data-stu-id="07285-122">You can use this new enhanced structure for product properties to select which updated product properties must be pushed to associated products.</span></span> 

![Nova exibição avançada de produtos para atualização](media/NewUpdateProductsEnhancedView.PNG) 

<span data-ttu-id="07285-124">Os gerentes de mercadoria podem alterar essas propriedades herdadas de produto para cada produto, para atender a requisitos de negócios individuais.</span><span class="sxs-lookup"><span data-stu-id="07285-124">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>


