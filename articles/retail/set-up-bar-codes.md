---
title: "Configurar códigos de barra"
description: "Este artigo descreve como usar códigos de barras no Microsoft Dynamics 365 para Varejo."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fdc56bf468babd4b0b0652d9791114af676c8470
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="set-up-bar-codes"></a><span data-ttu-id="74279-103">Configurar códigos de barras</span><span class="sxs-lookup"><span data-stu-id="74279-103">Set up bar codes</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="74279-104">Este artigo descreve como usar códigos de barras no Microsoft Dynamics 365 para Varejo.</span><span class="sxs-lookup"><span data-stu-id="74279-104">This article describes how to use bar codes in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="74279-105">Você pode usar códigos de barras para comprar e vender produtos, rastrear variantes de produtos, configurar clientes e funcionários.</span><span class="sxs-lookup"><span data-stu-id="74279-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="74279-106">Você também pode usar códigos de barras para emitir e endossar cupons, vales-presentes e memorandos de crédito.</span><span class="sxs-lookup"><span data-stu-id="74279-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="74279-107">Você pode configurar produtos de varejo para tenham códigos de barras padrão ou personalizados, e códigos de barras internos.</span><span class="sxs-lookup"><span data-stu-id="74279-107">You can set up retail products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="74279-108">Os produtos podem ter mais de um código de barras.</span><span class="sxs-lookup"><span data-stu-id="74279-108">Products can have more than one bar code.</span></span> <span data-ttu-id="74279-109">Por exemplo, um produto podem ter vários códigos de barras se vier de vários fabricantes ou se tiver variantes baseadas em tamanho, estilo ou cor.</span><span class="sxs-lookup"><span data-stu-id="74279-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="74279-110">Os códigos de barra podem incluir o peso ou o preço do produto.</span><span class="sxs-lookup"><span data-stu-id="74279-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="74279-111">Máscaras de código de barras são modelos usados para criar códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="74279-111">Bar code masks are templates that are used to create bar codes.</span></span> <span data-ttu-id="74279-112">**Observação:** se você atribuir um código de barras exclusivo a cada combinação de variantes, poderá passar o código de barras no scanner da registradora e permitir que o programa determine que variante do produto está sendo vendida.</span><span class="sxs-lookup"><span data-stu-id="74279-112">**Note:** If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="74279-113">Você também pode coletar e ver estatísticas sobre vendas por variante.</span><span class="sxs-lookup"><span data-stu-id="74279-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="74279-114">A cada grupo de tamanhos, cores e estilos pode ser atribuído um número exclusivo que identifica o grupo no código de barras.</span><span class="sxs-lookup"><span data-stu-id="74279-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="74279-115">O Dynamics 365 para Varejo utiliza a máscara de código de barras para gerar automaticamente códigos de barras para cada combinação de variantes.</span><span class="sxs-lookup"><span data-stu-id="74279-115">Dynamics 365 for Retail uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="74279-116">Essa funcionalidade pode ser útil quando há muitos tamanhos, cores e estilos, pois o número de combinações aumenta significativamente quando cada código de variante é adicionado.</span><span class="sxs-lookup"><span data-stu-id="74279-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="74279-117">Se essa funcionalidade não for usada, os códigos de barras devem ser atribuídos manualmente a cada combinação que representa uma variante de produto.</span><span class="sxs-lookup"><span data-stu-id="74279-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span> <span data-ttu-id="74279-118">É possível criar códigos de barras de modo manual ou automático.</span><span class="sxs-lookup"><span data-stu-id="74279-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="74279-119">Para criar códigos de barras, conclua as tarefas a seguir na ordem em que são listadas.</span><span class="sxs-lookup"><span data-stu-id="74279-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1.  <span data-ttu-id="74279-120">[Configurar caracteres da máscara do código de barras](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="74279-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2.  <span data-ttu-id="74279-121">[Configurar máscaras de código de barras](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="74279-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3.  <span data-ttu-id="74279-122">Defina configurações do código de barras.</span><span class="sxs-lookup"><span data-stu-id="74279-122">Configure bar code setups.</span></span>
4.  <span data-ttu-id="74279-123">Crie códigos de barras para produtos.</span><span class="sxs-lookup"><span data-stu-id="74279-123">Create bar codes for products.</span></span>


<a name="see-also"></a><span data-ttu-id="74279-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="74279-124">See also</span></span>
--------

[<span data-ttu-id="74279-125">Configurar máscaras de código de barras</span><span class="sxs-lookup"><span data-stu-id="74279-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)




