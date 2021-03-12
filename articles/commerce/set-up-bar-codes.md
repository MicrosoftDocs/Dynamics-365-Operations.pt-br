---
title: Configurar códigos de barras
description: Este artigo descreve como usar códigos de barras no Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 86a29935974fbe30947c089d161f024428230b51
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969767"
---
# <a name="set-up-bar-codes"></a><span data-ttu-id="b9118-103">Configurar códigos de barras</span><span class="sxs-lookup"><span data-stu-id="b9118-103">Set up bar codes</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b9118-104">Este artigo descreve como usar códigos de barras no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b9118-104">This article describes how to use bar codes in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b9118-105">Você pode usar códigos de barras para comprar e vender produtos, rastrear variantes de produtos, configurar clientes e funcionários.</span><span class="sxs-lookup"><span data-stu-id="b9118-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="b9118-106">Você também pode usar códigos de barras para emitir e endossar cupons, vales-presentes e memorandos de crédito.</span><span class="sxs-lookup"><span data-stu-id="b9118-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="b9118-107">Você pode configurar produtos para que tenham códigos de barras padrão ou personalizados, e códigos de barras internos.</span><span class="sxs-lookup"><span data-stu-id="b9118-107">You can set up products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="b9118-108">Os produtos podem ter mais de um código de barras.</span><span class="sxs-lookup"><span data-stu-id="b9118-108">Products can have more than one bar code.</span></span> <span data-ttu-id="b9118-109">Por exemplo, um produto podem ter vários códigos de barras se vier de vários fabricantes ou se tiver variantes baseadas em tamanho, estilo ou cor.</span><span class="sxs-lookup"><span data-stu-id="b9118-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="b9118-110">Os códigos de barra podem incluir o peso ou o preço do produto.</span><span class="sxs-lookup"><span data-stu-id="b9118-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="b9118-111">Máscaras de código de barras são modelos usados para criar códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="b9118-111">Bar code masks are templates that are used to create bar codes.</span></span>

> [!NOTE]
> <span data-ttu-id="b9118-112">Se você atribuir um único código de barras a cada combinação de variantes, poderá verificar o código de barras no registro e permitir que o programa determine que variante do produto está sendo vendida.</span><span class="sxs-lookup"><span data-stu-id="b9118-112">If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="b9118-113">Você também pode coletar e ver estatísticas sobre vendas por variante.</span><span class="sxs-lookup"><span data-stu-id="b9118-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="b9118-114">A cada grupo de tamanhos, cores e estilos pode ser atribuído um número exclusivo que identifica o grupo no código de barras.</span><span class="sxs-lookup"><span data-stu-id="b9118-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="b9118-115">O Commerce usa a máscara de código de barra para gerar automaticamente códigos de barra para cada combinação variante.</span><span class="sxs-lookup"><span data-stu-id="b9118-115">Commerce uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="b9118-116">Essa funcionalidade pode ser útil quando há muitos tamanhos, cores e estilos, pois o número de combinações aumenta significativamente quando cada código de variante é adicionado.</span><span class="sxs-lookup"><span data-stu-id="b9118-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="b9118-117">Se essa funcionalidade não for usada, os códigos de barras devem ser atribuídos manualmente a cada combinação que representa uma variante de produto.</span><span class="sxs-lookup"><span data-stu-id="b9118-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span>

<span data-ttu-id="b9118-118">É possível criar códigos de barras de modo manual ou automático.</span><span class="sxs-lookup"><span data-stu-id="b9118-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="b9118-119">Para criar códigos de barras, conclua as tarefas a seguir na ordem em que são listadas.</span><span class="sxs-lookup"><span data-stu-id="b9118-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1. <span data-ttu-id="b9118-120">[Configurar caracteres da máscara do código de barras](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="b9118-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2. <span data-ttu-id="b9118-121">[Configurar máscaras de código de barras](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="b9118-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3. <span data-ttu-id="b9118-122">Defina configurações do código de barras.</span><span class="sxs-lookup"><span data-stu-id="b9118-122">Configure bar code setups.</span></span>
4. <span data-ttu-id="b9118-123">[Crie códigos de barras para produtos](../supply-chain/pim/tasks/create-bar-code-product.md).</span><span class="sxs-lookup"><span data-stu-id="b9118-123">[Create bar codes for products](../supply-chain/pim/tasks/create-bar-code-product.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b9118-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b9118-124">Additional resources</span></span>

[<span data-ttu-id="b9118-125">Configurar máscaras de código de barras</span><span class="sxs-lookup"><span data-stu-id="b9118-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)
