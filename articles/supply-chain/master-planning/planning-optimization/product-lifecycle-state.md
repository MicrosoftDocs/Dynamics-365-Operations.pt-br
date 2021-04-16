---
title: Excluir produtos que têm estados específicos do ciclo de vida do produto
description: Este tópico explica como excluir produtos com base no estado do ciclo de vida ao usar a funcionalidade de otimização de planejamento.
author: ChristianRytt
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7028a509aa884589958542f7ec627d69dffcfcec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839238"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a><span data-ttu-id="29e5d-103">Excluir produtos que têm estados específicos do ciclo de vida do produto</span><span class="sxs-lookup"><span data-stu-id="29e5d-103">Exclude products that have specific product lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="29e5d-104">Produtos liberados e versões liberadas do produto incluem um campo **Estado do ciclo de vida do produto**.</span><span class="sxs-lookup"><span data-stu-id="29e5d-104">Released products and released product versions include a **Product lifecycle state** field.</span></span> <span data-ttu-id="29e5d-105">Este campo permite controlar, dentre outras coisas, quais produtos são incluídos durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="29e5d-105">This field lets you control, among other things, which products are included during master planning.</span></span> <span data-ttu-id="29e5d-106">É possível adicionar, remover e editar estados do ciclo de vida, conforme a necessidade, acessando **Gerenciamento de informações de produto \> Configuração \> Estado do ciclo de vida do produto**.</span><span class="sxs-lookup"><span data-stu-id="29e5d-106">You can add, remove, and edit lifecycle states as required by going to **Product information management \> Setup \> Product lifecycle state**.</span></span> <span data-ttu-id="29e5d-107">Para cada estado do ciclo de vida do produto, defina a opção **Está ativa para o planejamento** como *Sim* se os produtos que tiverem esse estado tiverem de ser incluídos durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="29e5d-107">For each product lifecycle state, set the **Is active for planning** option to *Yes* if products that have that state should be included during master planning.</span></span> <span data-ttu-id="29e5d-108">Quando a opção for definida como *Não*, os produtos e as grades associados serão excluídos de todo o planejamento mestre e de todos os cálculos no nível da BOM (lista de materiais).</span><span class="sxs-lookup"><span data-stu-id="29e5d-108">When the option is set to *No*, the associated products and variants will be excluded from all master planning and all calculations at the bill of materials (BOM) level.</span></span>

<span data-ttu-id="29e5d-109">Os produtos e as grades liberados nos quais o campo **Estado do ciclo de vida do produto** é deixado em branco são tratados como se tivessem um estado de ciclo de vida do produto, em que a opção **Ativo para planejamento** está definida como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="29e5d-109">Released products and variants where the **Product lifecycle state** field is left blank are treated as though they have a product lifecycle state where the **Is active for planning** option is set to *Yes*.</span></span> <span data-ttu-id="29e5d-110">Em outras palavras, eles serão incluídos durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="29e5d-110">In other words, they will be included during master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="29e5d-111">Para ajudar a evitar sugestões de fornecimento desnecessárias, é altamente recomendável que você associe todos os produtos e grades obsoletos com um estado do ciclo de vida do produto em que a opção **Está ativa para o planejamento** está definida como *Não*.</span><span class="sxs-lookup"><span data-stu-id="29e5d-111">To help avoid unnecessary supply suggestions, we strongly recommend that you associate all obsolete released products and variants with a product lifecycle state where the **Is active for planning** option is set to *No*.</span></span> <span data-ttu-id="29e5d-112">Essa abordagem é especialmente importante quando você trabalha com grades de configuração de produtos que não podem ser reutilizadas, pois ela ajudará a evitar desperdício.</span><span class="sxs-lookup"><span data-stu-id="29e5d-112">This approach is especially important when you work with product configuration variants that aren't reusable, because it will help prevent waste.</span></span>

## <a name="related-resources"></a><span data-ttu-id="29e5d-113">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="29e5d-113">Related resources</span></span>

<span data-ttu-id="29e5d-114">Para obter mais informações sobre estados de ciclo de vida de produtos, consulte a [Visão geral do estado de ciclo de vida de produtos](../../pim/product-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="29e5d-114">For more information about product lifecycle states, see [Product lifecycle state overview](../../pim/product-lifecycle.md).</span></span>

<span data-ttu-id="29e5d-115">Para obter informações detalhadas que incluem etapas para usar estados de ciclo de vida de produto para excluir produtos dos cálculos de planejamento mestre e do nível da BOM, consulte [Criar um estado do ciclo de vida do produto para excluir produtos do planejamento mestre](../../pim/tasks/exclude-products-master-planning.md).</span><span class="sxs-lookup"><span data-stu-id="29e5d-115">For detailed information that includes steps for using product lifecycle states to exclude products from master planning and BOM-level calculations, see [Create a product lifecycle state to exclude products from Master planning](../../pim/tasks/exclude-products-master-planning.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]