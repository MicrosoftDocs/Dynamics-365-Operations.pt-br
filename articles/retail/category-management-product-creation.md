---
title: "Gerenciamento e criação de categorias de produtos"
description: "Este tópico descreve os aprimoramentos feitos em relação à experiência de gerenciamento para categorias de produtos de varejo. Esses aprimoramentos permitem que os gerentes de mercadoria tenham uma correlação entre a hierarquia de produtos de varejo e os detalhes do produto liberado."
author: ashishmsft
manager: AnnBe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
ms.search.form: RetailCategoryAndProductWorkspace, RetailCategory
audience: Application User
ms.search.scope: Core, Retail
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: e269f6c3815cea55b69b7eb6a9a65bf7c9e15378
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="product-category-management-and-creation"></a><span data-ttu-id="2ba6a-104">Gerenciamento e criação de categorias de produtos</span><span class="sxs-lookup"><span data-stu-id="2ba6a-104">Product category management and creation</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="2ba6a-105">Os aprimoramentos feitos em relação à experiência de gerenciamento para categorias de produto de varejo permitem que os gerentes de mercadoria tenham uma correlação entre a hierarquia de produtos de varejo e os detalhes do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-105">Enhancements that have been made to the management experience for Retail product categories let merchandising managers have a correlation between Retail product hierarchy and released product details.</span></span> <span data-ttu-id="2ba6a-106">Para exibir esses aprimoramentos, no espaço de trabalho **Gerenciamento de categorias e produtos** , selecione **Hierarquia de produtos de varejo** para abrir a página **Nova estrutura de categoria de produtos de varejo** .</span><span class="sxs-lookup"><span data-stu-id="2ba6a-106">To view these enhancements, in the **Category & product management**  workspace, select **Retail product hierarchy** to open the **New structure of Retail product category** page.</span></span> 

<span data-ttu-id="2ba6a-107">Em versões anteriores, as propriedades de produtos eram divididas em Propriedades básicas do produto e Propriedades de produto de varejo, com base no escopo de sua aplicabilidade.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-107">In previous releases, product properties were divided into Basic product properties and Retail product properties, based on the scope of their applicability.</span></span> <span data-ttu-id="2ba6a-108">As propriedades de produto de varejo eram *globais*.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-108">Retail product properties were *global*.</span></span> <span data-ttu-id="2ba6a-109">Em outras palavras, para uma determinada propriedade do produto, o mesmo valor é compartilhado em todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-109">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="2ba6a-110">As propriedades básicas do produto eram *específicas da entidade legal*.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-110">Basic product properties were *legal entity–specific*.</span></span> <span data-ttu-id="2ba6a-111">Em outras palavras, uma determinada propriedade do produto pode diferir nas entidades legais, com base nos requisitos de negócios individuais.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-111">In other words, a given product property might differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="2ba6a-112">Com esses aprimoramentos, para propriedades do produto na categoria de varejo do produto, continuamos a separar os campos com base em sua aplicabilidade dentro de um grupo, para refletir a estrutura de formulário de detalhes do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-112">With these enhancements, for product properties in the Retail product category, we continue to separate the fields, based on their applicability within a group, to reflect the released product details form structure.</span></span>

<span data-ttu-id="2ba6a-113">Você pode alternar entre gerenciar propriedades específicas de entidade legal em todas as entidades legais gerenciá-las para uma entidade legal específica.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-113">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="2ba6a-114">Selecione **Exibir/Editar todas as entidades legais** ou **Exibir/Editar uma entidade legal específica**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-114">Just select **View/Edit for all legal entities** or **View/Edit for a specific legal entity** as you require.</span></span>

<span data-ttu-id="2ba6a-115">Os gerentes de mercadoria também podem definir valores padrão para um conjunto de propriedades adicionais de produto em nível de uma categoria individual.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-115">Merchandising managers can also define default values for an additional set of product properties at the level of an individual category.</span></span> <span data-ttu-id="2ba6a-116">Esses valores de propriedade são herdados por um produto, com base em sua associação a uma categoria no momento da criação do produto.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-116">These property values are inherited by a product, based on their association with a category at the time of product creation.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="2ba6a-117">Selecionar propriedades para atualizar os produtos do formulário Categoria de produto de varejo</span><span class="sxs-lookup"><span data-stu-id="2ba6a-117">Select properties to update products from the Retail product category form</span></span>

<span data-ttu-id="2ba6a-118">Você pode usar propriedades lógicas de agrupamento para selecionar quais propriedades atualizadas do produto devem ser enviadas por push para os produtos associados.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-118">You can use logical grouping properties to select which updated product properties should be pushed to associated products.</span></span>

<span data-ttu-id="2ba6a-119">Os gerentes de mercadoria podem alterar essas propriedades herdadas de produto para cada produto, para atender a requisitos de negócios individuais.</span><span class="sxs-lookup"><span data-stu-id="2ba6a-119">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>

